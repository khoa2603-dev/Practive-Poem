# YÊU CẦU XÂY DỰNG WEBSITE — GIẢI CỨU VẦN THƠ

> **Hướng dẫn cho Antigravity:** Hãy xây dựng một website **chạy được thật, hoàn chỉnh và có thể dùng ngay trong lớp học**, không chỉ thiết kế mockup. Hãy xem tài liệu này là yêu cầu sản phẩm và thực hiện theo mức độ ưu tiên dưới đây. Tự đưa ra các quyết định kỹ thuật hợp lý, không cần hỏi lại những tiểu tiết.

## 1. Mục tiêu và đối tượng

- **Tên sản phẩm:** GIẢI CỨU VẦN THƠ.
- **Slogan:** *Gom từng con chữ – Gửi trọn hồn thơ.*
- **Người dùng:** Giáo viên Ngữ văn lớp 6–7, đặc biệt bộ sách **Kết nối tri thức với cuộc sống**; học sinh lên máy tính, máy chiếu hoặc bảng tương tác để chơi.
- **Ý tưởng chính:** Giáo viên dán một đoạn thơ vào web; các tiếng/từ trong thơ bị tách thành thẻ chữ, xuất hiện hiệu ứng “cơn gió” làm các thẻ bay ra khỏi trang thơ và xáo trộn quanh màn hình. Học sinh **kéo thả** các thẻ về vị trí đúng để khôi phục bài thơ. Sau khi hoàn thành, hiện bài thơ nguyên vẹn và câu hỏi gợi mở đọc hiểu.
- **Ưu tiên sư phạm:** vui, dễ tham gia, đẹp, chữ dễ đọc, kiến thức đúng; tập trung vào trật tự ngôn từ, nhịp/vần, hình ảnh và cảm xúc. Không biến giờ văn thành cuộc thi tốc độ thuần túy.

## 2. Công nghệ và phạm vi MVP

- Đề xuất: **React + TypeScript + Vite + CSS/Tailwind CSS**; có thể dùng thư viện kéo thả hỗ trợ cả chuột và cảm ứng như `dnd-kit`, miễn vận hành ổn định. Không cần backend trong phiên bản đầu.
- Chạy trên trình duyệt máy tính và thiết bị cảm ứng. Responsive cho màn hình máy chiếu 16:9, laptop và điện thoại.
- **Không yêu cầu tài khoản/đăng nhập/API trả phí/AI**; mọi dữ liệu do giáo viên nhập và lưu cục bộ bằng `localStorage`.
- Hoàn thiện **một luồng sản phẩm end-to-end**: nhập thơ → cấu hình → xem trước → bắt đầu → thẻ bay/xáo trộn → học sinh khôi phục → kiểm tra → hoàn thành → xem bài thơ và câu hỏi đọc hiểu.
- Cung cấp lệnh cài và chạy (`npm install`, `npm run dev`, `npm run build`) và đảm bảo build thành công.

## 3. Thiết kế giao diện (giáo dục + thơ ca)

**Phong cách:** *Sách cổ tích hiện đại*, thanh lịch, có nét thư viện/giấy thơ, không quá trẻ con hoặc rối mắt.

