# Bài tập về nhà

## Phần 1: Phân tích các vi phạm Quy tắc Vàng trong tư duy Database

1.  **Quy tắc 1: Tính liên tục của dữ liệu 
    -   **Hiện trạng vi phạm:** Bảng xuất hiện hàng trống  xen giữa các dòng dữ liệu.
        
    -   **Hệ quả kỹ thuật:** Khi nhấn tổ hợp phím tắt `Ctrl + Shift + L`, tính năng AutoFilter của Excel tự Hàng trống đóng vai trò như một điểm ngắt ranh giới, làm Excel hiểu rằng bảng đã kết thúc dẫn đến việc các hàng phía dưới hàng trống bị bỏ sót hoàn toàn khỏi phạm vi lọc.
        
2.  **Quy tắc 2: Cấu trúc nguyên tử và duy nhất của Tiêu đề 
    
    -   **Hiện trạng vi phạm:** Hàng tiêu đề đang sử dụng tính năng **Merge & Center**.
        
    -   **Hệ quả kỹ thuật:**  giá trị tiêu đề thực chất chỉ lưu ở ô trên cùng bên trái , các ô còn lại trong vùng gộp nhận giá trị rỗng . Điều này làm hỏng cấu trúc header, khiến Excel không thể gán AutoFilter chính xác.
3.  **Quy tắc 3: Tính nhất quán và chuẩn hóa của giá trị dữ liệu (Data Cleanliness & Consistency)**
    
    -   **Hiện trạng vi phạm:** Chuỗi ký tự ở cột "Trạng thái" chứa các khoảng trắng vô hình ở đầu hoặc cuối chuỗi 
        

## Phần 2: Hướng dẫn các bước sửa lỗi và chuẩn hóa

### Bước 1: Hủy bỏ Merge Cell ở hàng tiêu đề

1.  Chọn toàn bộ hàng tiêu đề đang bị gộp.
    
2.  Tại thẻ **Home** > nhóm **Alignment** > nhấp vào **Merge & Center** để bỏ gộp ô
    
3.  Đặt lại tên tiêu đề rõ ràng, đơn nhất cho từng cột (ví dụ tách riêng:  `Mã thiết bị`,  `Tên thiết bị`,  `Khu vực`,  `Trạng thái`).
    

    

### Bước 2: Xóa bỏ triệt để các hàng trống (Blank Rows)

1.  Bôi đen vùng dữ liệu từ hàng tiêu đề đến hết dòng cuối cùng.
    
2.  Nhấn phím `F5` (hoặc `Ctrl + G`) $\rightarrow$ chọn **Special...**  $\rightarrow$ chọn **Blanks**  $\rightarrow$ nhấn **OK**.
    
3.  Khi các ô trống đang được chọn, nhấn chuột phải $\rightarrow$ chọn **Delete...**  $\rightarrow$ chọn **Entire row** (Xóa toàn bộ hàng) $\rightarrow$ nhấn **OK**.
    
4.  Dữ liệu lúc này đã liền mạch, không còn bị ngắt quãng.
    

### Bước 3: Làm sạch cột "Trạng thái" bằng hàm `TRIM()`

1.  Chèn thêm một cột phụ tạm thời bên cạnh cột "Trạng thái" cũ, đặt tên là **Trạng thái chuẩn**.
    
2.  Giả sử ô trạng thái đầu tiên nằm tại ô `D3`, tại ô cột phụ nhập công thức:
    
    Excel
    
    ```
    =TRIM(D3)
    
    ```
    
    _Hàm `=TRIM()` sẽ loại bỏ toàn bộ khoảng trắng thừa ở đầu, cuối và rút gọn khoảng trắng kép giữa các từ về 1 khoảng trắng chuẩn._
    
3.  Copy công thức xuống toàn bộ các dòng còn lại trong cột.
    
4.  **Cố định giá trị:** Bôi đen toàn bộ cột vừa tính $\rightarrow$ nhấn `Ctrl + C` (Copy) $\rightarrow$ nhấp chuột phải tại chính cột đó $\rightarrow$ chọn **Paste as Values** (hoặc `Paste Special > Values`) để chuyển từ công thức sang dữ liệu tĩnh.
    
5.  Xóa cột trạng thái cũ hoặc đổi tên cột mới thành `Trạng thái`.
    
