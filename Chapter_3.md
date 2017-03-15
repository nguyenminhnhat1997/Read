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

### Ở đây là 1 vài điểm quan tâm khác trong `sample` :mẫu: request:

- The `Referer` header được sử dụng để `indicate` (cho biết) urL, từ `originated`(nguồn gốc) request.

- The `User-Agent` header được sử dụng để cung cấp thông tin về trình duyệt hoặc client software mà `generated` tạo ra request.

- The `Host` header `specifies` (xác định) hostname mà `appeared` (xuất hiện) đầy đủ trong urL đang truy cập

- The `cookie` header được sử dụng để gửi thêm các thông số mà server cung cấp cho client

### HTTP Responses

<img src="http://sv1.upsieutoc.com/2017/03/08/cbcb.png"/>

- HTTP version đang được sử dụng

- Một số `status` (trạng thái) code `indicating` (cho biết) kết quả của request. 200 là trạng thái code phổ biến nhất, có nghĩa là request đã thành công và nguồn tài nguôn đó đang được trả về.

### 1 vài điểm chú ý khác của response

- The `Server` header chứa 1 biểu ngữ cho biết phần mềm mà web server đang sử dụng, và 1 vài chi tiết khác như, chẳn hạn như modules cài đặt, và hệ điều hành server. 

- The Set-Cookies header `issues` phát cho trình duyệt thêm 1 cookie, điều này được `mitted back` (nhắc lại) trong cookies header của các `subsequent`(tiếp theo) requests đến server

- The `Pragma` header `instructs`(hướng dẫn) trình duyệt không lưu trữ response trong cache của nó.

- The `Expires` header cho biết rằng nội dung response đã hết hạn trong quá khứ và những thứ đó sẽ k đc lưu cached -> load nội dung mới vào. Những chỉ thị là thường xuyên được cấp khi nội dung đông đang được trả lại để `ensure`(đảm bảo) rằng các trình duyệt `obtain`(có được) 1 phiên bản mới của nội dung trong `subsequent occasions` (những yêu cầu tiếp theo)

- Hầu hết tất cả  HTTP responses chứa 1 message body sau dòng headr

- The `Content-Type` header cho biết rằng thân của message này chứa 1 nội dung HTML

- The `Content-Length` header cho biết độ dài của message body theo bytes.

### HTTP Methods

Khi bạn tấn công vào web application, bạn sẽ được làm việc với hầu hết duy nhất với method phổ biến nhất được sử dụng: GET và POST. Bạn cần phải `aware` (nhận thức) 1 vài sự khác biệt `improtant` (quan trọng)  giữa những method, như chúng có thể `affect` (tác động) đến bảo mật của ứng dụng web nếu `overlooked` (bỏ qua)

The `GET` mà method được `designed`(thiết kế) để lấy tài nguyên. Nó có thể được sử dụng để gửi 1 thông số đến nguồn tài nguyên được yêu cầu trong chuỗi truy vấn trên URL. Điều này cho phép người dùng `bookmark`(đánh dấu) 1 URL cho 1 tài nguyên động mà họ có thể `reuse`(tái sử dụng). Toàn bộ URL có thể xuất hiện trong nhật kí của máy chủ. Không thích hợp để truyền những thông tin nhạy cảm trong chuỗi truy vấn.

- The `POST` được thiết kế để thực hiện các hành động

- thông số request có thể có trong URL và trong thân của 1 thông báo. 

- các thông số trong body không được lưu trong bookmarks hoặc nhật kí của server

- Một nơi tốt cho dữ liệu nhãy cảm

- `HEAD` function chỉ trả về header, không trả về thông báo message body

- Có thể sử dựng `HEAD` để kiểm tra nếu 1 nguồn tài nguyên là sẵn sàng để lấy nó.

- `TRACE` đươc thiết kế cho mục đích `diagnostic` (chuẩn đoán).

- `OPTIONS` hỏi server để báo cáo methods HTTP là có hiệu lực cho 1 nguồn tài nguyên `particular`(cụ thể).

-`PUT` cố gắng upload nguồn tài nguyên xác định lên server, sử dụng nội dung trong body của request

## URL 

- Là 1 định danh duy nhất cho 1 web site thông qua nó mà nguồn tài nguyên đc truy xuất.

- Format thường là như sau: protocol://hostname[port]/[path/]file[? param = value]

- HTTP port 80, HTTPS port 443.

## Rest

