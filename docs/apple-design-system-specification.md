# FlowDesk.AI — Apple Minimalist Design System Specification

> **Phong cách cốt lõi:** Apple Design Philosophy (macOS Sequoia, iOS 18, Apple.com)  
> **Định hướng thẩm mỹ:** Tinh giản tối đa (Clean & Minimalist), không màu mè (Restrained Monochromatic), chữ chuẩn Apple SF Pro.  
> **Nguyên mẫu tương tác:** `docs/apple-design-system-homepages.html`  

---

## 1. Triết lý Thiết kế Tinh giản (Restrained Minimalism)

Để giao diện không bị "màu mè" như các dashboard AI thông thường mà đạt được độ sang trọng, đẳng cấp như sản phẩm của chính Apple:

1. **Triệt tiêu các mảng màu lòe loẹt:** Không sử dụng các thẻ nền xanh/đỏ/tím/cam bản to. Toàn bộ thẻ dữ liệu (Cards) đều dùng màu trắng tinh khiết (`#FFFFFF`) trên nền canvas xám dịu nhẹ (`#F5F5F7`).
2. **Dùng chấm tín hiệu tối giản (Minimal Indicator Dots):** Thay vì các tag bôi nền màu xanh/đỏ/cam, hệ thống chỉ dùng **một chấm tròn 6px** tinh tế (`--status-green`, `--status-orange`, `--status-red`) đặt cạnh dòng chữ xám/đen.
3. **Biểu đồ đơn sắc chuẩn Apple (Monochromatic Data Viz):**
   * Biểu đồ cột thể tích (Hourly Volume) lấy cảm hứng từ tính năng **Apple Screen Time** trên macOS/iOS: Thanh đen tuyền (`#1D1D1F`) thể hiện phần AI giải quyết tự động, thanh xám bạc (`#C7C7CC`) thể hiện phần kỹ thuật viên xử lý.
   * Thanh phân bổ danh mục (Category Distribution) lấy cảm hứng từ thanh dung lượng **Apple Storage** trong macOS System Settings: Dải màu chuyển tông từ đen than đến xám chì sang trọng.
4. **Đường viền Hairline siêu mảnh:** Tất cả đường viền chỉ dày 1px với độ mờ nhẹ `rgba(0, 0, 0, 0.08)`, tạo cảm giác phẳng, liền mạch và nhẹ nhàng.
5. **Nút bấm phong cách Apple:** Nút Primary sử dụng màu đen tuyền `#1D1D1F` (hoặc xanh Apple `#0071E3`), nút Secondary sử dụng màu trắng viền mảnh hairline, bo tròn dạng viên thuốc (Pill shape) mềm mại.

---

## 2. Hệ thống Font chữ Chuẩn Apple (Apple Typography)

Giao diện áp dụng bộ font chuẩn của Apple với tỷ lệ Tracking (khoảng cách chữ) và Tabular Nums (chữ số thẳng hàng) chuẩn mực:

* **Font Stack:**  
  ```css
  font-family: -apple-system, BlinkMacSystemFont, "SF Pro Display", "SF Pro Text", "SF Pro", "Helvetica Neue", Inter, sans-serif;
  ```
* **Tỷ lệ & Khoảng cách chữ (Optical Tracking):**
  * **Tiêu đề trang (View Title):** `24px / Bold / Letter-spacing: -0.025em;` — đậm, gọn gàng, tự tin.
  * **Chữ số đo lường (Large KPI Numbers):** `26px / Bold / Letter-spacing: -0.03em; font-variant-numeric: tabular-nums;` — giúp các con số luôn ngay hàng thẳng lối khi nhảy dữ liệu.
  * **Tiêu đề phân mục (Section Title):** `11.5px / Semibold / Uppercase / Letter-spacing: 0.04em; color: #6E6E73;`
  * **Nội dung thân bài (Body Text):** `13.5px / Regular / Letter-spacing: -0.01em; color: #1D1D1F;`
  * **Nhãn mô tả phụ (Secondary Text):** `12px / Regular / color: #6E6E73;`

