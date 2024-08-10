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

2. Mở `Command Prompt` và gõ lệnh `nvidia-smi` để xem đã nhận được GPU chưa, lưu ý 2 thông số là `Tên GPU` và `Phiên bản CUDA`

   <img src="https://github.com/user-attachments/assets/b189a53b-fde1-4c2c-a778-c43c9418632d">

3. Nếu muốn thay đổi phiên bản CUDA hay chưa có CUDA thì tải thêm `CUDA Tootkit`

   <img src="https://github.com/user-attachments/assets/41240a37-35aa-4671-ad2f-feb972c53973">


## Cài đặt `WSL2`  

1. Mở `Command Prompt` với `Run as administrator` và gõ lệnh sau: `wsl --install`

   <img src="https://github.com/user-attachments/assets/8fe30b77-ce7c-4ccd-93c2-f321a52cb4f8">

2. Sau khi chạy xong thì khởi động lại thiết bị và mở `wsl` 

  <img src="https://github.com/user-attachments/assets/633e4226-7876-4758-8bb9-67f6ac9ba045">  

3. Thực hiện nhập tên `username` và `password`, lưu ý: password không hiển thị khi nhập, nó sẽ đen xì  
   Chưa có ảnh, thêm ảnh vào đường dẫn bên dưới khi nào có cơ hội:
   <img src="">
4. Sau khi cài đặt tên và password thì mở `visual studio code` bằng lệnh `code .` để mở thư mục hiện tại

   <img src="https://github.com/user-attachments/assets/e7ecf970-777e-4f2b-9102-4e1155aa8c63">
   
5. Cài đặt extension `Remote Development` của Microsoft  

  <img src="https://github.com/user-attachments/assets/37603b0a-5f84-4d4e-9f59-a8407ca8bf71">

## Cài đặt Tensorflow GPU  
1. Tạo một thư mục trong `Linux`, ví dụ tạo thư mục `File Code` để lưu các project vào đây  

   <img src="https://github.com/user-attachments/assets/f30ae6bf-6e90-4f3c-aa89-7e77e78813cf">
1.1 Thêm thư mục vào `Vissual studio code` bằng lệnh `Add folder to workspace`

   <img src="https://github.com/user-attachments/assets/289fc812-bedc-4833-8a79-0c9ecce6f83b">

1.2 Mở `Terminal` và chạy các bước dưới đây vào `Terminal` 

   <img src="https://github.com/user-attachments/assets/46c6da1a-94e4-4614-82f4-05c57c9ae84a">

2. Chạy lệnh này `apt install python3.10-venv` để cài đặt thư viện môi trường ảo của Python

   <img src="https://github.com/user-attachments/assets/5842ecb4-d3a2-4424-9b0f-5d2c94a968e5">
   
3. Mở `Terrminal` và chạy lệnh sau `python3 -m venv .Tensorflow_project --prompt="tensorflow_gpu"` để tạo môi trường ảo  

   <img src="https://github.com/user-attachments/assets/a23e4eb4-cb7e-4009-ba48-e99f3453880d">

4. Sau khi chạy xong thì sẽ xuất hiện 1 thư mục mới có tên `.Tensorflow_project` với cấu trúc như sau:

   <img src="https://github.com/user-attachments/assets/67c6a35a-b717-4ccb-8f34-101de7fa555c">

5. Để kich hoạt môi trường ảo thì chạy lệnh `source .Tensorflow_project/bin/activate` và chạy thử với lệnh `pip list`

   <img src="https://github.com/user-attachments/assets/a23e4eb4-cb7e-4009-ba48-e99f3453880d">

6. Cài đặt `Tensorflow GPU` bằng câu lệnh `pip install tensorflow[and-cuda]`

   <img src="https://github.com/user-attachments/assets/1ea0afbf-f4ce-49f8-989f-cb20efbaad27">

7. Để chạy file python thì sử dụng câu lệnh `python path/to/file.py`

   <img src="https://github.com/user-attachments/assets/15b373ce-43d0-49df-8bdb-7bde43e0344b">

8. Kiểm tra xem GPU đã được chạy chưa, bằng cách chạy code và mở `Task Manager` ra vào mục `Performance`

   <img src="https://github.com/user-attachments/assets/d21a447c-29dd-441c-b94e-ee103772ba4a">
   
9. Khi đóng `Vissual studio code` thì sẽ hiện câu hỏi có muốn lưu workspace không thì nhất có, nhớ copy dường dẫn:
   Ví dụ: `/home/ducquan/File_Code.code-workspace`
   Từ lần sau mở thì chỉ cần mở `WSL` và gõ lệnh `cd /home/ducquan/File_Code` và gõ `code .` là sẽ vào workspace đã lưu

   <img src="https://github.com/user-attachments/assets/ab5f2bef-87cb-4dce-ae7d-4f28a77b8869">

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
   ```
   
   <img src="https://github.com/user-attachments/assets/a2f7a78f-e29a-4437-886a-9d366db3f1bd">
   
2. Nếu gặp lỗi `The virtual environment was not created successfully because ensurepip is not available.  On Debian/Ubuntu systems, you need to install the python3-venv package using the following command`
    Cần phải chạy lệnh này trước `apt install python3.10-venv` để cài đặt môi trường ảo cảu python 3.10

4. Cài đặt `OpenCV`:
   Đầu tiên chạy lệnh cài đặt opencv `pip install opencv-python`

   <img src="https://github.com/user-attachments/assets/eaf38075-0aeb-478b-9a54-91fd8f277a6b">

   Sau đó chạy 2 lệnh sau thì sử dụng bình thường
   ```
   sudo apt-get install libgl1-mesa-glx  
   sudo apt-get install xdg-utils
   ```

   <img src="https://github.com/user-attachments/assets/3de96705-da90-4f0c-b9b4-6d048ac5fa20">

5. `Matplotlib` không hiển thị hình ảnh khi chạy hàm `plt.show`  
    Cài đặt thêm thư viện `tkinter` do còn thiếu bằng lệnh `sudo apt-get install python3-tk`
   
   <img src="https://github.com/user-attachments/assets/0341559c-4e08-4a72-9fd3-ecaa63de1b3b">


 
