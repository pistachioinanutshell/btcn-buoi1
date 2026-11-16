# AI Usage Log

## 1. Công cụ AI

**Tên công cụ:** Claude (Anthropic), model Claude Opus 5.5, sử dụng qua giao diện claude.ai.

## 2. Mục đích sử dụng

- Phân tích giao diện website The Craft House từ ảnh chụp màn hình tôi cung cấp.
- Lập bảng khảo sát 5 khu vực: trang chủ, danh mục, chi tiết sản phẩm, tìm kiếm, giỏ hàng.
- Chọn phương án cải tiến đơn giản nhất và đề xuất bố cục giao diện.
- Tạo mã HTML/CSS cho thẻ sản phẩm mới.
- Giải thích phương án thiết kế: thành phần HTML, cách tổ chức CSS, responsive, khả năng sử dụng.
- Tách CSS thành file riêng và soạn README, AI_USAGE.

## 3. Prompt đã sử dụng

**Prompt 1 – Khảo sát website** (kèm 6 ảnh chụp: trang chủ, menu Board Games, chi tiết Islandopoly, tìm kiếm, giỏ hàng, thanh toán):

> Đóng vai trò là người dùng đang tìm mua sản phẩm board games, và bạn tìm thấy website The Craft House (https://thecrafthouse.vn/?country=VN) có các sản phẩm đáp ứng nhu cầu của bạn. Hãy trải nghiệm 5 hạng mục của website này, gồm: Trang chủ - Danh mục sản phẩm (Boardgames) - Chi tiết sản phẩm - Tìm kiếm - Giỏ hàng (xem hình UI/UX đính kèm) và đưa ra các đánh giá và khảo sát. Với mỗi khu vực, bạn cần ghi nhận: 1. Chức năng đang được cung cấp. 2. Điểm hợp lý trong thiết kế. 3. Điểm có thể cải thiện. 4. Đề xuất cải tiến và lý do. Output: một bảng khảo sát ngắn, tối thiểu năm dòng tương ứng với năm khu vực.

**Prompt 2 – Rút gọn bảng khảo sát** (kèm ảnh mẫu trình bày):

> Rút ngắn nội dung lại, viết tóm tắt thôi vì yêu cầu mỗi khu vực chỉ có 1 gạch đầu dòng. Xem ví dụ hình đính kèm về cách trình bày.

**Prompt 3 – Chọn phương án và tạo mã nguồn:**

> Hãy chọn một chức năng hoặc khu vực giao diện để cải tiến cho website The Craft House (chọn phương án đơn giản nhất). Giới hạn: chỉ cần HTML/CSS và một trang web có thể chạy được. Các bước: 5.1 Xác định vấn đề, 5.2 Đề xuất giao diện, 5.3 Tạo mã nguồn.

**Prompt 4 – Chỉnh sửa trang:**

> Bỏ phần [danh sách 5 thay đổi chính] ra khỏi file html.

**Prompt 5 – Báo cáo và tách CSS:**

> Bổ sung báo cáo cho 3 mục: (1) Xác định vấn đề – tại sao chọn cải thiện cái này (3–5 dòng); (2) Trình bày đề xuất giao diện gồm bố cục, thành phần HTML, cách tổ chức CSS, hiển thị trên máy tính và điện thoại, những điểm cần kiểm tra về khả năng sử dụng; (3) Tách mã CSS thành file riêng.

**Prompt 6 – Tài liệu nộp bài:**

> Viết file AI_USAGE và README theo yêu cầu của giảng viên.

## 4. Kết quả AI đề xuất

**Bảng khảo sát.** AI lập bảng 5 khu vực (thêm 1 dòng về trang thanh toán), sau đó rút gọn còn một ý cho mỗi ô. Các vấn đề chính AI nêu ra:

| Khu vực | Vấn đề chính |
|---|---|
| Trang chủ | Hero không nhắc đến board game |
| Danh mục | Không có trang danh mục và bộ lọc |
| Chi tiết sản phẩm | Thiếu số người chơi, độ tuổi; hiển thị "0.0 ★" khi chưa có đánh giá |
| Tìm kiếm | Trạng thái rỗng không có gợi ý; giao diện tiếng Anh |
| Giỏ hàng | Định dạng tiền không thống nhất; thiếu mã giảm giá và gói quà |

**Phương án cải tiến.** AI chọn "Thiết kế lại thẻ sản phẩm" vì đây là thành phần nhỏ nhất nhưng được dùng ở nhiều trang. Thẻ đề xuất gồm:

- Ảnh 1:1 kèm nhãn "Bán chạy".
- Danh mục.
- Tên tối đa 2 dòng.
- Giá.
- Trạng thái freeship.
- Nút "Thêm vào giỏ".

**Mã nguồn.** Trang HTML5/CSS3 có 8 sản phẩm mẫu (tên và giá lấy từ ảnh chụp website), lưới responsive 4/3/2 cột và hỗ trợ chế độ tối. Hình sản phẩm được vẽ bằng SVG để không dùng ảnh có bản quyền. Trang không có JavaScript hay thư viện.

**Lỗi AI tự phát hiện và sửa.** Khi chụp thử giao diện điện thoại, AI phát hiện nút "Thêm vào giỏ" của thẻ Bài Tây bị lệch so với thẻ bên cạnh. Nguyên nhân là quy tắc `.card-ship + .card-btn { margin-top: 14px; }` ghi đè `margin-top: auto`. AI đã sửa bằng cách chuyển khoảng cách sang `margin-bottom` của `.card-ship`.

## 5. Kiểm tra và điều chỉnh

**Những điểm tôi đã điều chỉnh:**

- **Bảng khảo sát:** bản đầu của AI quá dài so với yêu cầu. Tôi yêu cầu rút gọn còn một ý mỗi ô, theo mẫu trình bày tôi cung cấp.
- **Trang demo:** tôi bỏ khối danh sách "5 thay đổi chính" trong phần so sánh. Nội dung này đã có trong báo cáo, không cần lặp lại trên giao diện.
- **CSS:** tôi yêu cầu tách CSS từ thẻ `<style>` ra file riêng. Các style viết trực tiếp trong HTML (màu nền ảnh từng thẻ) được đổi thành class `.tile-*` trong `style.css`.
- **Cấu trúc thư mục:** tổ chức lại theo đề bài, gồm `index.html` và `css/style.css`.

**Những điểm đối chiếu với website thật** (theo yêu cầu "không xem câu trả lời của AI là kết quả khảo sát nếu chưa kiểm tra"):

- [ ] Khoảng trắng lớn trên trang chủ: AI chỉ nhận xét từ ảnh chụp và lưu ý có thể do hiệu ứng cuộn chưa tải. Cần kiểm tra lại trên website thật.
- [ ] Tìm kiếm có gợi ý tức thời, có hỗ trợ gõ không dấu không: AI không kiểm chứng, chỉ đưa ra như đề xuất. Cần gõ thử "co ty phu" trên website.
- [ ] Trang danh mục và bộ lọc: AI chỉ thấy mega menu trong ảnh chụp. Cần kiểm tra xem bấm vào tiêu đề nhóm có mở trang danh mục không.
- [ ] Phương thức thanh toán ngoài Payoo (mục "+2" trong ảnh checkout): cần kiểm tra trên website.

**Những phần không sử dụng:**

- Dòng khảo sát trang thanh toán chỉ là phần bổ sung, không đưa vào bảng 5 khu vực chính.
- Hình minh họa SVG chỉ dùng cho bản demo. Khi dùng thật, cần thay bằng ảnh sản phẩm do cửa hàng cung cấp.

**Tự kiểm tra trên trình duyệt** (tôi tự điền sau khi chạy thử):

- [ ] Mở `index.html` trên Chrome, giao diện hiển thị đúng.
- [ ] Chrome DevTools, chế độ thiết bị: máy tính (1280px) 4 cột, tablet (768px) 3 cột, điện thoại (375px) 2 cột.
- [ ] Giá và nút "Thêm vào giỏ" thẳng hàng giữa các thẻ.
- [ ] Dùng phím Tab đi qua các link và nút, thấy khung focus.
- [ ] Điểm tôi tự phát hiện và sửa thêm: `[ghi lại ở đây]`

## 6. Phần tôi hiểu và có thể giải thích

- **Cấu trúc HTML:** `<header>`, `<main>` và `<section>` chia vùng trang. Mỗi sản phẩm là một `<article class="card">`, vì mỗi thẻ là một nội dung độc lập. Tên sản phẩm dùng `<h3>` để giữ phân cấp tiêu đề. Nút dùng `<button type="button">`.
- **Lưới responsive:** `.grid` dùng `display: grid` với `repeat(4, minmax(0, 1fr))`, và media query đổi sang 3 cột (dưới 1000px) rồi 2 cột (dưới 680px).
- **Nút luôn nằm đáy thẻ:** `.card` và `.card-body` dùng `display: flex; flex-direction: column`. Nút có `margin-top: auto` nên đẩy xuống đáy, kể cả khi tên sản phẩm ngắn.
- **Giới hạn tên 2 dòng:** `-webkit-line-clamp: 2` cắt tên dài. `min-height: calc(1.35em * 2)` giữ chiều cao cố định để giá thẳng hàng.
- **Ảnh vuông:** `aspect-ratio: 1 / 1` trên `.card-media`. Màu nền mỗi ảnh lấy từ biến `--tile`, khai báo trong các class `.tile-*`.
- **Biến màu:** mọi màu khai báo trong `:root`. `@media (prefers-color-scheme: dark)` đổi sang bộ màu tối.
- **Hình SVG dùng lại:** mỗi hình vẽ một lần trong `<symbol id="...">`, sau đó gọi lại bằng `<use href="#...">`.
- **Khả năng tiếp cận:** `aria-label` mô tả link ảnh, `aria-hidden="true"` ẩn hình trang trí khỏi trình đọc màn hình, `:focus-visible` hiện khung khi dùng bàn phím, `prefers-reduced-motion` tắt hiệu ứng chuyển động.
