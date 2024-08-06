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
