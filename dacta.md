# ĐẶC TẢ HỆ THỐNG

## 1. Liệt kê các chức năng và đặc tả quy trình hoạt động, xử lý của hệ thống

### 1.1. Danh sách các chức năng
1. Chức năng Nhập hàng
2. Chức năng Quản lý Kho
3. Chức năng Bán Hàng
4. Chức năng Quản lý Nhân Viên và Cộng Tác Viên
5. Chức năng Quản lý Giải Đấu và Tài Trợ Sự Kiện

### 1.2. Đặc tả quy trình hoạt động và xử lý

#### Chức năng: Nhập hàng
- **Mục đích:** Quản lý quy trình mua hàng từ nhà cung cấp, kiểm đếm số lượng, chất lượng và cập nhật dữ liệu nhập kho vào hệ thống.
- **Đối tượng thực hiện:** Quản lý cửa hàng, Nhân viên mua/nhập hàng.
- **Quy trình hoạt động & xử lý:**  
  Quy trình nhập hàng bắt đầu khi nhân viên kiểm tra lượng tồn kho và nhận thấy các mặt hàng phụ kiện  chạm mức tối thiểu, từ đó tiến hành lập đơn đặt hàng  gửi đến nhà cung cấp. Khi nhận được hàng bàn giao, nhân viên kho cùng quản lý tiến hành đối chiếu với hóa đơn chứng từ, kiểm tra thực tế số lượng, chất lượng bao bì và tính toàn vẹn của từng sản phẩm. Nếu lô hàng đạt chuẩn, nhân viên tạo phiếu nhập kho trên hệ thống để ghi nhận công nợ và tự động cập nhật tăng số lượng tồn kho theo thời gian thực. Trường hợp phát hiện hàng hóa không đạt chuẩn hoặc thiếu hụt số lượng, nhân viên sẽ lập biên bản sự cố ngay tại chỗ để từ chối nhận hoặc yêu cầu nhà cung cấp thực hiện đổi trả.

#### Chức năng: Quản lý Kho
- **Mục đích:** Theo dõi chính xác lượng hàng tồn kho tại cửa hàng và các điểm phân phối, quản lý vị trí lưu trữ, điều phối xuất chuyển hàng cho cộng tác viên ở các khu vực và kiểm soát thất thoát hàng hóa.
- **Đối tượng thực hiện:** Nhân viên kho, Quản lý cửa hàng.
- **Quy trình hoạt động & xử lý:**  
  Quy trình quản lý kho vận hành liên tục nhằm kiểm soát biến động hàng hóa tại kho chính và các điểm lưu trữ của cộng tác viên ở xa. Mỗi khi phát sinh giao dịch nhập hàng, bán lẻ, xuất chuyển cho cộng tác viên hoặc xuất thưởng giải đấu, hệ thống sẽ tự động cập nhật số lượng tồn kho theo thời gian thực. Khi cộng tác viên tại các khu vực khác có nhu cầu lấy hàng về bán, nhân viên kho lập phiếu xuất kho chuyển hàng gắn theo mã số của cộng tác viên đó, hệ thống sẽ tự động trừ lượng tồn tại kho chính và ghi nhận số lượng chuyển vào kho ký gửi của cộng tác viên. Định kỳ, nhân viên thực hiện quét mã kiểm kê thực tế tại quầy và đối chiếu số lượng hàng ký gửi từ xa để phát hiện sai lệch, hàng hư hỏng nhằm xử lý thất thoát. Trường hợp cộng tác viên không bán hết hoặc đổi trả, kho sẽ lập phiếu nhập hoàn để thu hồi hàng về kho chính.

#### Chức năng: Bán Hàng
- **Mục đích:** Quản lý và xử lý toàn diện quy trình bán hàng đa kênh bao gồm bán trực tiếp tại quầy và bán hàng trực tuyến (qua trang mạng, kênh bán hàng); tính tiền, áp dụng ưu đãi, xác nhận thanh toán, đóng gói giao vận và in hóa đơn cho khách hàng.
- **Đối tượng thực hiện:** Thu ngân, Nhân viên xử lý đơn trực tuyến, Khách hàng (tại quầy và mua từ xa), Đơn vị vận chuyển.
- **Quy trình hoạt động & xử lý:**  
  Quy trình bán hàng tiếp nhận và xử lý đơn hàng linh hoạt qua cả hai kênh trực tiếp tại quầy và bán hàng trực tuyến. Đối với khách mua tại quầy, nhân viên thu ngân quét mã vạch sản phẩm; đối với đơn hàng mua từ xa, nhân viên tiếp nhận thông tin từ hệ thống để xác nhận đơn và tạo phiếu đặt hàng. Hệ thống tự động kiểm tra lượng hàng tồn sẵn sàng bán, áp dụng phiếu giảm giá, tích điểm thành viên và tính toán phí vận chuyển. Khách hàng lựa chọn các phương thức thanh toán linh hoạt như tiền mặt, chuyển khoản qua mã phản hồi nhanh, thẻ ngân hàng hoặc thanh toán khi nhận hàng. Ngay khi thanh toán thành công hoặc đơn hàng từ xa được duyệt, hệ thống tự động trừ kho tức thời, in hóa đơn và phiếu gửi hàng để giao cho đơn vị vận chuyển hoặc đưa trực tiếp cho khách, đồng thời ghi nhận doanh thu vào hệ thống. Quy trình cũng hỗ trợ tiếp nhận đổi trả cho cả hai kênh nếu sản phẩm còn nguyên bao bì và có hóa đơn hợp lệ.

#### Chức năng: Quản Lý Nhân Viên và Cộng Tác Viên
- **Mục đích:** Quản lý hồ sơ, phân quyền tài khoản, theo dõi ca làm việc và đánh giá hiệu suất bán hàng của nhân viên chính thức; đồng thời quản lý thông tin, cấp mã số định danh, theo dõi danh mục hàng hóa cấp phát, kiểm soát công nợ sản phẩm và thanh toán hoa hồng cho cộng tác viên tại các khu vực xa (cộng tác viên không có tài khoản đăng nhập hệ thống).
- **Đối tượng thực hiện:** Quản lý cửa hàng, Nhân viên bán hàng (Cộng tác viên được quản lý qua mã số định danh, không có tài khoản đăng nhập).
- **Quy trình hoạt động & xử lý:**  
  Quy trình quản lý nhân sự tập trung vào việc điều phối nhân lực và quản lý hoạt động phân phối hàng hóa của cộng tác viên. Quản lý thực hiện cấp tài khoản cho nhân viên làm việc tại quầy để xếp ca, chấm công và theo dõi doanh thu ca trực. Riêng đội ngũ cộng tác viên tại các khu vực xa không được cấp tài khoản truy cập hệ thống mà chỉ được cấp một mã số cộng tác viên định danh. Khi cộng tác viên nhập hàng từ kho về bán, hệ thống sẽ ghi nhận danh mục và số lượng sản phẩm cấp phát theo mã số tương ứng để theo dõi công nợ hàng hóa. Đến kỳ đối soát, quản lý cập nhật số lượng hàng cộng tác viên đã bán thực tế và số tiền nộp về để hệ thống tự động tính toán theo tỷ lệ hoa hồng chiết khấu, đồng thời kiểm soát lượng hàng còn tồn đọng hoặc hư hỏng tại từng khu vực.

#### Chức năng: Quản Lý Giải Đấu và Tài Trợ Sự Kiện
- **Mục đích:** 
  - Tổ chức, vận hành và điều phối các sự kiện, giải đấu giao lưu, thi đấu tại cửa hàng từ khâu đăng ký, bốc thăm chia cặp đến tổng kết trao thưởng.
  - Quản lý và khai thác các nguồn lực tài trợ (hiện vật độc quyền, kinh phí tổ chức) từ các đối tác phân phối và nhà sản xuất phụ kiện nhằm giảm chi phí vận hành cho cửa hàng.
  - Tối ưu hóa lợi nhuận, thúc đẩy doanh số bán lẻ phụ kiện thi đấu (bọc bài, hộp đựng bài, thảm đấu) và gia tăng giá trị gắn bó dài lâu của khách hàng.