- Bảng màu: nền **kem giấy** `#F7EFD9`, **xanh ngọc** `#377F78`, **vàng mật ong** `#D5A85F`, nâu chữ `#4D4033`; màu phản hồi đúng/sai dễ nhận biết và đủ tương phản.
- Typography: dùng font tiếng Việt rõ ràng, không lỗi dấu; ưu tiên sans-serif dễ đọc cho thẻ; serif thanh lịch cho tiêu đề; không dùng chữ thư pháp khó đọc.
- Trang chủ: tên game, slogan, nút **Tạo màn chơi**, **Bài thơ đã lưu**, **Chơi thử**.
- Trang thiết lập giáo viên: form nhập thơ, lựa chọn cấp độ/chế độ, thời gian, nút **Xem trước**, **Bắt đầu**, **Lưu bài thơ**.
- Màn hình chơi: thanh trên hiển thị tên bài, tiến độ, thời gian, điểm và nút tạm dừng; vùng giữa là **trang thơ với các ô nhận thẻ theo từng dòng**; các thẻ xáo trộn ở **vùng từ thất lạc** xung quanh hoặc phía dưới, không che ô thả.
- Nút dễ nhận thấy: **Gợi ý**, **Kiểm tra**, **Hoàn tác**, **Làm lại**, **Tạm dừng**, **Toàn màn hình**, **Âm thanh bật/tắt**.
- Hiệu ứng: khi nhấn **“Thổi bay vần thơ”**, thẻ xuất phát từ vị trí trong bài thơ rồi bay/đổi vị trí trong **1–2 giây**; khi đặt vào ô có hiệu ứng hút nhẹ (snap); xong một dòng phát sáng dịu; xong bài mở trang sách và hiện thông điệp chúc mừng. Tắt/giảm chuyển động khi thiết bị bật `prefers-reduced-motion`.
- Âm thanh ngắn, tinh tế, tùy chọn tắt; tuyệt đối không để animation gây chóng mặt hoặc khiến thẻ khó bấm.

## 4. Luồng giáo viên

**Đầu vào:**

- Tên bài thơ; tác giả (tùy chọn); trường/lớp (tùy chọn); nội dung thơ gõ/dán **nhiều dòng, nhiều khổ**.
- Tôn trọng xuống dòng, khổ thơ, dấu câu, chữ hoa/chữ thường, dấu tiếng Việt. Loại bỏ dòng trống thừa nhưng giữ ngắt khổ có ý nghĩa.
- Tùy chọn **tách theo tiếng** (mặc định) hoặc **tách theo cụm từ** (có thể nâng cấp: GV tự ngăn cụm bằng dấu `|`). Phân biệt rõ “tiếng” và “từ” trong tiếng Việt.
- Cài mức độ: **Dễ** = xáo trộn khoảng 30% tiếng, **Vừa** = 60%, **Khó** = 100%; giữ nguyên những tiếng còn lại tại ô tương ứng.
- Thời gian: 30 giây, 60 giây, 90 giây, 120 giây, hoặc không giới hạn; có thể tắt chấm điểm thời gian.
- Chế độ kiểm tra: **Kiểm tra từng dòng** hoặc **Kiểm tra toàn bài**.
- Nút **Xem trước** để thấy số dòng, số ô, số thẻ, kiểm tra nội dung trước khi chơi; cảnh báo khi thơ quá dài.
- Lưu, mở lại, đổi tên, sửa, xóa các bài thơ đã lưu trong `localStorage`. Có **Xuất/Nhập JSON** để sao lưu và chia sẻ (nếu khả thi trong MVP).

**Xử lý bài thơ dài:** Đặt giới hạn gợi ý khoảng **12–24 thẻ phải kéo mỗi lượt**, và tự chia bài dài thành các vòng theo dòng/khổ; tránh trải 50 thẻ cùng lúc khiến thẻ chồng nhau và học sinh chỉ tìm chữ thay vì tư duy.

## 5. Luồng học sinh / tương tác bắt buộc

1. Xem tên tác phẩm, luật ngắn gọn, bấm **Bắt đầu**.
2. Hiệu ứng cơn gió đưa các thẻ thuộc phần xáo trộn sang vị trí ngẫu nhiên; vùng thơ chỉ còn các ô trống hoặc thẻ được giữ cố định.
3. Học sinh **kéo một thẻ vào một ô trống**. Nếu ô có thẻ thì cho phép hoán đổi hoặc trả thẻ cũ về kho. Hỗ trợ **thả lại kho**, **đổi vị trí**, **hoàn tác**, **đặt lại**.
4. Hỗ trợ **chạm/click chọn thẻ rồi chạm/click ô đích** như một phương án thay thế kéo thả, đặc biệt hữu ích trên bảng tương tác/thiết bị cảm ứng.
5. **Kiểm tra**: tô rõ những vị trí đúng và vị trí cần xem lại nhưng **không tự chèn đáp án**; cho phép sửa và kiểm tra lại. Có thể tùy chọn chỉ báo số lượng đúng để tăng thử thách.
6. **Gợi ý ba cấp**: (1) hiện chữ đầu dòng/chữ đầu của ô cần thiết; (2) đánh dấu tiếng gieo vần hoặc một vị trí liên quan (chỉ khi đủ căn cứ); (3) chỉ đúng vị trí của một thẻ được chọn. Trừ điểm gợi ý nếu có tính điểm.
7. Khi khớp toàn bộ, hiển thị **bài thơ nguyên văn với đúng dấu câu và ngắt dòng**, hiệu ứng chúc mừng nhẹ và điểm. Hiện câu hỏi đọc hiểu do giáo viên nhập hoặc câu hỏi mặc định “Hình ảnh/từ ngữ nào trong đoạn thơ khiến em ấn tượng nhất? Vì sao?”. Không tự chấm điểm câu hỏi mở.
8. Giáo viên có thể bấm **Hiện đáp án** khi kết thúc hoặc hết giờ (cần xác nhận); có thể **Chơi lại** cùng bài với xáo trộn mới.