- Chỉ 1 urL có chứa các thông số của nó trong 1 đường dẫn urL chứ không phải 1 chuỗi truy vấn.

- *Ví dụ*: urL chứa chuỗi truy vấn: `seach?made=for&mode=pin`

- *Ví dụ*: urL chứa Rest-style : `seach/for/pin`

## HTTP Header

### General Header.

**Connection**: Đóng hoặc giữ kết nối TCP.

<img src="http://sv1.upsieutoc.com/2017/03/15/3432d0.png"/>

**Content-Encoding**: Xác định cụ thể kiểu mã hóa nào đc use cho nội dung đc chứa in messenge body, vd như gzip, đc use nén responses cho việc truyền đc nhanh hơn.

<img src="http://sv1.upsieutoc.com/2017/03/15/3b977c.png"/>

**Content-Length**: Xác định độ dài của messenge body tính theo `bytes`.

<img src="http://sv1.upsieutoc.com/2017/03/15/3e1568.png"/>

**Content-Type**: Xác định kiểu của nội dung đc chứa trong message body như text/html....

<img src="http://sv1.upsieutoc.com/2017/03/15/336aef.png"/>

**Transfer-Encoding**: Xác định bất kì mã hóa nào đã đc thực hiện trên message body -> tạo thuận lợi cho việc chuyển giao HTTP -> thường đc use để xác định chunked encoding.

<img src="http://sv1.upsieutoc.com/2017/03/15/3b4bfc.png"/>

### Request Headers

**Accept**: Nói với server những kiểu của nội dung mà client sẽ đc phép nhận, như images, office document...

<img src="http://sv1.upsieutoc.com/2017/03/15/3da338.png"/>

**Accept-Encoding**: Nói với server những kiểu nội dung mã hóa mà client sẽ đc phép nhận.

<img src="http://sv1.upsieutoc.com/2017/03/15/3e29c9.png"/>

**Authorization**: Gửi thông tin xác thực đến server cho 1 trong các loại xác thực đã đc cài đặt sẵn trên server.

<img src="http://sv1.upsieutoc.com/2017/03/15/3d9318.png"/>

**Cookie**: gửi 1 cookies đến server mà server đã ban hành trước đó#

<img src="http://sv1.upsieutoc.com/2017/03/15/3c341c.png"/>

**Host**: Xác định hostname mà xuất hiện đầy đủ trong URL đã đc requesed.

<img src="http://sv1.upsieutoc.com/2017/03/15/396afa.png"/>

 **If-Modified-Since**: Khi browser nhận đc request resource lần cuối cùng. Nếu resource là không thay đổi kể từ thời điểm đó, thì server có thể chỉ thị client sử dụng cache copy, sử dụng 1 response với trạng thái code 304
 
<img src="http://sv1.upsieutoc.com/2017/03/15/4ad756.png"/>

**If-None-Match**: Xác định 1 `entity tag` -> thẻ đó là dấu hiệu xác định nội dung của của message body, browser trình lên tentity tag đó, server sẽ cấp với response resource. Khi nó nhận được sau cùng server có thể sử dụng `entity tag` để xác định liệu browser có thể sử dụng thẻ đó để cached copy resource.

<img src="http://sv1.upsieutoc.com/2017/03/15/4703c3.png"/>

### Response Headers

**Access-Control-Allow-Origin**: Cho biết liệu resoure có thể đc lấu thông qua cross-domain Ajax requests.

<img src="http://sv1.upsieutoc.com/2017/03/15/30ae35.png"/>

**Cache-Control**: Chuyển các chỉ thị bộ nhớ đệm tới trình duyệt.

<img src="http://sv1.upsieutoc.com/2017/03/15/36948c.png"/>

**Etag**: Xác định 1 `entity tag` client có thể submit xác nhận request này trong tương lai cho những resource tương tự trong trong If-None-Match header để thông báo cho máy chủ phiên bản của resource mà browser hiện đang lưu giữ trong bộ nhớ cache.

<img src="http://sv1.upsieutoc.com/2017/03/15/3ce6a3.png"/>

**Expires**: Nói với browser trong bao lâu các nội dung của message body là hợp lệ. Browser có thể use chaped copy của resource này cho đến thời điểm này.

<img src="http://sv1.upsieutoc.com/2017/03/15/3d15e1.png"/>
****:
<img src=""/>
****:
<img src=""/>
****:
<img src=""/>
****:
<img src=""/>
****:


