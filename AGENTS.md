# Quy tắc sơ đồ Mermaid

- Lưu mỗi sơ đồ Mermaid thành tệp `.md` trong `diagram/`, với phần sơ đồ nằm trong khối mã có nhãn `mermaid` để Markdown preview có thể render.
- Không lưu sơ đồ mới dưới dạng tệp `.mmd` độc lập.
- Gắn liên kết tới tệp `.md` ở đúng mục chức năng và cấp DFD trong `dacta.md`.
- Dùng lại ID kho dữ liệu dùng chung đã có; không cấp cùng một ID cho hai kho dữ liệu khác nhau.

## Quy tắc mã màu DFD trong Visual Paradigm

- Thực thể ngoài dùng màu nền xanh tím nhạt `#E6ECFF` (RGB `230, 236, 255`), theo sơ đồ DFD bán hàng mức 0.
- Tiến trình dùng màu xanh cyan nhạt `#E1F6FF` (RGB `225, 246, 255`); phần thân tiến trình để trắng như sơ đồ mẫu.
- Kho dữ liệu giữ màu mặc định của Visual Paradigm; không tự đặt màu cho kho dữ liệu.
- Viền và chữ màu đen theo mặc định của sơ đồ mẫu.

## Quy tắc số lần xuất hiện trong DFD

- Trong mỗi sơ đồ DFD, mỗi thực thể ngoài và mỗi kho dữ liệu chỉ được vẽ một lần.
- Không tạo hình lặp của cùng một thực thể hoặc kho dữ liệu để giảm giao cắt; điều chỉnh bố cục và đường nối thay thế.
- Một thực thể hoặc kho dữ liệu có thể xuất hiện ở các sơ đồ/cấp DFD khác nhau; giữ nguyên tên và ID dùng chung giữa các sơ đồ.
