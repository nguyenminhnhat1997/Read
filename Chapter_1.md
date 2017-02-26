# Chapter 1 : WEB application (In)security.

- There is no **doubt** that web application security is a **current** and newsworthy 

subject.

 **doubt**: nghi ngờ.

 **current**: phổ biến.

> Không có gì nghi nghờ rằng bảo mật ứng dụng  web là phổ biến và là vấn đề đáng đăng lên báo.

- For all **concerned**, the **stakes** are high: for **businesses** that **derive** **increas-
ing** revenue from Internet commerce, for users who trust web applications with 
sensitive information, and for **criminals** who can make big money by stealing 
**payment details** or **compromising** bank accounts. **Reputation** plays a `critical role`.

 **concerned**: liên quan.

 **stakes**: mối đe dọa.

 **businesses**: công ty, doanh nghiệp.

 **derive**: xuất phát.

 **increasing**: ngày càng tăng.

 **revenue**: lơi ích, lợi nhuận.

 **criminal**: tội phạm.

 **stealing**: đánh cắp.

 **payment details**: cách thanh toán, chi tiêu chi tiết.

 **compromising**: xâm nhập.

 **Reputation**: danh tiếng.

 **critical role**: vai trò quan trọng.

> đối với những tất cả vấn đề liên quan, các mối đe dọa là cao: đối vs những công ty, doanh nghiệp mà `xuất phát` từ việc `ngày càng tăng` các lợi ích từ kinh doang buôn bán qua Internet, cho những người dùng tin tưởng các ứng dụng web với những thông tin nhạy cảm và tội phạm kẻ có thể kiếm số tiền lớn bằng việc ăn cắp các tài liệu thanh toán, chi tiêu chi tiết hoặc xâm nhập vào tài khoản ngân hàng. Uy tín, danh tiếng đóng vai trò quan trọng.

Few people want to do business with an `insecure` website, so few `organizations` 
want to `disclose` details about their own security vulnerabilities or `breaches`. 

- **insecure**: không an toàn.

- **organizations**: tổ chức.

- **disclose**: tiết lộ 

- **breaches**: vi phạm.

> 1 vài người muốn làm kinh doanh, buôn bán với 1 website không an toàn, vì thế 1 vài tổ chức muốn tiết lỗ chi tiết về những lỗ hổng bảo mật của họ hoặc những vi phạm.

`Hence`, it is not a `trivial` task to `obtain` `reliable` information about the `state of` 
web application security today.

- **hence**: vì thế do đó. (vì thế mà hen)

- **trivial**: không quan trọng (bạn trí không quan trọng đối với bạn vial)

- **obtain**: đạt được (bạn ốp đạt được bạn tình).

- **reliable**: tin cậy (rẻ vào nhà bạn li, able tin cậy đó)

- **state of**: trạng thái (trạng thái cái tay của mình of rồi)

>  Vì thế, đó không phải là 1 nhiệm vụ quan trọng để đạt được thông tin tin cậy về trạng thái về bảo mật ứng dụng web ngày nay.

This chapter takes a `brief` look at how web applications have `evolved` and the 
many `benefits` they `provide`.

- **brief**: ngắn (bờ ríp ngắn )

- **evolved**: phát triển (e vô là phát triển về d)

- **benefits**: lợi ích (bé nè fit kiểm tra lại lợi ích cho a)

- **provide**: cung cấp (pro vì cung cấp để chơi)

> chương này có 1 cái nhìn ngắn gọn làm cách nào ứng dụng web  có được phát triển và nhiều lợi ích chúng chung cấp.

We present some `metrics` about vulnerabilities in current web applications, `drawn` from the authors’ `direct` experience, `demonstrating` that the `majority` of applications are far from `secure`.

- metric: số liệu (me của trí có số liệu rõ ràng)

- drawn: rút ra (được rút ra từ wn)

- direct : trực tiếp (đi rẽ trực tiếp thì ctay )

- demonstrating: giải thích, chứng minh 

- majority: đa số (mà giờ đa số đều rity hết)

- secure: an toàn (sẽ cứ rẽ mặc dù không an toàn)

> Chúng tôi trình bày 1 vài số liệu về lổ hổng trong ứng dụng phép ngày nay, rút ra trực  tiếp từ những kinh nghiệm của tác giả, giải thích chứng minh rằng đa số ứng dụng web là xa với sự an toàn.

