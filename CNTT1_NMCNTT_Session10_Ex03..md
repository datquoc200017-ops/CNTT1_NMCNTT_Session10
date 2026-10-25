# Bài tập về nhà

## Phần 1: Phân tích 4 tham số VLOOKUP trong bài toán

Cú pháp:  `=VLOOKUP(Lookup_value, Table_array, Col_index_num, [Range_lookup])`

1.  **Lookup_value :** Mã linh kiện tại Sheet `Don_Hang` (ví dụ: ô `B2`).
    
2.  **Table_array:** Vùng chứa danh mục tại Sheet `Danh_Muc` (ví dụ:  `Danh_Muc!$A$2:$C$10`).
    
3.  **Col_index_num:**
    
    -   Cột `2` để lấy **Tên linh kiện**.
        
    -   Cột `3` để lấy **Đơn giá**.
        
4.  **Range_lookup :** Chọn `0` (hoặc `FALSE`) để tìm kiếm chính xác tuyệt đối theo mã linh kiện.
    

## Phần 2: Triển khai công thức & Xử lý bẫy dữ liệu

### 1. Khắc phục Bẫy 1 (Lỗi lệch vùng do quên dấu `$`)

-   Dùng phím `F4` để khóa cố định bảng tra (`$A$2:$C$10`) nhằm tránh việc vùng tra cứu bị trôi xuống dưới khi kéo công thức cho 100 dòng đơn hàng.
    

### 2. Khắc phục Bẫy 2 

-   Nếu bảng danh mục có khoảng trắng thừa, dùng hàm `TRIM()` kết hợp tại cột mã linh kiện nguồn hoặc chuẩn hóa dữ liệu trước bằng `=TRIM(...)`.
    


