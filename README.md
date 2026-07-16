# CafeF Financial Extractor 📊

Công cụ web (HTML/JS thuần) giúp tự động hóa việc thu thập (crawl), tổng hợp dữ liệu báo cáo tài chính của nhiều doanh nghiệp từ trang thông tin tài chính **CafeF**. 

Dự án được tối ưu hóa giao diện giúp nhà phân tích tài chính dễ dàng theo dõi, lọc dữ liệu theo chỉ tiêu mong muốn và xuất trực tiếp ra định dạng Excel chỉ với vài cú click chuột.

---

## ✨ Tính năng nổi bật

- **⚡ Thu thập dữ liệu thông minh**: Hỗ trợ 2 chế độ lấy dữ liệu:
  - **Chạy tuần tự (Sequential)**: Lấy dữ liệu an toàn, giảm thiểu nguy cơ bị chặn IP.
  - **Chạy song song (Parallel Limit)**: Sử dụng kỹ thuật giới hạn luồng (Concurrency Limit = 5) bằng Promise Pool, tối ưu tốc độ thu thập vượt trội nhưng vẫn đảm bảo tính ổn định.
- **🎯 Lọc chỉ tiêu động (Multi-Select)**: Cho phép tìm kiếm nhanh và lựa chọn một hoặc nhiều chỉ tiêu cụ thể (Ví dụ: Doanh thu, Lợi nhuận sau thuế, Phải thu khách hàng,...).
- **📐 Cấu trúc bảng ngang tối ưu**: Tự động gộp toàn bộ các chỉ tiêu được chọn vào một dòng duy nhất cho mỗi doanh nghiệp (không tạo thêm nhiều dòng `<tr>` gây loãng bảng), giúp dễ dàng so sánh chéo giữa các doanh nghiệp.
- **📌 Giao diện đóng băng (Sticky Headers & Columns)**:
  - Giữ cố định 2 dòng tiêu đề bảng khi cuộn xuống dưới.
  - Giữ cố định đồng thời cột **Mã cổ phiếu** và **Tên doanh nghiệp** sát cạnh nhau khi cuộn ngang, thuận tiện phân tích bảng dữ liệu lớn.
- **📄 Xuất Excel nhanh chóng**: Tích hợp thư viện `SheetJS` để xuất toàn bộ dữ liệu hiển thị trên bảng ra file `.xlsx` một cách trực quan, giữ nguyên cấu trúc phân tầng.
- **🎨 Giao diện hiện đại**: Thiết kế tối giản, sạch sẽ, hỗ trợ hiển thị tiến trình thu thập thời gian thực (Progress Log).

---

## 🛠️ Công nghệ sử dụng

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **DOM Parser**: Sử dụng API trình duyệt nguyên bản để bóc tách dữ liệu từ tài liệu HTML trả về từ CafeF.
- **Thư viện bên thứ ba**: [SheetJS (xlsx.full.min.js)](https://github.com/SheetJS/sheetjs) phục vụ tính năng xuất file Excel.

---

## 🚀 Hướng dẫn sử dụng nhanh

Dự án được cấu hình chạy hoàn toàn trên trình duyệt (Client-side) và đang được hosting trực tiếp qua dịch vụ **GitHub Pages**. Bạn không cần tải hay cài đặt bất cứ thứ gì về máy:

1. **Truy cập ứng dụng**: Mở trình duyệt và truy cập liên kết:  
   👉 **https://levutrieu.github.io/CafefExtractor**
2. **Thao tác**:
   - Chọn **Loại báo cáo** (Bảng cân đối kế toán, Kết quả kinh doanh, Lưu chuyển tiền tệ...).
   - Chọn **Năm tài chính** cần lấy dữ liệu.
   - Tại ô **Chọn chỉ tiêu**, tìm kiếm nhanh và tích chọn các chỉ tiêu bạn cần phân tích.
   - Nhấn **Chạy song song** (để lấy dữ liệu nhanh) hoặc **Chạy tuần tự** (để chạy an toàn).
3. **Xuất kết quả**: Sau khi ứng dụng hoàn thành tiến trình bóc tách dữ liệu, nhấn nút **Xuất Excel** để tải báo cáo trực quan về máy tính cá nhân dưới định dạng `.xlsx`.

---

## 📂 Danh sách doanh nghiệp hỗ trợ

Công cụ hiện đã tích hợp sẵn danh sách hàng trăm mã cổ phiếu phổ biến trên các sàn giao dịch chứng khoán Việt Nam (như AAA, ASM, BCG, HPG, HSG, MSN, MWG, VNM, VIC, VRE...). Bạn có thể dễ dàng bổ sung thêm mã cổ phiếu tùy ý bằng cách chỉnh sửa mảng `companies` trong mã nguồn JavaScript.

---

## ⚠️ Lưu ý miễn trừ trách nhiệm (Disclaimer)

Dự án này được phát triển cho mục đích học tập, nghiên cứu cá nhân và phân tích dữ liệu đầu tư nội bộ. Vui lòng không lạm dụng công cụ để thực hiện việc gửi yêu cầu (request) với tần suất quá cao lên máy chủ của CafeF, tránh ảnh hưởng đến hệ thống cung cấp dữ liệu gốc.

---

## ✨ URL bổ trợ

👉 Danh sách tất cả công ty: **[All Company](https://cafef.vn/du-lieu/ajax/pagenew/databusiness/congtyniemyet.ashx?centerid=0&skip=0&take=2000&major=0)**
