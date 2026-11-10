# GIẢI CỨU VẦN THƠ
> *Gom từng con chữ – Gửi trọn hồn thơ.*

Ứng dụng web giáo dục tương tác khôi phục vần điệu thơ ca dành cho **Giáo viên và Học sinh Ngữ văn lớp 6–7** (đặc biệt bộ sách *Kết nối tri thức với cuộc sống*). Ứng dụng hỗ trợ hoàn hảo việc trình chiếu trên máy chiếu 16:9, bảng tương tác thông minh và thiết bị cảm ứng trong lớp học.

---

## 🌟 Tính năng nổi bật

### 1. Dành cho Học sinh (Trải nghiệm lớp học hào hứng)
- **Kéo thả & Chạm linh hoạt**: Hỗ trợ đồng thời kéo thả bằng chuột/bút và chế độ **Chạm chọn thẻ ➔ Chạm ô đích** (cực kỳ hữu ích trên bảng tương tác thông minh, không lo trượt tay hay rơi chữ giữa chừng).
- **Thổi bay vần thơ**: Hoạt ảnh cơn gió cuốn những chiếc lá và cánh hoa, đưa các con chữ ra khỏi trang thơ và xáo trộn ngẫu nhiên.
- **Kiểm tra thông minh**: Đánh dấu trực quan các vị trí đúng (xanh lục dịu) và vị trí cần tư duy lại (màu cam hổ phách); **tuyệt đối không tự điền đáp án** để giữ trọn tính sư phạm.
- **Gợi ý 3 cấp độ sư phạm**:
  - *Cấp 1*: Hiển thị chữ cái đầu tiên mờ mờ trong ô trống.
  - *Cấp 2*: Đánh dấu phát sáng ô chữ và con chữ tương ứng có liên kết hiệp vần (vần lưng, vần chân trong thơ lục bát).
  - *Cấp 3*: Cứu nguy tự động đưa 1 thẻ về đúng vị trí (trừ 10 điểm gợi ý).
- **Hoàn tác (Undo)**: Nút hoàn tác và phím tắt `Ctrl + Z` giúp học sinh sửa nước đi bất cứ lúc nào.
- **Hoàn thành & Đọc hiểu**: Khi giải cứu trọn vẹn, pháo hoa chúc mừng bùng nổ, bài thơ nguyên vẹn hiện ra kèm **Câu hỏi gợi mở đọc hiểu & cảm thụ văn học** để cả lớp cùng thảo luận.

### 2. Dành cho Giáo viên (Soạn bài & Quản lý bài giảng)
- **Tạo & Lưu bài thơ không giới hạn**: Nhập tên bài, tác giả, khối lớp, nội dung thơ nhiều dòng, nhiều khổ.
- **Tùy biến độ khó**:
  - *Dễ*: 70% từ được giữ cố định sẵn trong ô, học sinh chỉ cần tìm 30% từ còn lại.
  - *Vừa*: 40% từ cố định, xáo trộn 60%.
  - *Khó*: Xáo trộn 100% toàn bộ con chữ.
- **Xử lý bài thơ dài thông minh**: Tự động chia bài thơ dài thành từng khổ/vòng nhỏ (khoảng 12–24 thẻ mỗi lượt), tránh làm học sinh bị ngợp bởi quá nhiều thẻ.
- **Chế độ kiểm tra**: Kiểm tra theo từng dòng hoặc Kiểm tra toàn bài.
- **Thời gian thi đấu**: Không giới hạn, 30s, 60s, 90s, 120s, 180s.
- **Hiện đáp án**: Nút mở toàn bộ đáp án khi hết giờ (có hộp thoại xác nhận bảo mật).
- **Xuất / Nhập JSON**: Dễ dàng sao lưu kho bài thơ và chia sẻ cho đồng nghiệp trong tổ bộ môn qua tệp JSON.
- **Âm thanh tổng hợp tự nhiên**: Tích hợp âm thanh Web Audio API (tiếng chuông hạc, tiếng gió reo, nhạc chiến thắng) không phụ thuộc file ngoài, có nút bật/tắt âm thanh tiện lợi.

### 3. Tối ưu cho Máy chiếu & Lớp học
- **Chế độ máy chiếu 16:9**: Nút bấm một chạm phóng to font chữ (24px–28px), tăng độ tương phản và căn lề tối ưu để học sinh ngồi bàn cuối vẫn nhìn rõ nét.
- **Chế độ Toàn màn hình**: Ẩn thanh công cụ trình duyệt để mở rộng không gian bài học.

---

## 🚀 Hướng dẫn cài đặt và chạy trên máy tính