## 6. Logic kỹ thuật cần làm đúng

- **Unicode tiếng Việt**: giữ nguyên dấu, không bỏ dấu để so sánh. Chuẩn hóa Unicode NFC khi xử lý nhưng hiển thị đúng văn bản gốc; tách khoảng trắng linh hoạt.
- **Dấu câu** như `, . ! ? : ; “ ” ( )` phải đi kèm thẻ hoặc vị trí hợp lý; đừng biến dấu câu riêng lẻ thành thẻ xáo trộn vô nghĩa. Khi ghép xong phải khôi phục chính xác dấu câu và viết hoa.
- **Từ/tiếng trùng nhau**: mỗi thẻ có ID riêng (ví dụ `token-12`), dù có cùng chữ như “em”, “là”; quản lý theo `tokenId`, `lineIndex`, `slotIndex` để tránh lỗi kéo/chấm.
- **Chấm theo vị trí đúng** của thẻ trong đáp án; khi nhiều thẻ trùng chữ, có thể chấp nhận hoán đổi giữa các thẻ có cùng nội dung hiển thị nếu bài thơ thu được hoàn toàn chính xác (không phạt vì ID khác nhau).
- Shuffle thật sự ngẫu nhiên bằng Fisher–Yates, tránh trạng thái tất cả thẻ đã sẵn đúng chỗ khi bắt đầu; tạo lại bố cục cho mỗi lượt chơi.
- Bố trí thẻ không chồng lấp và không tràn màn hình: dùng layout thích ứng theo kích thước màn hình, có thể là “mây từ” quanh trang thơ trên desktop và khay thẻ cuộn được ở mobile. **Ưu tiên tính dễ thao tác hơn hiệu ứng vật lí phức tạp.**
- Kéo/thả hoặc chọn/đặt trên màn hình cảm ứng không bị xung đột với cuộn trang. Có trạng thái đang kéo/được chọn; phản hồi rõ khi thả sai nơi.
- Lưu trạng thái phiên chơi cục bộ để tránh mất bài khi vô tình tải lại; cho phép khôi phục hoặc bắt đầu mới.
- Tính điểm đề xuất: **80 điểm** khôi phục chính xác, **10 điểm** thưởng thời gian, **10 điểm** câu hỏi đọc hiểu (GV chấm thủ công); nếu không dùng câu hỏi đọc hiểu thì điều chỉnh tổng điểm minh bạch. Không khuyến khích bấm nhanh hơn việc suy luận đúng.

## 7. Chế độ chơi và phạm vi triển khai

**MVP bắt buộc:**

1. **Mảnh ghép vần thơ:** thẻ xáo trộn, kéo thả/chọn-đặt, kiểm tra, gợi ý, chấm điểm, hoàn thành.
2. **Bài thơ mất tích:** chỉ ẩn 30–60% thẻ theo độ khó; những thẻ còn lại cố định.
3. Màn hình giáo viên để nhập và lưu nhiều bài thơ; màn hình chơi chiếu trên lớp; hoạt động được khi không đăng nhập.

**Nâng cấp sau, không trì hoãn MVP vì những tính năng này:**