---

## 3. Kiến trúc 3 Màn hình Trang chủ (Tối giản & Sang trọng)

### 3.1 Màn hình 1: Quản trị viên (Executive Operations — `SCR-DB-01`)
* **Thanh thông báo sự cố (macOS Notification Banner):** Thiết kế dạng thẻ trắng bo tròn thanh mảnh, một chấm đỏ phát sáng nhẹ báo hiệu cụm vé P1 kèm 2 nút bấm tối giản `Acknowledge` và `Inspect Incident`.
* **Bộ 4 chỉ số vận hành (KPI Metric Box):** 4 ô thẻ trắng tối giản hiển thị số vé tiếp nhận (`8,420`), tỷ lệ AI tự động (`68.4%`), vé đang xử lý (`1,760`), và độ tuân thủ SLA (`96.8%`).
* **Biểu đồ Intake & Tự động hóa:** Phong cách Apple Screen Time đơn sắc, không màu mè.
* **Radar điểm nghẽn SLA:** Bảng dữ liệu viền hairline siêu mảnh, thời gian đếm ngược dạng viên thuốc xám thanh nhã.
* **Năng lực đội ngũ kỹ thuật:** Bảng phân bổ kỹ sư trực ca, thể hiện trạng thái bằng chấm màu xanh lá/cam tinh tế.

### 3.2 Màn hình 2: Bàn làm việc Kỹ thuật viên (Technician Workbench — `SCR-DB-02`)
* **Thanh thông tin cá nhân & Công tắc trực ca (iOS Switch):** Công tắc gạt tròn kiểu iOS màu xanh lá khi bật `Active` và chuyển sang màu xám nhạt khi `Off`. Bộ đếm năng lực dạng chip xám `14 / 20 pts (70%)`.
* **4 chỉ số cá nhân:** Số vé đang giao, thời gian xử lý trung bình (MTTR `1h 48m`), SLA đạt `98.4%`, CSAT `4.92 ★`.
* **Bảng công việc hôm nay (My Active Queue Today):** Sắp xếp theo hạn chót SLA, phân biệt độ ưu tiên bằng chấm nhỏ đỏ (P1), cam (P2), xám (P3).
* **Bảng tiếp nhận vé nhóm (Unassigned Team Pool):** Danh sách vé mới của nhóm với nút bấm **[Claim Ticket]** màu đen Apple; khi bấm, vé trượt mượt mà sang bảng công việc cá nhân.

### 3.3 Màn hình 3: Cổng tự phục vụ Người gửi (Requester Self-Service — `SCR-DB-03`)
* **Hero Search kiểu Apple Spotlight:** Lời chào *"Good morning, Alex"* thanh lịch; thanh tìm kiếm viên thuốc tròn mềm mại (`⌘K`). Khi gõ phím, một menu thả xuống (Flyout) gợi ý ngay giải pháp triệt tiêu vé mà không dùng màu sắc lòe loẹt.
* **Ngăn nhắc việc (Action Stack):** 2 thẻ thông báo trắng sạch sẽ nhắc trả lời câu hỏi của AI và xác nhận đóng vé.
* **4 Dịch vụ nhanh 1-Click (Apple Service Grid):** Ô icon vuông bo tròn 9px tinh tế cho Access & IAM, Password & MFA, Hardware, Software.
* **Theo dõi tiến độ (Milestone Stepper):** Đường tiến trình tối giản 4 chặng với các chấm tròn đen và xanh dương Apple.

---

## 4. Hướng dẫn Mở file Trải nghiệm

Mở trực tiếp file sau bằng bất kỳ trình duyệt nào:
```text
docs/apple-design-system-homepages.html
```
* **Chuyển vai trò:** Bấm `Admin`, `Technician`, hoặc `Requester` trên thanh chuyển đổi tối giản ở giữa trên cùng.
* **Trải nghiệm tương tác:** Gạt công tắc `Shift Status`, bấm `Claim Ticket`, gõ tìm kiếm `vpn` trên màn Requester.