### Yêu cầu hệ thống:
- Đã cài đặt **Node.js** (phiên bản 18+ hoặc 20+ LTS).

### Các bước khởi chạy:

1. **Cài đặt thư viện phụ thuộc**:
   ```bash
   npm install
   ```

2. **Chạy máy chủ phát triển cục bộ**:
   ```bash
   npm run dev
   ```
   Sau đó mở trình duyệt theo địa chỉ: `http://localhost:5173`

3. **Kiểm tra và đóng gói sản phẩm**:
   ```bash
   npm run build
   ```
   Thư mục `dist/` chứa toàn bộ mã nguồn tĩnh sẵn sàng triển khai.

---

## 🌐 Hướng dẫn triển khai Online (Vercel / Netlify / GitHub Pages)

### Cách 1: Triển khai nhanh qua Vercel (Khuyên dùng)
1. Đăng ký/đăng nhập tài khoản miễn phí tại [Vercel](https://vercel.com).
2. Tải mã nguồn lên GitHub hoặc kéo thả thư mục dự án lên giao diện Vercel.
3. Cấu hình build:
   - **Framework Preset**: `Vite`
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
4. Nhấn **Deploy** và nhận ngay đường link chia sẻ cho học sinh và giáo viên trong trường!

### Cách 2: Triển khai qua Netlify
1. Đăng nhập [Netlify](https://www.netlify.com).
2. Kéo thả trực tiếp thư mục `dist` vào mục **Deploys**.
3. Trang web sẽ trực tuyến ngay lập tức với tên miền tùy chỉnh miễn phí.

---

## 📂 Cấu trúc mã nguồn

```
d:/KHOA_ANTIGRAVITY/web cho Ngọc/
├── index.html                  # File HTML chính, cấu hình SEO & Google Fonts
├── package.json                # Cấu hình gói và thư viện
├── vite.config.ts              # Cấu hình Vite React TypeScript
├── src/
│   ├── main.tsx                # Điểm khởi đầu ứng dụng
│   ├── App.tsx                 # Điều phối trò chơi, quản lý trạng thái chính
│   ├── index.css               # Hệ thống thiết kế Modern Storybook & CSS Variables
│   ├── types/
│   │   └── poem.ts             # Kiểu dữ liệu TypeScript (Poem, Slot, Token, Round)
│   ├── services/
│   │   ├── audio.ts            # Bộ tổng hợp âm thanh Web Audio API
│   │   ├── poemParser.ts       # Xử lý tiếng Việt NFC, ngắt nhịp/vần, dấu câu, chia khổ
│   │   └── storage.ts          # Lưu trữ localStorage, bài thơ mẫu, xuất/nhập JSON
│   └── components/
│       ├── Navbar.tsx          # Thanh điều hướng, bật máy chiếu, âm thanh, toàn màn hình
│       ├── PoetryPage.tsx      # Trang thơ cổ tích chứa các ô nhận chữ
│       ├── PoemSlotView.tsx    # Ô chữ tương tác, nhận thả thẻ hoặc click đặt chữ
│       ├── WordCard.tsx        # Thẻ chữ tương tác, hỗ trợ kéo chuột & chạm chọn
│       ├── WordTray.tsx        # Vùng từ thất lạc (kho từ bị gió thổi bay)
│       ├── GameControls.tsx    # Thanh công cụ: Kiểm tra, Gợi ý, Hoàn tác, Thổi bay
│       ├── WindAnimation.tsx   # Hoạt ảnh cơn gió, cánh hoa và lá rơi
│       ├── CompletionModal.tsx # Bảng chúc mừng, hiển thị bài thơ nguyên văn & đọc hiểu
│       ├── TeacherEditor.tsx   # Trình soạn bài thơ và thiết lập thông số cho giáo viên
│       ├── LibraryModal.tsx    # Quản lý kho bài thơ, xuất/nhập JSON
│       ├── ConfirmModal.tsx    # Hộp thoại xác nhận mở đáp án / xóa bài
│       └── HelpModal.tsx       # Hướng dẫn chi tiết cho giáo viên và học sinh
```

---

## 📚 Bộ bài thơ mẫu tích hợp sẵn
1. **Trang thơ sân trường** (Bài thơ mẫu chuẩn đặc tả: thể thơ lục bát 6–8, câu hỏi liên kết vần *trường* – *thương*).
2. **Hạt gạo làng ta** (Trần Đăng Khoa – Thể thơ 4 chữ sinh động).
3. **Chuyện cổ nước mình** (Lâm Thị Mỹ Dạ – Thể thơ lục bát bài học làm người).
4. **Ước mơ thời áo trắng** (Thể thơ lục bát truyền cảm hứng học trò).
