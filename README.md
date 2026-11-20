# 📐 Phần mềm học Hình học 8

Ứng dụng web **một file** (`index.html`) giúp học Hình học lớp 8 theo cách trực quan: kéo thanh trượt, kéo điểm trên hình, xem lời giải từng bước, luyện tập, ôn thẻ nhớ và làm bài kiểm tra. Không cần cài đặt, không cần mạng sau khi tải xong, không gửi dữ liệu đi đâu.

## Có gì trong ứng dụng

| Khu vực | Mục | Nội dung |
|---|---|---|
| 📘 Học | Bài học | 10 bài từ tứ giác đến tam giác đồng dạng, hình vẽ thay đổi theo thanh trượt |
| | Kéo & khám phá | 5 mô hình kéo điểm (hình bình hành, đường trung bình, Talet, tổng 4 góc, Pythagore) |
| | Hình khối | Hộp, lập phương, lăng trụ, chóp, xoay 3D, tính V, Sxq, Stp |
| | Thẻ nhớ | Ôn ngắt quãng 47 thẻ kiến thức |
| 🧩 Giải bài | Giải từng bước | 10 bài cơ bản |
| | Dạng toán | Học kì 1, nâng cao và chuyên đề (45 bài giải từng bước có hình vẽ thêm dần) |
| | Chuyên đề | Chuyên đề 1 và 2 (tam giác cân, tam giác đều, hình vuông) kèm đề tự luyện |
| 🎲 Luyện & thi | Luyện tập | 10 dạng đề tự sinh số, có gợi ý |
| | Kiểm tra | 12 câu trắc nghiệm, chấm điểm và gợi ý ôn chỗ yếu |
| 🗓️ Lộ trình | Lộ trình, Tra cứu | Kế hoạch 8 tuần, cơ sở dữ liệu kiến thức |

Có chế độ **sáng/tối tự động** theo máy, nút **A− / A+** chỉnh cỡ chữ, và hệ thống XP, chuỗi đúng, cấp độ.

## Chạy trên máy của bạn

Cách nhanh nhất: bấm đúp vào `index.html` (mở bằng Chrome, Edge, Firefox hoặc Safari).

Hoặc chạy một máy chủ nhỏ (cần Python):

```bash
cd hinh-hoc-8
python -m http.server 8000
# mở http://localhost:8000
```

## Đăng lên GitHub Pages

**Cách 1: chỉ dùng trình duyệt (dễ nhất)**

1. Đăng nhập GitHub, bấm **New repository**, đặt tên (ví dụ `hinh-hoc-8`), chọn **Public** (GitHub Pages miễn phí cho repo công khai), bấm **Create**.
2. Bấm **uploading an existing file**, kéo thả **tất cả file trong thư mục này** (`index.html`, `.nojekyll`, `README.md`, thư mục `.github`), bấm **Commit changes**.
3. Vào **Settings → Pages → Build and deployment → Source: Deploy from a branch**, chọn nhánh `main`, thư mục `/ (root)`, bấm **Save**.
4. Đợi 1 đến 2 phút. Địa chỉ trang sẽ là `https://<tên-tài-khoản>.github.io/hinh-hoc-8/`.

**Cách 2: tự động bằng GitHub Actions** (đã kèm file `.github/workflows/pages.yml`)

1. Làm bước 1 và 2 như trên.
2. Vào **Settings → Pages → Source: GitHub Actions**.
3. Mỗi lần bạn đẩy file mới lên nhánh `main`, trang tự cập nhật. Xem tiến trình ở tab **Actions**.

**Cách 3: dùng dòng lệnh**

```bash
cd hinh-hoc-8
git init -b main
git add .
git commit -m "Phần mềm học Hình học 8"
git remote add origin https://github.com/<tên-tài-khoản>/hinh-hoc-8.git
git push -u origin main
```

Sau đó bật Pages như cách 1 (bước 3) hoặc cách 2 (bước 2).

## Lưu ý

- **Tiến độ học** (XP, bài đã xem, thẻ nhớ, lộ trình, điểm thi cao nhất) lưu trong `localStorage` của trình duyệt, nên mỗi máy và mỗi trình duyệt có dữ liệu riêng. Xóa dữ liệu duyệt web hoặc dùng chế độ ẩn danh thì mất tiến độ.
- Ứng dụng **không dùng thư viện hay font từ bên ngoài**, nên chạy được cả khi offline.
- **Bản quyền nội dung:** phần Chuyên đề được diễn đạt và vẽ lại theo tài liệu PDF "Các chuyên đề nâng cao Toán hình lớp 8" do người dùng cung cấp (đề bài và hướng dẫn giải bám theo tài liệu). Phần sơ đồ nhận dạng các hình và một số bài lý thuyết tham khảo tài liệu của thầy Nguyễn Chí Thành. Trước khi để repo ở chế độ công khai, bạn nên kiểm tra quyền sử dụng các tài liệu gốc, hoặc để repo ở chế độ riêng tư (Private) và chỉ chia sẻ cho người cần dùng.

## Cấu trúc file

```
hinh-hoc-8/
├── index.html              # toàn bộ ứng dụng (HTML + CSS + JavaScript + dữ liệu)
├── README.md               # file này
├── .nojekyll               # báo GitHub Pages đừng xử lý bằng Jekyll
└── .github/workflows/pages.yml   # tự động đăng lên GitHub Pages (tùy chọn)
```

## Chỉnh sửa nội dung

Mọi dữ liệu nằm ngay trong `index.html`, trong thẻ `<script>`:

| Biến | Nội dung |
|---|---|
| `L` | 10 bài học tương tác (tab Học) |
| `X` | 10 bài giải từng bước cơ bản (tab Giải từng bước) |
| `Z` | 45 bài giải từng bước có ký hiệu góc, cạnh (tab Dạng toán và Chuyên đề) |
| `CDS` | Lý thuyết, các dạng, đề tự luyện của Chuyên đề |
| `D` | 47 mục kiến thức (tab Tra cứu và Thẻ nhớ) |
| `Q` | 24 câu hỏi kiểm tra |
| `PL` | Các việc trong lộ trình 8 tuần |

Một bài trong `Z` có dạng:

```js
{g:'CĐ2', n:'Tên bài', nd:'Nhận dạng', cc:'Công cụ', loi:'Lỗi hay gặp',
 P:{A:[x,y], B:[x,y], ...},            // tọa độ các điểm (khung 400 x 250)
 E:{q:['g','ABC'],                      // 'g' đa giác, 'l' đoạn thẳng, 'p' điểm có nhãn,
    ra:['r','BAC'],                     // 'r' góc vuông, 'a' cung góc, 'k' vạch bằng nhau,
    ...},                               // 'pa' mũi tên song song, 't' chữ
 S:[{s:'Lời giải bước 1', a:['q'], h:['q']},   // a: hiện thêm, h: tô đỏ, d: ẩn bớt
    ...]}
```

Trong lời giải có thể viết phân số bằng `{tử|mẫu}` và góc bằng `∠ABC` (tự hiện dấu mũ).

## Giấy phép

Chưa chọn giấy phép. Hãy thêm file `LICENSE` phù hợp (ví dụ MIT cho phần mã) sau khi bạn kiểm tra bản quyền nội dung như ghi ở trên.