---

---

## 5. Bản Thiết Kế Đầy Đủ Toàn Diện (Interactive Multi-Role ITSM System)

> **File nguyên mẫu sản phẩm:** `docs/itsm-enterprise-apple-redesign.html`

Hệ thống được mở rộng hoàn chỉnh cho cả 3 phân hệ cốt lõi với khả năng tương tác sống động:

### 5.1 Phân hệ Người yêu cầu (Requester Portal — Alex Nguyen)

Cổng thông tin tự phục vụ tối giản, chuyên nghiệp và chuẩn xác theo triết lý Apple Enterprise SaaS:

#### 1. Điều hướng chính (Main Navigation — Đúng 3 Menu)
1. **Trang chủ (`req-home`):** Cổng tự phục vụ tổng quan.
2. **Lời yêu cầu (`req-request`):** Quản lý toàn bộ danh sách vé cá nhân của Alex Nguyen.
3. **Giải pháp (`req-solution`):** Kho bài viết tri thức tự khắc phục sự cố.

#### 2. Trang chủ (Home Page — `req-home`)
- **Nút hành động nổi bật:** `+ Tạo Yêu cầu Hỗ trợ (Create Support Request)` mở form đầy đủ thông tin.
- **Thông báo vận hành (Announcements):** Cảnh báo lịch bảo trì SSO Okta, VPN và khuyến nghị nâng cấp OS.
- **Tóm tắt vé cá nhân (My Ticket Summary):** 5 thẻ đo lường chuẩn xác: *Tổng yêu cầu (5), Đang mở - Open (1), Đang xử lý - In Progress (1), Chờ thông tin - Pending (1), Đã giải quyết - Resolved (2)*.
- **Bảng vé cập nhật gần đây:** Hiển thị các vé mới nhất của Alex Nguyen; bấm vào bất kỳ dòng nào sẽ mở ngay trang **Chi tiết vé (Ticket Detail)**.
- **Lối tắt truy cập nhanh (Quick Access):** 4 ô tác vụ 1-click (Tạo yêu cầu, Vé của tôi, Kho giải pháp, Hỏi đáp FAQ).
- **Hỏi đáp thường gặp (FAQ):** Tìm kiếm tức thì, lọc theo danh mục (VPN, IAM, Phần cứng) và cơ chế Accordion mở rộng câu trả lời.

#### 3. Trang Lời yêu cầu (Request Page — `req-request`)
- **Bảng cuộn 4 chiều (4-Way Scrolling):** Độ rộng bảng lớn, cuộn ngang - dọc mượt mà.
- **Cố định cột đầu (Sticky Column):** Ghim cột `MÃ YÊU CẦU` sang trái khi cuộn ngang.
- **Bộ lọc & Tìm kiếm trực tiếp:** Lọc theo mã vé, tiêu đề, trạng thái (*Open, In Progress, Pending, Resolved, Closed*) và mức ưu tiên (*Critical, High, Medium, Low*).
- **Tùy chỉnh cột (Column Customizer):** Popover chọn ẩn/hiện bất kỳ cột nào trong bảng.
- **Tương tác mở chi tiết:** Nhấn vào bất kỳ hàng nào trên bảng hoặc nút `Chi tiết & Hội thoại` sẽ chuyển thẳng sang trang **Chi tiết vé chuyên biệt**.

#### 4. Trang Chi tiết Vé Chuyên biệt (Ticket Detail Page — `view-req-ticket-detail`)
- **Header thông tin chuẩn mực:**
  - Nút quay lại: `← Quay lại danh sách yêu cầu (Back to Requests)`.
  - Mã vé dạng Pill: `#REQ-2026-00125`.
  - Tiêu đề đầy đủ (Full Subject) nổi bật.
  - Nhãn trạng thái trực quan với chấm tròn tối giản (*Open, In Progress, Pending, Resolved*).
  - Dòng Metadata chi tiết: *Người tạo, Kênh tạo (✉️ Email / 🌐 Web Portal), Ngày tạo, Phản hồi đầu tiên, Cập nhật lần cuối*.
