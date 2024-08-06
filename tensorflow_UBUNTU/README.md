# Setup Tensorflow GPU in WSL with visual studio code  
Những thao tác để sử dụng GPU với Tensorflow lớn hơn phiên bản 2.10  
### Đầu tiên bạn phải có GPU trên máy tính đã, ví dụ mình đang thực hiện là GPU NVIDIA QUARDO P2000, ngày thực hiện: 06/08/2024  
## Cài đặt `WSL2`  

1. Mở `Command Prompt` với `Run as administrator` và gõ lệnh sau: `wsl --install`
 
   <img src="https://github.com/user-attachments/assets/e09daa7c-e2e1-423c-987f-242de03eee9e">

3. Sau khi chạy xong thì khởi động lại thiết bị và mở `wsl` 

  <img src="https://github.com/user-attachments/assets/633e4226-7876-4758-8bb9-67f6ac9ba045">  

3. Thực hiện nhập tên `username` và `password`, lưu ý: password không hiển thị khi nhập, nó sẽ đen xì
4. Sau khi cài đặt tên và password thì mở `visual studio code` bằng lệnh `code .` để mwor thưu mục hiện tại


   <img src="https://github.com/user-attachments/assets/e7ecf970-777e-4f2b-9102-4e1155aa8c63">
   
6. Cài đặt extension `Remote Development` của Microsoft  

  <img src="https://github.com/user-attachments/assets/37603b0a-5f84-4d4e-9f59-a8407ca8bf71">
