## Những gì bạn cần.

- Một chiếc máy tính có kết nối Internet

## Mục đích.

- để hiểu và khai thác kiểu đơn giản nhất của lỗ hỏng: command injection

## Gioi thiệu Bash Command Line

`date`: In ra ngày và thời gian

`ls`: danh sách các file và thư mục trong thư mục làm việc hiện tại

`pwd`: Im ra thư mục hiện tại đang làm việc

`cd`: chuyển đến thư mục mà bạn muốn

`echo "Hi "`: in ra text "Hi"

`date >> /home/cg/root/foo`: in ra ngày trong file /home/cg/root/foo

`echo "Hi" >> /home/cg/root/foo`: in ra text "hi" in file /home/cg/root/foo

`ls -l /home/cg/root`: danh sach, ở dạng dài, các file và thư mục của danh mục /home/cg/root

### Exploit the Ping Form 

- `google`

- `google; ls`: lỗi 

## what Commant Injection ?

- Command Injection là 1 cuộc tấn công trong đó mục tiêu là `thực hiện các lệnh tùy ý` trên máy chủ hệ điều hành thông qua 1 ứng dụng bị lỗ hỏng.

- Những cuộc tấn công là có thể khi 1 ứng dụng chuyển không  an toàn dữ liệu do người dùng cung cấp (forms, cookies, HTTP headers etc)
