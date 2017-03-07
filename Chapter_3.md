# Web Application Technologies

Ưng dụng web `employ a myriad` (sử dụng vô số) các công nghệ để thực hiện những chức năng của nó. Chương này là 1 `short primer` (đầu tiến, ngắn) trên các kỹ thuật chủ chốt mà bạn 
`likely` (có thể) `encouter` (bắt gặp) khi tấn công web applications. Chúng ta sẽ `examine` (xem xét) giao thức HTTP, công nghệ được sử dụng phổ biến trên server và phía client, và các chương trình mã hóa được sử dụng để `represent` (đại diện ) cho dữ liêu trong những `situation` (tình huống) khác nhau.
Những kĩ thuật nhìn chung là dễ để hiểu, và `a grasp` (nắm bắt) những `features` (đặc điểm) `relevant` (liên quan) là chìa khóa  để `performing` (thực hiện) `effective` (hiệu quả) các cuộc tấn công chống lại web applications.

## The HTTP Protocol

Hypertext transfer protocol (HTTP) là 1 giao thức `communication` (truyền thông) cốt lõi được sử dụng để `access` truy cập World Wide Web và được sử dụng bởi tất cả các web applications ngày nay. Nó là 1 giao thức đơn giản được `originally` (ban đầu) được phát triển cho `retriecing` (truy xuất) tài nguyên văn bản tĩnh  
Nó đã được `extend` (kéo dài) và `leveraged` (được sử dụng) trong `various` (nhiều) cách để `enable` (cho phép) nó hỗ trợ các ứng dụng `distributed` (được phân bố) `complex` (phức tạp) mà hiện nay `commonplace` (phổ biến)

HTTP sử dụng kiểu thông báo message-based trong đó 1 client gửi 1 thông báo request và server trả về 1 thông báo response. Giao thức là `essentially` (về bản chất) `connectionless` (phi kết nối): mặc dù HTTP sử dụng TCP protocol như `mechanism` (cơ chế) vận chuyển của nó, mỗi `exchange` (trao đổi) request và response là một `transport-tion` (giao dịch) tự quản và có thể sử dụng 1 kết nối TCP khác.

## HTTP Requests

Tất cả thông báo HTTP (requests and responses) `consist` (bao gồm) 1 hoặc nhiều headers, mỗi header trên 1 dòng `separate` (riêng), theo sau bởi 1 `blank line` (dòng trắng) `mandatory` (bắt buộc), theo sau bởi 1 phần thân thông báo. một kiểu HTTP request như sau: 

<img src="http://sv1.upsieutoc.com/2017/03/07/3590960d31fb54e1.png"/>

Dòng đầu tiên của mỗi HTTP request `consists` bao gồm 3 items, `separated`  (cách nhau) bởi spaces.

- Động từ `indicating` (cho biết) method HTTP.method được sử dụng phổ biến nhất là `GET`, có chức năng là `retrieve` (lấy) 1 tài nguyên từ web server. GET requests không có 1 message body, vì thế nó không `further` (thêm) data sau dòng trống sau 1 thông báo headers.

- Requested URL. URL `typically` (thường) có chức năng như 1 tên của tài nguyên được yêu cầu, cùng với 1 phần chuỗi truy vấn chứa thông số mà client đi đến tài nguyên đó. Chuỗi truy vấn cho biết bởi dấu `?` trong URL. Ví dụ nội dung 1 thông số với tên là `uid` và giá trị là 129

- HTTP version là phiên bản đang được sử dụng. HTTP version chỉ thường sử dụng trên Internet la 1.0 và 1.1, và hầu hết các trình duyệt sử dụng version 1.1 bởi mặc định.

- 
