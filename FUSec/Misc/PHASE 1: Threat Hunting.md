# Challenge:
Bạn được giao nhiệm vụ săn tìm mã độc ẩn trong một máy window 10 chứa (nhiều) dữ liệu (quan trọng). Flag chính là tên file (không chứa path) của mẫu mã độc bạn cần tìm. Nội dung của flag không chứa kí tự viết hoa. Dưới đây là link tải file máy ảo (có thể bỏ vào VMWARE hay Virtualbox để chạy). Cần giải bài này trước khi giải Phase 2: Malware analysis 
Mật khẩu vào máy ảo là "123": https://drive.google.com/file/d/16ntnmYhpmU67uPMcxB_p2OcRRPCqjSUC/view?usp=sharing

author: EaZyq

# Solution:
Đề bài cho một file `.ova` để chúng ta có thể phân tích, import file này và mở bằng Oracle VM VirtualBox:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/58c2a5ce-45a3-491b-8dcc-cc293a27a8be)

Có thể thấy được sau khi được khởi động thì có rất nhiều chương trình được khởi động cùng, làm mình nghĩ tới liệu malware có Persistence giống như các chương trình này không?
Truy ngược qua các đường dẫn thư mục tới đường dẫn Registry theo tài liệu MITRE ATT&CK về Persistence: https://attack.mitre.org/tactics/TA0003/ để tìm thư mục chứa các chương trình nhằm mục đích autorun, tìm thấy thư mục tại đường dẫn `C:\Users\hunter\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup`:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/b0e7aa1a-8aec-4fe9-940f-1fb24de6edf7)

Trong các chương trình được liệt kê thì có file `.mp4` khá đáng nghi vì mặc dù nằm trong đường dẫn nhưng lại không được kích hoạt khi máy được khởi động, mình kiểm tra thử bằng VirusTotal thì file này được xác minh là không độc hại:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/049ee4d9-4b8b-4d1f-955f-85d3e7b1ba0e)

Ngoài ra bên ngoài Desktop còn có một thư mục có chứa một bức ảnh nhưng sau khi kiểm tra thì không phát hiện bất thường:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/16204bd5-c36b-4e15-b2fc-87b14fd49209)

Có một điểm đáng chú ý ở ngoài Desktop là có sẵn thư mục Sysinternals Suite, trong thư mục này có phần mềm là `Autoruns` dùng để hiển thị các chương trình được cấu hình để chạy khi system bootup hoặc login, sau khi chạy thử phần mềm xem có chương trình đáng ngờ nào không thì mình tìm thấy một service có tên là `RedApple`:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/61a08809-bacd-49e4-827b-b8443d3e7134)

Service này không có gì để verify, thêm vào đó có tên tiến trình là `scvhost.exe`, tên tương tự với `svchost.exe`, là một tiến trình hệ thống của Windows, càng có cơ sở chứng minh đây là malware cần tìm

Flag: `FUSec{scvhost.exe}`
