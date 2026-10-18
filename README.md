# HSK cùng Tiểu Huyền · 小玄汉语课堂

Website học từ vựng HSK 1–3 của **Tiếng Trung Tiểu Huyền**. Đây là trang tĩnh, đưa lên GitHub Pages là chạy, không cần máy chủ.

## Đưa lên GitHub Pages (khoảng 5 phút)

1. Giải nén file `hsk-tieu-huyen.zip`, được thư mục `hsk-tieu-huyen`.
2. Đăng nhập GitHub, bấm **New repository**. Đặt tên (ví dụ `hsk`), chọn **Public**, bấm **Create repository**.
3. Trong trang repository vừa tạo, bấm **uploading an existing file**.
4. Mở thư mục `hsk-tieu-huyen`, chọn **file `index.html` và thư mục `audio`** (có thể kèm README.md), kéo thả cùng lúc vào trang GitHub. Chờ tải xong rồi bấm **Commit changes**.
   - `index.html` đã chứa sẵn toàn bộ từ vựng, câu ví dụ, bộ thủ và dữ liệu nét viết. Thư mục `audio` chứa âm thanh (39 file).
   - Kéo hai mục này từ *bên trong* thư mục, không kéo cả thư mục `hsk-tieu-huyen`, để `index.html` nằm ngay ở gốc repository.
   - Âm thanh không nhúng được vào `index.html` vì GitHub chỉ nhận file tối đa 25 MB khi tải qua trình duyệt.
5. Vào **Settings → Pages**. Ở mục **Branch** chọn `main`, thư mục `/ (root)`, bấm **Save**.
6. Chờ 1–2 phút rồi tải lại trang Settings → Pages. Link trang sẽ có dạng `https://<tên-tài-khoản>.github.io/hsk/`.

## Nếu trang báo không tải được âm thanh

- Mở repository trên GitHub, kiểm tra có thư mục `audio` với 39 file `h1-00.mp3` … `h3-16.mp3` chưa. Nếu chưa có: **Add file → Upload files**, kéo cả thư mục `audio` vào (trên máy tính, trình duyệt Chrome hoặc Edge), bấm **Commit changes**.
- Nếu lỡ tải 39 file MP3 thẳng vào gốc repository (không nằm trong thư mục `audio`), trang vẫn tự tìm được, không cần sửa.
- Mở trang qua link GitHub Pages (`https://…github.io/…`). Bấm đúp mở file `index.html` ngay trên máy thì trình duyệt chặn đọc âm thanh.
- Sau khi tải file lên, chờ 1–2 phút để GitHub Pages cập nhật rồi tải lại trang (Ctrl + F5).
- Khi thiếu file âm thanh, trang báo rõ thiếu file nào và tạm dùng giọng đọc tiếng Trung của trình duyệt.

## Cập nhật sau này

- Cập nhật trang: chỉ cần tải lên file `index.html` mới để thay file cũ (giữ nguyên thư mục `audio`).
- Dữ liệu từ vựng nằm trong `index.html`, ở các khối `<script type="application/json" data-path="data/hsk1.json">` (tương tự cho hsk2, hsk3). Nếu đặt các file `data/hsk1.json`… vào repository thì dữ liệu nhúng trong `index.html` vẫn được ưu tiên. Mỗi từ có các trường `h` (chữ Hán), `p` (pinyin), `s` (danh sách [từ loại, nghĩa]), `f` (các dạng phát âm), `x` (câu ví dụ: `z` chữ Hán, `p` pinyin, `v` nghĩa, `s` nguồn `doc` = tài liệu / `th` = biên soạn thêm).
- Âm thanh được gộp trong `audio/h1-00.mp3`, `audio/h2-00.mp3`… Mỗi file chứa 60 từ. Trang đọc từng đoạn theo vị trí ghi trong dữ liệu (`#vị-trí+độ-dài`), nên không đổi tên hay cắt ghép các file này bằng tay.

## Cấu trúc

| Đường dẫn | Nội dung |
|---|---|
| `index.html` | Giao diện, chức năng và toàn bộ dữ liệu: từ vựng HSK 1–3, câu ví dụ, bộ thủ, cấu tạo chữ, thứ tự nét |
| `audio/` | Âm thanh từ và câu ví dụ (39 file MP3 gộp, mỗi file 60 từ) |

## Giới hạn

- Tiến độ học lưu trong trình duyệt của từng máy (localStorage). Không có đăng nhập, không đồng bộ giữa các máy, giáo viên chưa xem được tiến độ học viên. Những tính năng đó cần máy chủ và cơ sở dữ liệu.
- Trang cần mạng để tải phông chữ (Google Fonts) và thư viện nét viết Hanzi Writer (jsDelivr). Không có mạng thì phông chữ dự phòng vẫn hiển thị đúng, nhưng phần thứ tự nét không chạy.

## Nguồn và giấy phép

- Từ vựng: file HSK1, HSK2 (CTI HSK) và file tổng hợp từ vựng HSK 3.0 cấp 1–5 kèm ví dụ do giáo viên cung cấp.
- Bản ghi phát âm: [audio-cmn](https://github.com/hugolpz/audio-cmn), giấy phép CC BY-SA (giọng Yue Tan – Shtooka, Chen Wang).
- Giọng máy cho câu ví dụ: mô hình MeloTTS (qua sherpa-onnx). Kiểm tra tự động bằng sherpa-onnx Paraformer.
- Thứ tự nét: [Hanzi Writer](https://hanziwriter.org) (MIT) với dữ liệu [Make Me a Hanzi](https://github.com/skishore/makemeahanzi) (Arphic Public License; dictionary.txt LGPL).
