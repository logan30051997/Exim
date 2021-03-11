# Khái niệm Mail Server

## 1. Mail Server là gì

Mail Server là một máy chủ thư điện tử dùng để gửi và nhận thư điện tử (Email).

Các Email Server thực chất là một Server vật lý hoặc là một Server đám mây được cấu hình thành một server gửi và nhận thư điện tử. Nó cũng có đầy đủ các thông số như một Server bình thường

Email client (từ kỹ thuật là Mail User Agent (MUA), là một phần mềm máy tính được dùng để truy cập và quản lý email của người dùng


## 2. Phân loại

- Outgoing Email Server là gì? 
Outgoing Mail Server hay Mail Server gửi đi sử dụng giao thức SMTP (Simple Mail Transfer Protocol). Đây là giao thức dịch chuyển mail đơn giản được dùng để liên lạc với server từ xa. Đồng thời cho phép gửi nhiều thư cùng một lúc tới các server khác nhau.
Port 25/465

- Incoming Email Server là gì? 
Giao thức này hay còn được biết đến dưới 2 hình thức: 

POP3 (Post Office Protocol): chuyển email tới lưu ở máy tính chứa Mail Client, thường là nội bộ máy tính của người dùng thông qua một ứng dụng email như Outlook, Mac Mail, Windows Mail… 
Port 110/995

IMAP (Internet Message Access Protocol): là phương thức phức tạp hơn cho phép nhiều client cùng lúc kết nối tới một Mailbox. Email từ Mailbox sẽ được sao chép tới máy client và bản gốc của Email vẫn sẽ được lưu trên Mail Server.
Port 143/993

## 3. Hoạt động

<img src="https://longvan.net/hinhanh/tintuc/cac-thuat-ngu-ve-mail-server.jpg">


**Bước 1: Kết nối với SMTP server**

Khi bạn gửi email, nền tảng hoặc dịch vụ email, chẳng hạn như G Suite, Exchange, Office 365 và Zimbra, sẽ kết nối với SMTP server. SMTP server đó được kết nối với domain của bạn và có địa chỉ cụ thể, chẳng hạn như smtp.gatefy.com hoặc smtp.example.com.

Ở giai đoạn này, dịch vụ email sẽ cung cấp cho SMTP server một số thông tin quan trọng, chẳng hạn như địa chỉ email của bạn, nội dung thư và địa chỉ email của người nhận.

**Bước 2: Xử lý domain của người nhận**

Bây giờ, SMTP server sẽ xác định và xử lý địa chỉ email của người nhận. Nếu bạn đang gửi email cho người khác trong công ty của mình, tức là đến cùng một domain, mail sẽ được chuyển hướng đến IMAP hoặc POP3 server.

Nếu bạn đang gửi mail cho một công ty khác, SMTP server sẽ cần giao tiếp với email server của công ty đó.

**Bước 3: Xác định IP của người nhận**

Ở giai đoạn này, SMTP server của bạn sẽ cần kết nối với DNS (Domain Name System) để tìm máy chủ của người nhận.

DNS hoạt động giống như một hệ thống dịch thuật. Về cơ bản, nó sẽ giúp chuyển domain của người nhận thành địa chỉ IP.

SMTP cần IP để thực hiện chức năng của nó một cách chính xác, do đó có thể chuyển thư trực tiếp đến máy chủ của người nhận.

**Bước 4: Chuyển email**

Tuy nhiên, không phải mọi thứ đều đơn giản như vẻ bề ngoài. Nói chung, email của bạn sẽ đi qua các SMTP server không liên quan khác nhau cho đến khi nó đến SMTP server của người nhận.

Khi nhận được email, SMTP server của người nhận sẽ kiểm tra thư và sau đó chuyển nó đến MAP hoặc POP3 server. Sau đó, email đi vào hàng đợi, được xử lý cho đến khi người nhận có thể truy cập. Sau đó, người nhận có thể đọc email.

Bây giờ, bạn đã biết những điều cơ bản về mail server đến và đi. Tuy nhiên, còn một thứ rất quan trọng cần đề cập. Đó là bảo mật email.

## 4. Giải pháp

Thông thường, những cá nhân hay doanh nghiệp yêu cầu một lương lớn dung lượng hơn bình thường sẽ đầu tư riêng Mail Server.

## 5. Thuật ngữ

- *TLS Mail Server là gì?*

TLS là bảo mật tầng truyền tải (Transport Layer Security). TLS hoạt động cùng với tầng ổ bảo mật SHL (Secure Sockets Layer). Mục đích chính cung cấp phương thức vận chuyển mã hoá cho đăng nhập được chứng thực của SASL.

- *SASL Mail Server là gì?*

SASL là lớp xác thực và bảo mật đơn giản (Simple Authentication and Security Layer). Để xác thực người dùng. SASL thực hiện xác thực, sau đó TLS cung cấp vận chuyển mã hoá dữ liệu xác thực.

- *Webmail là gì?*

Webmail là email trên nền website. Một số webmail mà các bạn có thường thấy như hotmail, gmail, yahoo mail. Webmail cho phép người dùng truy cập email bất cứ lúc nào.

- *SMTP-IN Queue là gì?*

Trước khi phân tán thư đến các Local queue hoặc Remote Queue, giao thức SMTP sẽ làm một thao tác sao lưu toàn bộ thư điện tử gửi đi từ email server của doanh nghiệp ở SMTP-IN Queue. Nói cách khác, SMTP-IN Queue chính là kho lưu trữ thông tin thư từ trước khi được gửi đi.

- *Local Queue là gì?*

Sau khi tiếp nhận thông tin thư từ, hệ thống sẽ tự động điều phối phân loại và xếp thư từ theo thứ tự ngay hàng thẳng lối trước khi chuyến vào hộp thư của người nhận. Việc xếp hàng các bức thư chính là Local Queue.

Để tăng cường khả năng bảo mật và giữ an toàn cho hệ thống email server, trước khi thư được gửi đến người dùng, local queue và remote queue sẽ tiến hành quét virut. Sau đó kiểm tra spam để chắc chắn về chất lượng thư gửi đi. Tránh trường hợp mail server bị các Blacklist liệt vào danh sách IP spam.

- *Local Mailboxes là gì?*

Local Mailboxes là hộp thư của các account có đăng kí tài khoản mail server của công ty.

- *Email Authentication là gì?*

Email Authentication là tính năng xác nhận danh tính của các user khi truy cập vào hộp thư email. Tính năng này giúp bạn bảo mật thông tin thư từ của chính mình. Nói cách khác Alternate Email là một dạng email dự phòng. Khi quên mật khẩu của mail server, bạn có thể sử dụng email này để giúp bạn lấy lại mật khẩu một cách nhanh chóng.

- *Mail Exchanger Record (MX) là gì?*

MX record có nhiệm vụ là chỉ đường cho email đi đến mail server của bạn. MX record thường đi kèm theo một A record sẽ trỏ về địa chỉ IP của mail server. Một thông số pref có giá trị số để chỉ ra mức độ ưu tiên của các mail server. Giá trị pref càng nhỏ thì mức độ ưu tiên càng cao.
