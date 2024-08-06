# Setup Tensorflow GPU in WSL with visual studio code  
Những thao tác để sử dụng GPU với Tensorflow lớn hơn phiên bản 2.10  
### Đầu tiên bạn phải có GPU trên máy tính đã, ví dụ mình đang thực hiện là GPU NVIDIA QUADRO P2000, ngày thực hiện: 06/08/2024  
## Cài đặt `Python` và `Latest Microsoft Visual C++ Redistributable Version` từ trang chủ  
Python: 3.10.14  
Latest Microsoft Visual C++ Redistributable Version: 14.40.33810.0  

<img src="https://github.com/user-attachments/assets/a1d1f3df-51c1-4b62-8c9b-ad0168ff879d">

## Cài đặt trình điều khiển GPU  

1. Vào trang chủ `Nvidia Driver` tìm kiếm driver phù hợp với GPU và cài đặt  
   
   <img src="https://github.com/user-attachments/assets/3c56e43e-0690-4536-892e-5a5de7a4e6b2">

2. Mở `Command Prompt` và gõ lệnh `nvidia-smi` để xem đã nhận được GPU chưa, lưu ý 2 thông số là `Tên GPU` và `Phieen bản CUDA`

   <img src="https://github.com/user-attachments/assets/fc412811-4cc8-4037-a148-4b9556077c5e">

3. Nếu muốn thay đổi phiên bản CUDA hay chưa có CUDA thì tải thêm `CUDA Tootkit`

   <img src="https://github.com/user-attachments/assets/41240a37-35aa-4671-ad2f-feb972c53973">


## Cài đặt `WSL2`  

1. Mở `Command Prompt` với `Run as administrator` và gõ lệnh sau: `wsl --install`


   <img src="https://github.com/user-attachments/assets/b189a53b-fde1-4c2c-a778-c43c9418632d">

2. Sau khi chạy xong thì khởi động lại thiết bị và mở `wsl` 

  <img src="https://github.com/user-attachments/assets/633e4226-7876-4758-8bb9-67f6ac9ba045">  

3. Thực hiện nhập tên `username` và `password`, lưu ý: password không hiển thị khi nhập, nó sẽ đen xì  
   Chưa có ảnh, thêm ảnh vào đường dẫn bên dưới khi nào có cơ hội:
   <img src="">
4. Sau khi cài đặt tên và password thì mở `visual studio code` bằng lệnh `code .` để mwor thưu mục hiện tại


   <img src="https://github.com/user-attachments/assets/e7ecf970-777e-4f2b-9102-4e1155aa8c63">
   
5. Cài đặt extension `Remote Development` của Microsoft  

  <img src="https://github.com/user-attachments/assets/37603b0a-5f84-4d4e-9f59-a8407ca8bf71">


## Cài đặt Tensorflow GPU  
1. Tạo một thư mục trong `Linux` và `Add folder to workspace`  vào Visual studio code
2. Mở `Terrminal` và chạy lệnh sau `python3 -m venv .Tensorflow_project --prompt="tensorflow_gpu"` để tạo môi trường ảo  

   <img src="https://github.com/user-attachments/assets/80548539-79f2-409d-b815-968145c7002a">

   Nếu gặp lỗi `The virtual environment was not created successfully because ensurepip is not available.  On Debian/Ubuntu systems, you need to install the python3-venv package using the following command` thì cần phải chạy lệnh này trước `apt install python3.10-venv`



## Một số lỗi hay gặp  
1. ```
   E: Could not open lock file /var/lib/dpkg/lock-frontend - open (13: Permission denied)  
   E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), are you root?
   ```
   Có nghĩa là đang có một tiến trình khác đang sử dụng quyền Root, cần phải đặt lại quyền root như sau:
   Chạy 1 trong 2 lệnh sau:
   ```
   ps aux | grep -i apt  
   ps aux | grep -i dpkg
   ```
   Kết quả sẽ trả về nếu có thư mục đang nắm quyền `Root`

   <img src="https://github.com/user-attachments/assets/b3f91ca1-8949-49dd-bf77-db017b508ae1">

   Nếu có thì chạy lệnh `sudo kill -9 <PID>` với `PID>` là `mã tiến trình`  còn nếu không có thì xóa thủ công các tiến trình có thể đang bị kẹt như:
   ```
   sudo rm /var/lib/dpkg/lock-frontend  
   sudo rm /var/lib/dpkg/lock  
   sudo rm /var/cache/apt/archives/lock  
   sudo rm /var/lib/apt/lists/lock  
   ```
   Sau đó cấu hình lại và cập nhật rồi chạy lại câu lệnh mà mình mong muốn:
   ```
   sudo apt update
   sudo apt install python3.10-venv
   ```
   
   <img src="https://github.com/user-attachments/assets/a2f7a78f-e29a-4437-886a-9d366db3f1bd">
   
