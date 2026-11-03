# Vấn đề :
Một quản trị viên điều phối cần quản lý đồng thời: tài khoản cá nhân, tài khoản quản trị hệ thống GreenLog, và tài khoản kiểm thử (Sandbox). Việc dùng chung một cửa sổ trình duyệt khiến các phiên đăng nhập bị xung đột (Session Conflict).
# Yêu cầu :
-   **Chức năng 1 (Cách ly dữ liệu):** Thiết lập mô hình 3 Profile độc lập (Personal - Work - Sandbox) để triệt tiêu hoàn toàn rủi ro văng tài khoản.
    
-   **Chức năng 2 (Tổ chức Bookmark):** Xây dựng cấu trúc cây thư mục Bookmark khoa học để truy cập nhanh các công cụ như GitHub, Canvas LMS và Portal công ty.
# Cách làm :

### Phần 1. Phân tích

-   Incognito Mode (Chế độ ẩn danh):
    
    -   Lưu trữ tạm thời trên RAM:Không lưu lịch sử, cookie hay dữ liệu trang web vào ổ cứng. Toàn bộ dữ liệu phiên làm việc sẽ bị xóa sạch ngay khi đóng toàn bộ cửa sổ ẩn danh.
        
    -   Hạn chế: Không hỗ trợ lưu trữ lâu dài, không đồng bộ dữ liệu qua tài khoản đám mây, và dễ gây xung đột session nếu mở nhiều tab ẩn danh cùng lúc.
        
-   Dedicated Profile (Hồ sơ chuyên dụng):
    
    -   Lưu trữ lâu dài trên ổ cứng: Mỗi Profile sở hữu một thư mục dữ liệu riêng biệt trên ổ đĩa (lưu trữ độc lập cookies, lịch sử, bookmark, extension và mật khẩu).
        
    -   Ưu điểm: Triệt tiêu hoàn toàn xung đột phiên (Session Conflict), cho phép duy trì trạng thái đăng nhập lâu dài và cá nhân hóa hoàn toàn cho từng mục đích sử dụng (Personal - Work - Sandbox).
        

### Phần 2. Triển khai

Quy trình tạo Profile mới và đồng bộ hóa Cloud Sync để bảo vệ Bookmark:

1. Tạo Profile độc lập: Mở trình duyệt →\rightarrow→ Nhấp vào ảnh đại diện/biểu tượng Profile ở góc trên bên phải →\rightarrow→ Chọn Add (Thêm)  →\rightarrow→ Đặt tên (ví dụ:  _Work_ hoặc _Sandbox_) và chọn tùy chọn tạo lối tắt trên màn hình.
    
2.  Kích hoạt Cloud Sync (Đồng bộ hóa đám mây):
    
    -   Đăng nhập vào Profile vừa tạo bằng tài khoản Google tương ứng.
        
    -   Bật tính năng Turn on sync (Bật đồng bộ) tích chọn đồng bộ Bookmarks,  Passwords, và Autofill.
        
    -   Khi đổi máy tính mới, chỉ cần đăng nhập lại tài khoản Google vào Profile tương ứng, toàn bộ cấu trúc Bookmark và dữ liệu sẽ tự động khôi phục.
        

### Phần 3. Kiểm thử

Khi làm việc trên máy tính công cộng, hãy tuân thủ nguyên tắc sử dụng Guest Profile (Chế độ Khách):

-   Tuyệt đối không đăng nhập tài khoản cá nhânvào trình duyệt chính của máy lạ.
    
-   Sử dụng tính năng Open Guest Window (Mở cửa sổ Khách) để trình duyệt tạo một phiên làm việc hoàn toàn cô lập, không lưu lịch sử, không chia sẻ cookie với bất kỳ profile nào khác.
    
-   Đóng toàn bộ cửa sổ Guest ngay khi kết thúc công việc để tự động xóa sạch mọi dấu vết phiên làm việc trên thiết bị công cộng.
