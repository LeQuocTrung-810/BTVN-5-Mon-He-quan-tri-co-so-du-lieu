# BTVN-5-Mon-He-quan-tri-co-so-du-lieu
Lê Quốc Trung k225480106065  K58KTP.K01
SUBJECT: Trigger on mssql

A. Trình bày lại đầu bài của đồ án PT&TKHT:
1. Mô tả bài toán của đồ án PT&TKHT, 
   đưa ra yêu cầu của bài toán đó
2. Cơ sở dữ liệu của Đồ án PT&TKHT :
   Có database với các bảng dữ liệu cần thiết (3nf),
   Các bảng này đã có PK, FK, CK cần thiết
 
B. Nội dung Bài tập 05:
1. Dựa trên cơ sở là csdl của Đồ án
2. Tìm cách bổ xung thêm 1 (hoặc vài) trường phi chuẩn
   (là trường tính toán đc, nhưng thêm vào thì ok hơn,
    ok hơn theo 1 logic nào đó, vd ok hơn về speed)
   => Nêu rõ logic này!
3. Viết trigger cho 1 bảng nào đó, 
   mà có sử dụng trường phi chuẩn này,
   nhằm đạt được 1 vài mục tiêu nào đó.
   => Nêu rõ các mục tiêu 
4. Nhập dữ liệu có kiểm soát, 
   nhằm để test sự hiệu quả của việc trigger auto run.
5. Kết luận về Trigger đã giúp gì cho đồ án của em.

HƯỚNG DẪN CÁCH LÀM:

Hướng dẫn làm phần A: 
 - Chỉ cần nêu ra y/c của đồ án.
 - Không cần chụp quá trình làm ra db, tables.
 - Chỉ cần đưa ra db gồm các bảng nào,
   mỗi bảng có các trường nào, kiểu dữ liệu nào,
   và pk, fk, ck của các bảng.

Hướng dẫn làm phần B:
1. Sv tạo repo mới trên github, cho phép truy cập public.
2. Tạo file Readme.md, đầu file để thông tin cá nhân sv.
3. Tiếp theo đưa phần A vào file Reame.md .
3. Các thao tác làm trên csdl bằng phần mềm ssms.
4. Chụp ảnh màn hình quá trình làm.
5. Paste ngay vào Readme.md, 
   rồi gõ mô tả ảnh này làm gì, nhập gì, hay đạt được điều gì...
6. Có thể thêm những nhận xét hoặc kết luận
   cho việc bản thân đã hiểu rõ thêm về 1 vấn đề gì đó.
7. Lặp lại các step 4 5 6 cho đến khi hoàn thành yêu cầu của phần B.
8. Xuất các file sql chứa cấu trúc và data, up lên cùng repo.
9. Link đến repo cần mở được trực tiếp nội dung, 
   Paste link này vào file excel online ghim trên nhóm.
   Thầy sẽ dùng tool để check các link này.

DEADLINE: 23H59:59 NGÀY 23/04/2025

p/s:
 - Sv được phép tham khảo mọi nguồn, nhưng phải tự làm lại.
 - Đọc thêm nội quy học tập để biết các chế tài.
 - Đã đến lúc khẳng định bản thân và toả sáng!
 - Chỗ nào vướng mắc cứ share lên nhóm để cùng tháo gỡ.  
