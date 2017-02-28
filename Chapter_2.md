# Ch2 Core Defense Mechanisms (Cơ chế phòng thủ cốt lõi)

## Core Defense Elements
+ Limiting user access to app's data and functionality

(Hạn chế người dùng truy cập đến các dữ liệu và chức năng của ứng dụng)

+ Limiting user input to prevent exploits that use malformed input

(Hạn chế đầu vào để ngăn chặn khai thác mà sử dụng đầu vào bị thay đổi )

+ Frustrating attackers with appropriate behavior when targeted

(làm nản lòng attacker với hành vi thích hợp khi nhắm mục tiêu)

+ Administrative monitoring and configuring the application

(quản trị giám sát và cấu hình ứng dụng)

defense: phòng thủ

mechanisms: cơ chế

prevent: ngăn chặn

malformed input: đầu vào bị thay đổi

frustrating: làm nản lòng

appropriate: thích hợp

behavior: hành vi

targeted: nhắm mục tiêu.

administrative: quản trị

monitoring: giám sát

configuring: cấu hình

## Handling User Access

- Authentication

(xác thực)

- Session management

(quản lý phiên)

- Access Control

(điểu khiển truy cập)

management: quản lý

authentication: xác thực

### Authentication 

- Username and password is most common method

(username và password là phương thức phổ biến nhất)

- Better: additional credentials and multistage login

(Tốt hơn: bổ sung thêm thông tin và login nhiều tầng)

- Best: client certificates, smartcards, challenge-response tokens

(Tốt nhất: thông tin client, thẻ thông minh, chứng thực bằng trả lời thách thức)

- Also: self-registration, account recovery, password change

(cũng tốt: tự bản thân đăng kí, phục hồi account, thay đổi password)

better: tốt hơn

credentials: giấy chứng nhận

multistage: nhiều tầng

smartcard: thẻ thông minh

challenge-response token: chứng thực bằng trả lời thách thức.

self-registration: tự đăng kí

account recovery: phục hồi tài khoản

### Common Login Problems 

- Predicatable usernames

- Password that can be guessed

(password đó có thể đc đoán)

- Defects in logic

(thiếu sót trong logic)

guessed: đoán

defects: thiếu sót 

### Session Management

- Session: a set of data structures that track the state of the user

(phiên: 1 tập hợp dữ liệu có cấu trúc để theo giỏi trạng thái của người dùng)

- A token identifies the session, usually a cookie

(1 dấu hiệu xác định session, thường là 1 cookie)

	-- Can also user hidden form fields or the URL query string
  
  (cũng có thể người dùng giữ các fields or chuỗi urL truy vấn)

- Session expire

(Kết thúc phiên)
track: theo giỏi

hidden: giấu

session expire: phiên hết hạn


### Common Session Problems

- Tokens are predictable (not random)

(mã thông báo là dự đoán đc )

- Tokens poorly handled, so an attacker can capture another user's token

(mã thông báo xử lí kém, vì thế 1 kẻ tấn công có thể bắt được mã thông báo của người dùng khác)

predictable: dự đoán đc

poorly handled: xử lí kém

capture: bắt

### Access Control

- Each request must be permitted or denied

(Mỗi yêu cầu cần được cho phép or từ chối)

- Multiple roles within application

(Nhiều vai trò trong application)

- Frequent logic errors and flawed assumptions

(thường xuyên lỗi logic và giả định sai lầm )

permitted: sự cho phép

denied: từ chối

roles: vai trò

frequent: thường xuyên

flawed assumptions: giả định sai lầm

### Handling User Input

- "Input Validation" is the most common solution

(đầu vào hợp lệ là giải pháp phổ biến nhất)

input validation: đầu vào hợp lệ

solution: giải pháp

