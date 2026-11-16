# E-commerce UI Improvement

## 1. Giới thiệu

Dự án cải tiến **thẻ sản phẩm** (product card) cho website The Craft House, một cửa hàng trực tuyến bán board game, đồ trang trí nhà cửa và quà tặng thủ công.

Trang demo hiển thị lưới 8 board game bán chạy với thẻ sản phẩm mới. Cuối trang có phần so sánh thẻ hiện tại của website với thẻ đề xuất.

## 2. Website tham khảo

- **Tên website:** The Craft House VN
- **URL:** https://thecrafthouse.vn/?country=VN
- **Khu vực đã khảo sát:**
  - Trang chủ
  - Danh mục sản phẩm (menu Board Games)
  - Chi tiết sản phẩm (Cờ Tỷ Phú Islandopoly)
  - Tìm kiếm
  - Giỏ hàng (bổ sung thêm trang thanh toán)

## 3. Chức năng

- Hiển thị danh sách sản phẩm dạng lưới.
- Mỗi thẻ hiển thị hình ảnh, danh mục, tên, giá, trạng thái miễn phí giao hàng và nút "Thêm vào giỏ".
- Nhãn "Bán chạy" cho các sản phẩm nổi bật.
- Bố cục hỗ trợ nhiều kích thước màn hình: 4 cột trên máy tính, 3 cột trên tablet, 2 cột trên điện thoại.
- Tự đổi màu theo chế độ sáng/tối của thiết bị.
- Phần so sánh thẻ sản phẩm cũ và mới.

## 4. Công nghệ

- HTML5
- CSS3: CSS Grid, Flexbox, CSS Variables, Media Queries
- Font Be Vietnam Pro (Google Fonts), có font dự phòng nếu không tải được
- Hình minh họa sản phẩm vẽ bằng SVG ngay trong HTML, không dùng ảnh có bản quyền của website gốc
- Không dùng JavaScript, thư viện, backend hay cơ sở dữ liệu

## 5. Cách chạy

Mở file `index.html` bằng trình duyệt (Chrome, Edge, Firefox hoặc Safari). File `css/style.css` phải nằm đúng thư mục `css/` cạnh `index.html`.

Xem bản trực tuyến: `[dán link GitHub Pages tại đây]`

Cấu trúc thư mục:

```
ecommerce-ui-improvement/
├── index.html
├── css/
│   └── style.css
├── README.md
└── AI_USAGE.md
```

Dự án không có thư mục `images/` vì hình sản phẩm được vẽ bằng SVG ngay trong `index.html`.

## 6. Cải tiến đã thực hiện

**Vấn đề ban đầu.** Thẻ sản phẩm trên trang chủ The Craft House có các hạn chế sau:

- Chỉ có ảnh, tên và giá, không có nút mua. Khách phải mở trang chi tiết mới thêm được vào giỏ.
- Ảnh không đồng nhất: có thẻ dùng ảnh lifestyle, có thẻ dùng ảnh nền trắng.
- Tên dài xuống dòng không đều nên giá bị lệch hàng giữa các thẻ.
- Thẻ không cho biết loại sản phẩm hay sản phẩm có được miễn phí giao hàng không.

**Thay đổi đã thực hiện:**

- Thêm nút "Thêm vào giỏ" luôn nằm sát đáy thẻ (Flexbox kết hợp `margin-top: auto`).
- Ảnh tỷ lệ 1:1 (`aspect-ratio`) trên nền màu đồng nhất.
- Giới hạn tên tối đa 2 dòng (`line-clamp`) để giá và nút thẳng hàng giữa các thẻ.
- Thêm dòng danh mục và trạng thái freeship (đơn từ 500.000₫).
- Giá in đậm với màu cam đậm hơn, đủ tương phản theo chuẩn WCAG AA.
- Lưới responsive 4/3/2 cột; nút cao tối thiểu 42px để dễ chạm trên điện thoại.

## 7. Hỗ trợ từ AI

AI (Claude của Anthropic) đã hỗ trợ các phần sau:

- Phân tích ảnh chụp 5 khu vực của website và lập bảng khảo sát.
- Đề xuất phương án thiết kế thẻ sản phẩm.
- Tạo mã HTML/CSS.
- Tách CSS thành file riêng.

Tôi đã kiểm tra, điều chỉnh và bổ sung các phần sau:

- Rút gọn bảng khảo sát theo đúng mẫu yêu cầu.
- Bỏ phần danh sách thay đổi khỏi trang demo.
- Yêu cầu tách CSS và tổ chức lại thư mục.
- Kiểm tra giao diện trên trình duyệt.

Chi tiết xem trong file [AI_USAGE.md](AI_USAGE.md).