- **Đối tượng thực hiện:** Quản lý giải đấu, Nhà tài trợ, Trọng tài sự kiện, Người tham gia.
- **Quy trình hoạt động & xử lý:**  
  Quy trình quản lý giải đấu và tài trợ bắt đầu khi ban tổ chức khởi tạo thông tin sự kiện trên hệ thống, xác định thể thức thi đấu, lệ phí tham gia và cơ cấu giải thưởng. Đồng thời, hệ thống tiếp nhận thông tin từ các nhà tài trợ (nếu có), ghi nhận gói tài trợ bằng hiện vật độc quyền (thảm đấu vô địch, bọc bài quảng bá, phụ kiện chính hãng) và cập nhật hiển thị quyền lợi biểu trưng, áp phích quảng bá trên trang sự kiện. Người chơi đăng ký thi đấu, nộp lệ phí trực tiếp hoặc thanh toán từ xa để hệ thống ghi nhận doanh thu và thực hiện điểm danh trước giờ khai mạc. Tiếp đó, hệ thống tự động chia cặp thi đấu theo từng vòng đấu và cho phép trọng tài cập nhật tỷ số trực tiếp. Khi giải đấu kết thúc, hệ thống tự động tổng kết bảng xếp hạng chung cuộc, đồng thời tạo phiếu xuất kho các phần quà tài trợ cùng vật phẩm của cửa hàng để trao thưởng cho đấu thủ chiến thắng.


---
## 2. Phân tích những hạn chế đang tồn tại trong hệ thống và đề xuất giải pháp cải tiến
place holder
---

## 3. Xây dựng mô hình DFD cho từng chức năng

### Chức năng: Nhập Hàng

####  Bảng danh sách câu hỏi và trả lời
Câu hỏi:
Trả lời:

#### Mô hình mức ngữ cảnh (Context Level)


#### Mô hình mức đỉnh (Level 1)


#### Mô hình mức dưới đỉnh (Level 2)



### Chức năng: Bán Hàng

####  Bảng danh sách câu hỏi và trả lời
Câu hỏi 1: Hệ thống Bán hàng tương tác với những thực thể bên ngoài nào?
  Trả lời: Gồm 4 thực thể ngoài: Khách hàng, Thu ngân, Nhân viên xử lý đơn trực tuyến, và Đơn vị vận chuyển.
Câu hỏi 2: Các luồng dữ liệu đầu vào gửi đến hệ thống bao gồm những gì?
  Trả lời: Thông tin đặt hàng (từ Khách hàng), Thông tin bán hàng tại quầy (từ Thu ngân), Thông tin xử lý đơn trực tuyến (từ Nhân viên xử lý đơn), và Trạng thái giao hàng (từ Đơn vị vận chuyển).
Câu hỏi 3: Hệ thống Bán hàng gửi trả lại những dữ liệu đầu ra nào cho các thực thể ngoài?
  Trả lời: Xác nhận đơn hàng / Hóa đơn (cho Khách hàng), Thông tin sản phẩm / Kết quả thanh toán (cho Thu ngân), Thông tin đơn hàng (cho Nhân viên xử lý đơn), và Phiếu gửi hàng / Thông tin giao hàng (cho Đơn vị vận chuyển).
2. Mô hình mức đỉnh (Level 1)
Câu hỏi 4: Chức năng Bán hàng ở mức đỉnh bao gồm các tiến trình chính nào?
  Trả lời: Gồm 5 tiến trình chính:
1.0 Tiếp nhận đơn hàng
2.0 Kiểm tra hàng và tính tiền
3.0 Xử lý thanh toán
4.0 Xuất hàng và giao hàng
5.0 Xử lý đổi trả
Câu hỏi 5: Các kho dữ liệu nào tham gia vào mô hình mức đỉnh của chức năng Bán hàng?
  Trả lời: Gồm 4 kho dữ liệu:
D1: Sản phẩm và tồn kho
D2: Khách hàng và thành viên
D3: Đơn hàng
D4: Hóa đơn và doanh thu
3. Mô hình mức dưới đỉnh (Level 2)

Câu hỏi 6: Phân hệ 1.0 Tiếp nhận đơn hàng (Level 2.1) được chi tiết hóa như thế nào?
  Trả lời: Gồm 3 tiến trình con:
1.1 Tiếp nhận thông tin đặt hàng (từ Khách hàng / Thu ngân / Nhân viên xử lý đơn).
1.2 Ghi nhận đơn hàng (lưu thông tin đơn vào kho D3 Đơn hàng).
1.3 Gửi xác nhận đơn hàng (đọc từ D3 để gửi xác nhận cho Khách hàng / Thu ngân / Nhân viên xử lý đơn).
Câu hỏi 7: Phân hệ 2.0 Kiểm tra hàng và tính tiền (Level 2.2) hoạt động ra sao?
  Trả lời: Gồm 4 tiến trình con:
