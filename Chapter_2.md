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

### Types of Input

- Arbitrary text, like blog posts

- Cookies

- Hidden form fields

- Parameters

- HTTP header fields, like User-Agent

Arbitrary text: văn bản tùy ý

### "Reject Known Bad"

(biết từ chối bad)

- Also called "blacklisting"

(cũng được gọi là "danh sách đen")

	-- Least effective method
	
	(phương thức ít hiệu quả)
	
	-- Difficult to identify all bad inputs
	
	(khó xác định tất cả các đầu vào xấu)

reject: từ chối

blacklisting: danh sách đen

least effective method: phương thức hiệu quả nhất

### "Accept Known Good"

(Biết chấp nhận cái tốt)

- Also called "whitelisting"

(cũng đc gọi là dánh sách trắng)

- Most effective technique, where feasible

(kĩ thuật hiệu quả nhất, nếu khả thi)

- However, sometimes you can't do it

(Tuy nhiên, 1 vài thứ bạn k thể làm được)

	-- Human names really contain apostrophes, so you can't filter them out
	
	(Tên người thực sự chứa dấu nháy, vì thế bạn không thể lọc chúng ra )

whitelisting: danh sách trắng.

effective: hiệu quả

technique: kỹ thuật

where feasible: nếu khả thi

apostrophes: dấu nháy

filter: lọc 

### Sanitization 

- Render dangerous input harmless

(trả lại đầu vào nguy hiểm vô hại)

- HTML-Encoding: Space becomes %20, etc.

- Difficult if several kinds of data may be present within an item of input

(khó khăn nếu 1 số kiểu của dữ liệu có thể có mặt trong 1 mục của đầu vào)

	-- Boundary validation is better (four slides ahead)
	
	(xác nhận ranh giới là tốt nhất (4 slides trên) )

sanitization: cải thiện

render: trả lại

harmless: vô hại

several kinds: 1 số loại

present: có mặt

item: mục

boundary: ranh giới

validation: xác nhận

### Safe Data Handling

(xử lí dữ liệu an toàn)

- Write code that can't be fooled by malicious data

(viết code mà thông thể bị lừa bởi dữ liệu độc hại)

	-- SQL parameterized queries

	-- Don't pass user input to an OS command line

- Effective when it can be applied

fooled: lừa

malicious: độc hại

command line: dòng lệnh

effective: có kết quả

### Semantic Checks

- Some malicious input is identical to valid input

(Một vài đầu vào độc hại là giống hệt với đầu vào hợp lệ)

	-- Such as changing an account number to another customer's number
	
	(chẳn hạn như việc thay đổi 1 số account đến số khách hàng khác)

- Data must be validated in context

(Dữ liệu cần phải được xác nhận trong bối cảnh)

	-- Does this account number being to the currently logged-in user ?
	
	(có số tài khoản này là để cho người dùng hiện tại đang đăng nhập)

semantic: ngữ nghĩa

identical: giống hệt

valid: hợp lệ

customer: khách hàng

validated: xác nhận.

currently: hiện tại.

### Difficulties with Simple Input Validation

(Những khó khăn với xác nhận đầu vào đơn giản)

- Data coming from user is "bad" or "untrusted"

(dữ liệu phổ biến từ phía người dùng là xấu or không tin cậy)

- The server-side app is "good" and trusted

(ứng dụng bên phía server-side là tốt và tin cậy)

	-- Many different types of input with different filtering requirements
	
	(Nhiều kiểu khác nhau của đầu vào với nhiều yêu cầu lọc khác nhau)

	-- Apps may chain several processing steps together
	
	(Ứng dụng có thể 1 loạt 1 các bước 1 vài quá trình cùng nhau )

		--- Data may be harmless at one stage, but be transformed into harmful data at another stage
		
		(Data có thể vô hại trong 1 giai đoạn, nhưng có thể thay đổi thành dữ liệu có hại trong 1 giai đoạn khác)

untrusted: không tin cậy

server-side: phía máy chủ

requirements: yêu cầu

chain: 1 loạt

processing: quá trình

stage: giai đoạn

harmless: vô hại

transformed: biến đổi

harmful: có hại


### Boundary Validation

- Trust boundary

(ranh giới tin cậy)

	-- Divides a trusted zone from an untrusted zone
	
	(phân chia 1 vùng tin cậy từ 1 vùng không tin cậy)

- Clean data that passes a boundary

(dữ liệu sạch đó chuyển đến 1 vùng ranh giới)

	-- Such as form the user into an application
	
	(chẳng hạn như hình thức người dùng đến 1 ứng dụng)
	
- Each component treats its input as potentially malicious

(mỗi thành phần xử lí đầu vào đó như có khả năng đôc hại)

- Data validation performed at each trust boundary

(Xác nhận dữ liệu biểu thị đến 1 vùng tin cậy)

	-- Not just between client and server
	
	(không chỉ giữa client và server)
	
divides: phân chia

boundary: giới hạn

zone: vùng

clean data: dữ liệu sạch

passes: vượt qua

component: thành phần

treats: xử lí

potentially: có khả năng

performed: thực hiện

### Boundary Validation Example

- 1 App gets login: username and password

- Allows only good characters, limits length, removes known attack signatures

- 2 App performs a SQL query to verify credentials

- Escape dangerous characters

- 3 Login succeeds; app passes data from user profile to a SOAP service

- XML metacharacters are encoded to block SOAP injection

- 4 App display user's account information back to the user's browser

- user-supplied data is HTML-encoded to block XSS

attack signatures: dấu hiệu tấn công

verify: xác minh

credentials: thông tin

escape: thoát khỏi

profile: người dùng



### Filtering Problems

- App removes this string:
	
	`-- <script>`

- So attacker sends this

	-- `<scr<script>ipt>`
	

### Multistep Validation 

- App first removes

	`../`

- Then removes

	`..\`

- Attacker sends

	`....\/`
	
### Canonicalization

- App gets URL-encoded data from Web browser

	-- Apostrophe (') is %27

	-- Percent(%) is %25

- To block apostrophes, app filters %27

- But URL is decoded twice by mistake

	-- %25%27 becomes %27 becomes apostrophe	

Canonicalization: quá trình chuẩn hóa

### Handling Attackers

- Handling errors

(xử lí lỗi)

- Maintaining audit logs

(duy trùy cửa sổ kiểm soát)

- Alerting administrators

(cảnh báo đến quản trị viên)

- Reacting to attacks

(phản ứng lại với kẻ tấn công)

maintaining: duy trì

audit logs: cửa sổ kiểm soát

alerting: cảnh báo

administrators: quản trị viên

reacting: phản ứng lại


#### Handling Errors

- Show appropriate error messages

(hiển thị các thông báo lỗi thích hợp)

- Unhanded errors lead to overly-informative

(buông lỗi dẫn đến quá tải thông tin)

appropriate: thích hợp

unhanded: buông ra

lead: dẫn đến

overly-informative: quá tải thông tin

#### Audit Logs

- Authentication events: login success and failure, change of password

- Key transactions, such as credit card payments

- Access attempts that are blocked by access control mechanisms

- Requests containing known attack strings

- For high security, log every client request in full

#### Protecting Logs

- Logs should contain time, IP addresses, and username
	-- May contain cookies and other sensitive data

- Attackers will try to erase and/or read logs

- Log must be protected

	-- Place on an autonomous system that only accepts update messages

	-- Flush logs to write-once media
	
	