- **Hệ thống 6 Tabs điều hướng Apple Navigation Tabs:**
  1. **Tab 1 — Detail (Chi tiết & Hội thoại):**
     - **Request Information:** Khung thông tin có cấu trúc gồm Người gửi, Danh mục, Danh mục con, Nhóm hỗ trợ, Kỹ thuật viên phụ trách, Mức ưu tiên và Mô tả ban đầu.
     - **Conversations (Hội thoại Trao đổi):** Phần quan trọng nhất thể hiện toàn bộ trao đổi giữa Requester và Technician qua kênh Email và Web. Phân biệt rõ tin nhắn Người gửi, phản hồi công khai của Kỹ thuật viên (Sarah Jenkins) và thông báo phân luồng AI. Tuyệt đối **không hiển thị Ghi chú nội bộ (Internal Notes)** cho Requester.
     - **Hộp soạn thảo phản hồi (Reply Composer):** Ô nhập văn bản, đính kèm tệp, nút `Gửi phản hồi (Send Reply)` (lưu vào vé hiện tại, cập nhật mốc thời gian, không tạo vé mới) và nút tiện ích `✉️ Mô phỏng Email từ Kỹ thuật viên` để kiểm thử tương tác nhận thư.
  2. **Tab 2 — Resolution (Giải pháp):** Hiển thị tóm tắt giải pháp (Resolution Summary), nguyên nhân gốc rễ (Root Cause), các bước khắc phục chi tiết (Solution Description), ngày giải quyết và người xử lý.
  3. **Tab 3 — Reminder (Nhắc nhở):** Danh sách lời nhắc theo dõi sự cố kèm thời hạn và trạng thái.
  4. **Tab 4 — Announcement (Thông báo):** Các thông báo liên quan đến dịch vụ của vé.
  5. **Tab 5 — History (Lịch sử):** Nhật ký kiểm toán thời gian thực ghi lại từng mốc: Tạo vé qua Email -> AI phân luồng & gán việc -> Kỹ thuật viên tiếp nhận -> Gửi email phản hồi.
  6. **Tab 6 — Properties (Thuộc tính):** Bảng tổng hợp các thuộc tính kỹ thuật có cấu trúc (chỉ đọc) của vé.

#### 5. Form Tạo Yêu cầu Mới (Create Support Request Modal)
Bao gồm đầy đủ các trường thông tin theo yêu cầu:
1. **Requester Name:** Tự động điền `Alex Nguyen (alex.nguyen@company.com)` và khóa chỉnh sửa.
2. **Category (Danh mục):** Chọn danh mục chính (Mạng, Quyền hạn IAM, Phần cứng, Phần mềm).
3. **Subcategory (Danh mục con):** Dropdown động tự động thay đổi theo Danh mục chính.
4. **Subject (Chủ đề):** Tiêu đề ngắn gọn mô tả sự cố.
5. **Priority (Mức độ ưu tiên):** Critical (P1), High (P2), Medium (P3), Low (P4).
6. **Description (Mô tả):** Khung nhập chi tiết triệu chứng, mã lỗi.
7. **Group (Nhóm hỗ trợ):** Lựa chọn nhóm chuyên trách (NetOps, Service Desk, Infra, SecOps).
8. **Emails to Notify (Tùy chọn):** Danh sách email nhận thông báo cập nhật vé.
9. **Attachments (Tùy chọn):** Chọn tệp đính kèm (ảnh chụp màn hình, log file), hỗ trợ xem danh sách và xóa tệp trước khi gửi.
- **Nút hành động:** `Thêm yêu cầu (Add Request)` (kiểm tra hợp lệ, gán mã vé mới, gán trạng thái ban đầu `Open`, kích hoạt AI phân luồng và chuyển ngay đến trang Chi tiết vé) & `Hủy bỏ (Cancel)`.