2.1 Kiểm tra sản phẩm (đọc thông tin sản phẩm từ kho D1 Sản phẩm và Tồn kho).
2.2 Kiểm tra tồn kho (kiểm tra số lượng tồn hiện có trong kho D1).
2.3 Áp dụng ưu đãi và tích điểm (đọc thông tin thành viên / điểm tích lũy từ kho D2 Khách hàng & Thành viên).
2.4 Tính tổng tiền và phí vận chuyển (chuyển tổng tiền sang 3.0 Xử lý thanh toán và lưu thông tin đơn vào kho D3 Đơn hàng).
Câu hỏi 8: Phân hệ 3.0 Xử lý thanh toán (Level 2.3) gồm những bước xử lý nào?
  Trả lời: Gồm 4 tiến trình con:
3.1 Nhận yêu cầu thanh toán (từ Khách hàng / Thu ngân).
   3.2 Xác nhận thanh toán (tiền mặt, QR, thẻ, COD).
   3.3 Lập hóa đơn và ghi nhận doanh thu (đọc từ kho D3, ghi nhận vào kho D4 Hóa đơn và doanh thu, gửi Hóa đơn cho Khách hàng).
   3.4 Cập nhật điểm tích lũy và chuyển đơn (cập nhật điểm vào kho D2, chuyển thông tin đơn hàng đã thanh toán sang 4.0 Xuất hàng và giao hàng).
Câu hỏi 9: Phân hệ 4.0 Xuất hàng và giao hàng (Level 2.4) được thực hiện như thế nào?
  Trả lời: Gồm 3 tiến trình con:
4.1 Lập phiếu xuất kho (nhận đơn đã thanh toán từ 3.0, đọc kho D3, cập nhật giảm tồn ở kho D1).
4.2 Đóng gói và lập phiếu gửi hàng (gửi phiếu gửi hàng cho Đơn vị vận chuyển).
4.3 Cập nhật trạng thái giao hàng (nhận trạng thái từ Đơn vị vận chuyển, cập nhật vào kho D3 Đơn hàng).
Câu hỏi 10: Phân hệ 5.0 Xử lý đổi trả (Level 2.5) xử lý quy trình trả hàng như thế nào?
  Trả lời: Gồm 4 tiến trình con:
5.1 Tiếp nhận yêu cầu đổi trả (từ Khách hàng).
5.2 Kiểm tra hóa đơn và điều kiện đổi trả (đối chiếu với kho D4 Hóa đơn và doanh thu).
5.3 Xử lý đổi trả và hoàn tiền (trả kết quả đổi trả cho Khách hàng).
5.4 Cập nhật tồn kho hàng đổi trả (cập nhật tăng tồn vào kho D1 Sản phẩm và tồn kho và cập nhật lại doanh thu ở kho D4 Hóa đơn và doanh thu).

#### Mô hình mức ngữ cảnh (Context Level)
<img width="732" height="422" alt="BanHang_context" src="https://github.com/user-attachments/assets/45bb9b4e-8d44-4e0e-8457-b0fd6a987270" />


#### Mô hình mức đỉnh (Level 1)
<img width="1492" height="942" alt="BanHang_level1" src="https://github.com/user-attachments/assets/7b2a96b8-18f6-4c83-b317-5289fab384e9" />


#### Mô hình mức dưới đỉnh (Level 2)
<img width="967" height="352" alt="BanHang_level2 1" src="https://github.com/user-attachments/assets/b88db771-2ab8-47b9-aa82-7f159d19edcf" />
<img width="1162" height="321" alt="BanHang_level2 2" src="https://github.com/user-attachments/assets/b5c76a11-1577-4a73-a366-29cccd455bf0" />
<img width="1172" height="492" alt="BanHang_level2 3" src="https://github.com/user-attachments/assets/8b342959-1810-45f4-877a-fe58fb0eb99d" />
<img width="1062" height="422" alt="BanHang_level2 4" src="https://github.com/user-attachments/assets/ab7d20f0-663e-446e-bdef-adddaab23998" />
<img width="1202" height="295" alt="BanHang_level2 5" src="https://github.com/user-attachments/assets/9762cd27-c493-4f86-b9fd-4783d26bd9dc" />






### Chức năng: Tổ Chức Giải Đấu & Tài Trợ Sự Kiện

####  Bảng danh sách câu hỏi và trả lời
Câu hỏi:
Trả lời:

#### Mô hình mức ngữ cảnh (Context Level)


#### Mô hình mức đỉnh (Level 1)


#### Mô hình mức dưới đỉnh (Level 2)

---