- **Cơn lốc văn chương:** hoạt ảnh nâng cao kiểu chuyển động vật lí, lựa chọn vị trí thẻ phân tán.
- **Tiếp sức thi sĩ:** luân phiên lượt của 2–4 đội, bảng điểm theo đội, mỗi học sinh chỉ kéo một thẻ/lượt.
- **Giải mã nhịp và vần:** sau khi ghép đúng, đánh dấu tiếng hiệp vần/ngắt nhịp, cho phép GV sửa đánh dấu trước khi chiếu.
- Chế độ nhiều máy kết nối bằng mã phòng (cần backend/realtime, chỉ làm ở giai đoạn sau).

## 8. Ví dụ dữ liệu mặc định và câu hỏi minh họa

**Bài thơ thử nghiệm tự biên soạn** (để có demo chạy sẵn, không dùng văn bản SGK có bản quyền làm dữ liệu mặc định):

```text
Tên: Trang thơ sân trường
Tác giả: Bài thơ minh họa

Nắng lên trên mái sân trường
Trang thơ mở lối yêu thương mỗi ngày
```

Trong chế độ tách theo tiếng, số ô dòng 1 là **6**, dòng 2 là **8**. Cần giữ đúng trật tự 6–8, không tự đổi dấu/cách viết hoa. Câu hỏi đọc hiểu sau màn chơi: **“Em nhận thấy tiếng nào tạo nên vần liên kết giữa hai dòng thơ?”** (định hướng: *trường – thương*).

## 9. Tiêu chí nghiệm thu (acceptance criteria)

Website chỉ được coi là xong khi kiểm tra được đầy đủ:

- [ ] Dán hai dòng thơ mẫu → đúng **6 ô + 8 ô** theo dòng, toàn bộ các tiếng xuất hiện dưới dạng thẻ hoặc đã cố định theo độ khó.
- [ ] Nhấn **Bắt đầu** → các thẻ xáo trộn rõ ràng; không bị che khuất, chồng lấn hoặc rơi ra ngoài vùng tương tác.
- [ ] Kéo thả bằng chuột **và** chạm để chọn/đặt trên điện thoại/bảng tương tác đều hoạt động.
- [ ] Hoán đổi, trả thẻ về kho, hoàn tác, làm lại và kiểm tra đáp án hoạt động thực tế.
- [ ] Trộn nhiều tiếng giống nhau và bài có dấu câu vẫn chấm đúng, không làm hỏng văn bản gốc.
- [ ] Nhập thơ dài → hệ thống chia thành lượt hợp lý, không vỡ bố cục.
- [ ] Đúng toàn bộ → màn hình thành công, thơ nguyên vẹn, điểm và câu hỏi đọc hiểu hiện ra.
- [ ] Dữ liệu bài thơ đã lưu vẫn tồn tại sau khi reload trang; có thể chỉnh sửa/xóa.
- [ ] Responsive trên laptop, màn hình 16:9, điện thoại; tiếng Việt hiển thị không lỗi font.
- [ ] Giao diện có đủ trạng thái loading/empty/error và nút quay lại; không có nút giả hoặc chức năng chỉ là hình ảnh.
- [ ] `npm run build` thành công, không lỗi TypeScript nghiêm trọng.

## 10. Kết quả cần bàn giao

- Toàn bộ **source code dự án**, cây thư mục rõ ràng.
- Một bản chạy thử có nội dung mẫu, luồng giáo viên và học sinh hoạt động đầy đủ.
- Hướng dẫn chạy trên máy local và **triển khai website** (ví dụ Vercel/Netlify), ưu tiên dễ chia sẻ bằng một link.
- README ngắn: cách nhập thơ, chỉnh độ khó, bắt đầu chơi, lưu lại bài, điều khiển khi trình chiếu.

**Quy tắc quyết định:** Nếu phải đánh đổi, hãy ưu tiên **kéo thả chính xác → khả năng xử lý tiếng Việt → hiển thị đẹp trên máy chiếu → lưu dữ liệu → hiệu ứng**. Không hy sinh vận hành thật để lấy animation phức tạp.