#### 6. Vòng đời Trạng thái Vé (Ticket Status Lifecycle)
- `Open` (Khởi tạo ban đầu khi tạo vé qua Web hoặc Email) &rarr; `In Progress` (Kỹ thuật viên tiếp nhận) &rarr; `Pending` (Chờ người dùng phản hồi) &rarr; `Resolved` (Đã xử lý xong) &rarr; `Closed` (Đóng hoàn tất).


### 5.2 Phân hệ Kỹ thuật viên (Technician — Sarah Jenkins)
Bao gồm đầy đủ 6 phân mục chuyên môn:
1. **Trang chủ (`tech-home`):** Trực ca, tải công việc, cảnh báo SLA khẩn cấp và 6 thẻ đo lường hiệu năng.
2. **Lời yêu cầu (`tech-requests`):**
   - **Thanh tác vụ kỹ thuật chuyên sâu (Action Toolbar):** Nằm ngay cạnh nút Tùy chỉnh cột, hỗ trợ đầy đủ 8 thao tác:
     * `+ New`: Tạo vé hỗ trợ kỹ thuật mới.
     * `✏️ Edit`: Chỉnh sửa thông tin vé đã chọn.
     * `📥 Pickup`: Tiếp nhận vé vào ca trực cá nhân, tự động chuyển trạng thái sang [In Progress].
     * `✓ Close`: Đóng vé hoàn tất theo quy chuẩn ITIL.
     * `🔗 Merge`: Gộp các vé trùng lặp vào một vé chính.
     * `↗ Link Request`: Liên kết vé với Sự cố hệ sinh thái hoặc vấn đề hạ tầng cha.
     * `👤 Assign`: Phân công lại vé cho kỹ thuật viên khác.
     * `🗑 Delete`: Xóa vé có xác nhận an toàn.
   - **Hộp tích chọn hàng loạt (Row Checkboxes):** Tích chọn từng dòng hoặc chọn tất cả (`Select All`) để xử lý tác vụ hàng loạt.
   - **Bảng cuộn 4 chiều:** Ghim cột Mã vé bên trái, hỗ trợ tìm kiếm và lọc tức thì.
3. **Giải pháp (`tech-solutions`):** Quản lý tài liệu kỹ thuật Runbook và nút soạn thảo bài viết mới.
4. **Thay đổi (`tech-changes`):** Quản lý quy trình thay đổi hệ thống (RFC, phê duyệt CAB, kế hoạch rollback).
5. **Hoạt động (`tech-activities`):** Nhật ký dòng thời gian hoạt động vận hành thời gian thực (*Activity & Event Stream*), theo dõi các thao tác Pickup, Close, Merge, Link, Assign và phân luồng AI.
6. **Báo cáo (`tech-reports`):** Báo cáo hiệu năng cá nhân (MTTR, tỷ lệ đạt SLA 98.4%, tỷ lệ giải quyết lần đầu FCR).

### 5.3 Phân hệ Quản trị viên (Administrator — Thu An)
Bao gồm 8 phân mục quản trị toàn diện:
- `adm-home` (Dashboard điều hành)
- `adm-requests` (Quản lý toàn bộ 8.4k vé toàn doanh nghiệp)
- `adm-solutions` (Kho tri thức & Phê duyệt bài viết mới)
- `adm-changes` (Hội đồng thẩm định thay đổi CAB)
- `adm-assets` (Kiểm kê tài sản thiết bị toàn công ty)
- `adm-reports` (Phân tích chỉ số BI doanh nghiệp & Xuất báo cáo)
- `adm-users` (Quản lý danh bạ tài khoản & Ma trận phân quyền RBAC)
- `adm-config` (Cấu hình SLA P1–P3 và quy tắc phân luồng tự động)
