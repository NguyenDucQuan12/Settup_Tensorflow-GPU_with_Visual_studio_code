# Setup Tensorflow GPU in WSL with visual studio code  
Những thao tác để sử dụng GPU với Tensorflow lớn hơn phiên bản 2.10  
### Đầu tiên bạn phải có GPU trên máy tính đã, ví dụ mình đang thực hiện là GPU NVIDIA QUARDO P2000, ngày thực hiện: 06/08/2024  
## Cài đặt `WSL2`  

1. Mở `Command Prompt` với `Run as administrator` và gõ lệnh sau: `wsl --install`
2. Sau khi chạy xong thì khởi động lại thiết bị và mở `wsl` 

  <img src="https://github.com/user-attachments/assets/633e4226-7876-4758-8bb9-67f6ac9ba045">  

3. Thực hiện nhập tên `username` và `password`, lưu ý: password không hiển thị khi nhập, nó sẽ đen xì
4. Sau khi cài đặt tên và password thì mở `visual studio code` bằng lệnh `code .` để mwor thưu mục hiện tại
5. Cài đặt extension `Remote Development` của Microsoft  