We `describe` the core security problem facing web applications — that users can `supply` `arbitrary` input — and the `various` `factors` that `contribute` to their `weak` security `posture`. 

- describe: mô tả  (để scri bé mô ta cho biết)

- supply: cung cấp (súp của ply cung cấp nhiều vitamin)

- arbitrary: tùy ý (a r á dãy bit tùy ý ra kìa )

- various: nhiều cái khác (vá nhiều cái khác nhau tôi ous rồi)

- factors: nhân tố (FA là 1 nhân tố to lớn :D )

- contribute: góp phần (con của trí góp phần cho 1 bute đó )

- weak: điểm yếu (chúng ta có điểm yếu là ak đó )

- posture: tình hình (tình hình của po sẽ tự rẻ vào nhà trinh )

> Chúng tôi mô tả vấn để cốt lỗi bảo mật mà ứng dụng web đang đối mặt - mà người dùng có thể cung cấp đầu vào tùy ý - và các nhân tố khác nhau mà góp phần vào tình hình an ninh yếu kém của họ (các website bảo mật kém, khi người dùng nhập vào -> lộ thông tin)

Finally, we describe the `latest trends` in web application security and how these 
may be `expected` to develop in the near future.

- latest trends: những xu hướng mới nhất (là test trên những xu hướng mới nhất)

- expect: kỳ vọng (e x kỳ vọng anh pect trở về)

> cuối cùng, chúng tôi mô tả những xu hướng mới nhất trong bảo mật ứng dụng web và làm cách nào để những điều đó có thể được kì vọng đêr phát triển trong tương lai gần.


Web Appli cation 

E-commerce, Social networks, Online banking, etc.

- E-commerce: thương mại điện tử (e ăn cơm bên thương mại điện tử á)

- Social networks: Mạng xã hội.

- Online banking: ngân hàng trực tuyến.

`Fundamental` security problem:

Users can supply arbitrary input

`Malicious` input can `compromise` the site

- fundamental: cơ bản (fun->vui đã, là cơ bản khi vui men có thể tal đó)

- malicious: nguy hiểm, hiểm độc (má của li hiểm độc suy ra ci -> ous=out)

- compromise: xâm hại (cơm xâm hại đến những ai pro như mi sẽ die)
> Vấn đề cơ bản bản về security:
Người dùng có thể cung cấp đầu vào tùy ý 
Những đầu vào nguy hiểm có thể xâm hại tới web site

information `flows` one-way

Users don't log in, shop, or submit comments

An attacker who `exploits` `flaws` in the web server software can 

	steal data on the web server (usually only `public` data anyway)

	`Deface` the site 

- flows: luồng

- exploits: khai thác 

- flaws: lỗ hổng.

- public: chung 

- deface: làm cho xấu đi, mất đi 

> Luồng thông tin theo 1 đường.
Người dùng không thể đăng nhập, shop, or gửi 1 coment

1 acttacker người khai thác lỗ hỏng trong web server software có thể.
Đánh cắp dữ liệu trên web server (thông thường bất kì dữ liệu public nào)
Làm cho 1 web site xấu đi, mất đi hình tượng.

- Two-way information flow

- Users log in, submit content

- Content `dynamically` `generated` and `tailored` for each user

- Much data is sensitive and `private` (e.g passwords)

- Most apps developed `in-house`

- Developers often `naive` about security.

content dynamically: nội dung động

generated: được tạo ra

tailored: phù hợp 

private: riêng tư, cá nhân

naive: ít hiểu biết, ngây thơ.

> Luồng thông tin 2 chiều
Người dùng đăng nhập gửi nội dung
Nội dung động được tạo ra và phù hợp cho mỗi người dùng, nhiều dữ liệu là nhạy cảm và riêng tư, nhiều ứng dụng đc phát triển trong nhà, các nhà phát triển thường ngây thơ về security.

`Benefits` of Web Apps
HTTP is lightweight and connectionless
	Resilient in event of communications errors

	Can be proxied and tunneled over other protocols

Web browsers run on many devices, highly functional, easy to use

Many platforms and development tools avaiable

lightweight:
connectionless
resilient
event
communication:
proxied
tunneled
devices
highly functinal:
platforms
development
avaiable