# Mô tả và yêu cầu của bài toán  
## Mô tả bài toán PT&TKHT quản lý chung cư Thái Nguyên Tower  
Ban quản lý chung cư Thái Nguyên Tower hiện đang gặp khó khăn trong việc quản lý thông tin cư dân, hợp đồng, căn hộ và tài sản cá nhân do phương pháp thủ công không còn hiệu quả. Với nhu cầu hiện đại hóa công tác quản lý, cần xây dựng một hệ thống thông tin giúp quản lý nhân khẩu cư trú tại chung cư một cách chính xác, hiệu quả và thuận tiện.  
Hệ thống này sẽ được thiết kế để lưu trữ, cập nhật và truy xuất dữ liệu nhanh chóng, sử dụng SQL để nhập dữ liệu, thực hiện các thao tác thêm, sửa, xóa và truy vấn thông tin từ cơ sở dữ liệu quan hệ.  
## Yêu cầu của bài toán  
- Các chức năng quản lý (quản lý nhân khẩu, thông tin liên lạc, thông tin hợp đồng, thông tin tài sản cá nhân).  
- Thiết kế hệ thống trên nền tảng SSMS
- Sử dụng SSMS và ngôn ngữ SQL để nhập dữ liệu và tương tác với hệ thống.
# Bài làm
## Tạo cơ sở dữ liệu gồm các bảng:
+ NhanKhau  
![image](https://github.com/user-attachments/assets/5f3adf3b-4bb3-481e-8910-f69a6969035d)  
+ HopDong  
![image](https://github.com/user-attachments/assets/d927227d-9605-4803-84ff-b582b8f96134)  
+ CanHo  
![image](https://github.com/user-attachments/assets/ce5c51eb-425f-41ca-aef8-f40c1c9a7d42)  
+ TienIch  
![image](https://github.com/user-attachments/assets/ece8d586-9cbf-4b71-8c41-f6cd18d3e569)  
+ CanHo_TienIch  
![image](https://github.com/user-attachments/assets/64844996-94cb-4a65-bed8-c1b4c17f8bd1)  
+ CuTru  
![image](https://github.com/user-attachments/assets/21ba7295-4f9e-47bc-8436-a38d245771b6)  
+ TamTruTamVang  
![image](https://github.com/user-attachments/assets/cd266237-7180-4745-9274-6ba97bd4e6a9)  
+ TaiSanCaNhan  
![image](https://github.com/user-attachments/assets/98b1ab7b-df55-438e-b69e-0a90493f796c)  
+ Các khóa chính đã được thể hiện trên ảnh của các bảng trên, dưới đây là liên kết giữa các khóa ngoại và khóa chính:
![image](https://github.com/user-attachments/assets/b98755ce-d951-46e4-8768-85e0279e0a76)  
![image](https://github.com/user-attachments/assets/1e4e3340-e671-4393-b69e-be6313c34169)  
![image](https://github.com/user-attachments/assets/15ba0ea5-7d43-42cd-90d3-6caa01b133fc)  
![image](https://github.com/user-attachments/assets/e55fe0d0-9ab5-4af4-8975-1e3e7f1acb8e)  
![image](https://github.com/user-attachments/assets/77ebdf9b-17f6-4ba5-8d15-1bb81cc584b5)  
![image](https://github.com/user-attachments/assets/be8b24f4-f2c0-4406-bad4-a93930052013)  
![image](https://github.com/user-attachments/assets/b8a132e0-60e7-413e-920c-3725393dda78)  
![image](https://github.com/user-attachments/assets/5b6d45aa-8eac-4c4e-8b20-6cdfd30fe1b6)  
## Nội dung bài tập
- Dựa trên csdl của đồ án.  
- Tìm cách bổ xung thêm 1 (hoặc vài) trường phi chuẩn (là trường tính toán được, nhưng thêm vào thì ok hơn, ok hơn theo logic nào đó của bài toán).  
+ Trong bảng HopDong, có trường phi chuẩn là mã nhân khẩu để not null, trong trường hợp không có nhân khẩu mới thì sẽ không được điền thêm thông tin vào HopDong vì vậy chúng ta thêm 1 trigger để ngăn chặn thao tác đó:  
![image](https://github.com/user-attachments/assets/e7e9f90c-0df0-48fd-a12a-117043cdd36f)  
+ Và khi có 1 nhân khẩu thay đổi nơi cư trú, việc xóa dữ liệu trong bảng nhân khẩu thì trigger sẽ giúp tự động xóa thông tin của cư dân/khách vãng lai đó:  
![image](https://github.com/user-attachments/assets/bb1934c5-e752-419c-b897-b2b4ae07cc3c)  
+ Thêm 1 trigger vào bảng hóa đơn để tự cập nhập trạng thái đã được thanh toán/chưa được thanh toán của hợp đồng mỗi khi gia hạn
![image](https://github.com/user-attachments/assets/23238017-5817-431d-91f3-3c3083a25c83)  
- Nhập dữ liệu có kiểm soát cho các bảng để test trigger
- Kết quả sau khi chạy thử trigger
