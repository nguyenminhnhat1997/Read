### Proj 1: Linux Buffer Overflow (tràn ổ đĩa): Command Injection (10 pts. + 12pts. extra credit)

1. Purpose

- Phát triển 1 lỗi tràn bộ đệm (buffer overflow) khai thác trên Linux, sử dụng shell commands

Tạo 1 chương trình lỗi.

- Chương trình này nhận vào 1 tên từ user và in ra 1 thông báo "Goodbye". Khi nó call system() để in ra phiên bản Linux version. Nó sử dụng 2 buffers(bộ đệm) trong 1 subroutine(đoạn chương trình con) để làm mà trong 1 unsafe(k an toàn) manner(cách), cho phép tên bộ đệm tràn vào trong câu lệnh buffer

- Trong 1 cửa sổ Terminal, thực hiện command(câu lệnh) :

- `nano buf.c`

- Coppy và paste đoạn code sau:

```javascript
#include <string.h>
#include <stdio.h>

main(){
	char name[200];
	printf("What is your name ? \n");
	scanf("$s",name);
	bo(name, "uname -a");
}
int bo(char *name, char *cmd){
	char c[40];
	char buffer[40];
	printf("Name buffer address:  %x\n", buffer);
	printf("Command buffer addres: %x\n", c);
	strcpy(c, cmd);
	strcpy(buffer, name);
	printf("Goodbye, %s!\n", buffer);
	printf("Executing command: %s\n", c);
	fflush(stdout);
	system(c);
}
```

- Lưu file với `Ctrl+X,Y,Enter`

- Thực hiện câu lệnh này để biên dịch code mà không cần protections(bảo vệ) modern(hiện đại) against(chống lại) tràn đĩa, và với debugging(gỡ lội) symbols(ký hiệu)

- `gcc -g -fno-stack-protector -z execstack -o buf.c`

- Chạy chương trình bình thường với command: `./buf`

- Hiện kết quả như hình: 

<img src="http://sv1.upsieutoc.com/2017/03/06/1f52cd.png"/>

- Observing(quan sát) 1 tai họa.

- Nhập vào 15 chữ A vào tên của bạn, chương trình sẽ attempts(nổ lực) thực hiện câu lên AAAAAAA mấy chục lần.

<img src="http://sv1.upsieutoc.com/2017/03/06/10b74c.png"/>

- Tìm điểm code để injection vào 

 		B1 Ta thực hiện lại ./buf

 		B2 Nhập AAAAAAAAAABBBBBBBBBBCCCCCCCCCCDDDDDDDDDDEEEEEEEEEE

 		B3 Xem kết quả thì chương trình cố gắng để thực hiện câu lệnh EE, như hình. Vì thế bất kì text chúng ta đặt 
 		vào chỗ của EE sẽ thực thi.

 		[![10b74c.png](http://sv1.upsieutoc.com/2017/03/06/10b74c.png)](http://www.upsieutoc.com/image/YwaDfK)

