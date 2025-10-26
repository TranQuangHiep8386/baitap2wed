# baitap2wed
wed2
1. Quá trình cài đặt phần mềm và thư viện
Trong quá trình làm, em đã cài đặt và cấu hình được đầy đủ các phần mềm cần thiết gồm Node.js, Node-RED, SQL Server và Apache24.
Ban đầu gặp một số lỗi như không truy cập được Node-RED, không mở được trang web hay lỗi “Access denied”, nhưng sau khi khởi động lại dịch vụ (restart Node-RED, Apache, SQL Server) và kiểm tra lại port 1880 và 80, em đã khắc phục được.
Em cũng đã hiểu cách cài đặt thêm thư viện node-red-node-mssql để Node-RED có thể kết nối đến cơ sở dữ liệu SQL Server.
Nhờ quá trình tự làm và sửa lỗi, em hiểu rõ hơn về cách các phần mềm này phối hợp với nhau trong hệ thống.

2. Cách sử dụng Node-RED để tạo API back-end
Em đã làm đúng theo quy trình:

Tạo flow1 trong Node-RED.

Thêm các node theo thứ tự: http in → function → MSSQL → http response.

Đặt URL /timkiem và test bằng đường dẫn http://localhost:1880/timkiem?q=thị.
Trong quá trình làm, em có gặp lỗi “không truy cập được web” và “không có bước đăng nhập”, nhưng sau khi kiểm tra lại cấu hình Node-RED và đăng nhập bằng tài khoản admin có mật khẩu, hệ thống đã chạy được.
Nhờ đó em hiểu rằng Node-RED cho phép tạo API trực quan bằng cách nối các node lại với nhau, và mỗi node có nhiệm vụ riêng (nhận request, xử lý dữ liệu, truy vấn SQL, trả kết quả về client).

3. Cách front-end tương tác với back-end
Em đã hiểu cách tạo giao diện gồm 3 file:

index.html để tạo form nhập thông tin,

tranvanhiep.js để xử lý dữ liệu và gửi request đến API Node-RED,

tranvanhiep.css để định dạng giao diện.
Em đã đặt đúng vị trí trong thư mục D:\Apache24\tranvanhiep để Apache có thể truy cập.
Front-end dùng JavaScript (fetch) để gửi yêu cầu đến API http://localhost:1880/timkiem và nhận dữ liệu JSON trả về từ Node-RED. Sau đó, kết quả được hiển thị lên trang web.
Nhờ vậy, em hiểu được quy trình tương tác giữa front-end và back-end:

Front-end (trình duyệt) → Node-RED API → SQL Server → Node-RED → hiển thị kết quả lên web.

4. Tổng kết
Qua bài này, em đã:

Biết cách cài đặt và cấu hình các thành phần của hệ thống web (SQL Server, Node-RED, Apache).

Hiểu được cách Node-RED hoạt động như một server back-end.

Biết kết nối front-end và back-end thông qua API, xử lý dữ liệu và hiển thị kết quả.

Học được cách tự phát hiện và khắc phục lỗi cấu hình, như lỗi không truy cập được web hoặc API không phản hồi.

Bài thực hành giúp em nắm vững quy trình triển khai một ứng dụng web cơ bản với đầy đủ ba tầng: giao diện – xử lý – dữ liệu.
