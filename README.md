# QUY ĐỊNH & HƯỚNG DẪN ĐĂNG SƠ ĐỒ DFD VÀO DỰ ÁN

> **QUY TẮC CỐT LÕI CHO THÀNH VIÊN:**  
> 1. 
> 2. Khi vẽ xong sơ đồ DFD, bắt buộc phải **UP ẢNH VÀO THƯ MỤC `diagram/`**.  
> 3. Sau khi up ảnh xong, phải **MENTION VÀO ĐÚNG VỊ TRÍ TRONG FILE `dacta.md`**.

---

## 1. CÔNG CỤ VẼ ĐỀ XUẤT
Thành viên có thể sử dụng bất kỳ công cụ nào để vẽ DFD:
- **Draw.io (Khuyên dùng):** [https://app.diagrams.net/](https://app.diagrams.net/)
- **Visual Paradigm / Lucidchart / Canva / Visio**

---

## 2. QUY CHUẨN ĐẶT TÊN ẢNH
Tất cả ảnh sơ đồ phải được lưu dưới dạng file `.png`, đặt tên theo mã chức năng để không bị trùng lặp:

```
diagram/
 ├── [ma_chuc_nang]_context.png   # Ảnh DFD Mức ngữ cảnh
 ├── [ma_chuc_nang]_level1.png    # Ảnh DFD Mức đỉnh
 └── [ma_chuc_nang]_level2.png    # Ảnh DFD Mức dưới đỉnh
```

*Ví dụ cụ thể:*
- Với chức năng Đặt hàng:
  - `DatHang_context.png`
  - `DatHang_level1.png`
  - `DatHang_level2.png`

---

## 3. QUY TRÌNH 3 BƯỚC: VẼ -> UP ẢNH -> MENTION VÀO `dacta.md`

### Bước 1: Vẽ sơ đồ & Xuất ảnh
- Vẽ đầy đủ 3 mức sơ đồ cho chức năng mình phụ trách:
  1. Mức ngữ cảnh (Context Level)
  2. Mức đỉnh (Level 1)
  3. Mức dưới đỉnh (Level 2)
- Chụp ảnh màn hình rõ nét vùng sơ đồ 

---

### Bước 2: Up ảnh vào thư mục `diagram/`
- Đổi tên file ảnh đúng theo chuẩn ở **Mục 2**.
- Upload các file ảnh vừa xuất vào thư mục:  
  📁 `diagram/` (nằm ở thư mục gốc của dự án).

---

### Bước 3: Mention (nhúng link ảnh) vào file `dacta.md`
- Mở file `dacta.md`.
- Kéo xuống **Mục 3 (Xây dựng mô hình DFD cho từng chức năng)**.
- Tại phần chức năng mà bạn phụ trách, **mention file ảnh** (đưa tên là được)


## 4. CHECKLIST KIỂM TRA TRƯỚC KHI PUSH CODE / NỘP BÀI
- [ ] Ảnh sơ đồ đã nằm trong thư mục `diagram/`.
- [ ] Tên file ảnh đúng cú pháp không dấu
- [ ] Đã **mention** đầy đủ link 3 mức sơ đồ vào đúng mục chức năng trong `dacta.md`.
- [ ] Đã trả lời đủ câu hỏi phân tích ở mục 3.1 trong `dacta.md`.
- [ ] Preview file `dacta.md` ảnh hiển thị rõ ràng, không bị lỗi gãy ảnh.
 ksdjfkasbdjkf
 sbfjasdjkfas
 bsdajfsadnkj