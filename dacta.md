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
Câu hỏi:
Trả lời:

#### Mô hình mức ngữ cảnh (Context Level)


#### Mô hình mức đỉnh (Level 1)


#### Mô hình mức dưới đỉnh (Level 2)



### Chức năng: Tổ Chức Giải Đấu & Tài Trợ Sự Kiện

####  Bảng danh sách câu hỏi và trả lời
Câu hỏi:
Trả lời:

#### Mô hình mức ngữ cảnh (Context Level)


#### Mô hình mức đỉnh (Level 1)


#### Mô hình mức dưới đỉnh (Level 2)

---

Chức năng: Bán Hàng
3.1. Phân tích chi tiết mô hình DFD qua các cấp
1. Mô hình mức ngữ cảnh (Context Level)
 Câu hỏi 1: Hệ thống Bán hàng tương tác với các thực thể bên ngoài nào?
Trả lời: Hệ thống tương tác trực tiếp với 4 thực thể bên ngoài bao gồm: Khách hàng, Thu ngân, Nhân viên xử lý đơn trực tuyến và Đơn vị vận chuyển.
 Câu hỏi 2: Các luồng dữ liệu chính ra và vào hệ thống ở mức ngữ cảnh là gì?
Trả lời:Luồng dữ liệu đầu vào: Khách hàng gửi Yêu cầu mua hàng (Thông tin đặt hàng) và Yêu cầu đổi trả; Thu ngân gửi Thông tin bán tại quầy; Nhân viên xử lý đơn trực tuyến gửi Thông tin xử lý đơn trực tuyến; Đơn vị vận chuyển gửi Trạng thái giao hàng.
        Luồng dữ liệu đầu ra: Hệ thống phản hồi Xác nhận đơn hàng / Hóa đơn hoặc Kết quả đổi trả cho Khách hàng; gửi Thông tin sản phẩm & Kết quả thanh toán cho Thu ngân; gửi Thông tin đơn hàng cho Nhân viên xử lý đơn; chuyển Phiếu gửi hàng & Thông tin giao hàng cho Đơn vị vận chuyển.
2. Mô hình mức đỉnh (Level 1)
  Câu hỏi 1: Hệ thống Bán hàng ở mức đỉnh được phân rã thành những tiến trình chính nào?
Trả lời: Hệ thống gồm 5 tiến trình chính:
1.0 Tiếp nhận đơn hàng
2.0 Kiểm tra hàng và tính tiền
3.0 Xử lý thanh toán
4.0 Xuất hàng và giao hàng
5.0 Xử lý đổi trả
   Câu hỏi 2: Các kho dữ liệu nào được sử dụng trong sơ đồ mức đỉnh?
Trả lời: Hệ thống khai thác 4 kho dữ liệu bao gồm: D1: Sản phẩm & Tồn kho   D2: Khách hàng & Thành viên   D3: Đơn hàng   D4: Hóa đơn & Doanh thu
  Câu hỏi 3: Quy trình luân chuyển dữ liệu tổng thể giữa các tiến trình diễn ra như thế nào?
Trả lời:Khi phát sinh giao dịch, tiến trình 1.0 tiếp nhận đơn từ khách hàng/thu ngân/nhân viên và lưu thông tin vào kho D3.  Tiến trình 2.0 đọc đơn hàng từ kho D3, truy vấn kho D1 để xác minh số lượng tồn kho khả dụng, đồng thời tra cứu kho D2 để áp dụng điểm tích lũy/ưu đãi thành viên và tính tổng tiền kèm phí vận chuyển. Thông tin tổng tiền được gửi sang tiến trình 3.0 để thực hiện giao dịch thanh toán và cập nhật doanh thu vào kho D4.  Tiến trình 4.0 tiếp nhận đơn hàng đã thanh toán, thực hiện cập nhật giảm số lượng tồn kho trong D1 và chuyển thông tin giao nhận cho Đơn vị vận chuyển. Đối với sự cố đổi trả, tiến trình 5.0 tiếp nhận yêu cầu từ khách hàng, kiểm tra hóa đơn hợp lệ từ kho D4, cập nhật nhập hoàn trả kho D1 và điều chỉnh lại doanh thu ở kho D4.
3. Mô hình mức dưới đỉnh (Level 2 - Tiến trình 2.0: Kiểm tra hàng và tính tiền)
  Câu hỏi 1: Tiến trình 2.0 được chi tiết hóa thành các tiến trình con nào?
Trả lời: Tiến trình 2.0 gồm 4 tiến trình thành phần:
2.1 Kiểm tra sản phẩm
2.2 Kiểm tra tồn kho
2.3 Áp dụng ưu đãi & tích điểm  
2.4 Tính tổng tiền
  Câu hỏi 2: Chi tiết luồng dữ liệu và quy trình xử lý bên trong Tiến trình 2.0 diễn ra ra sao?
Trả lời:
Bước 1 (Kiểm tra sản phẩm - 2.1): Đọc thông tin đơn hàng từ kho D3, gửi mã sản phẩm sang kho D1 để đối chiếu thông tin tên hàng và đơn giá.
Bước 2 (Kiểm tra tồn kho - 2.2): Tiếp nhận danh sách sản phẩm cần kiểm tra từ 2.1, truy vấn kho D1 để xác minh số lượng tồn kho hiện tại xem có đủ đáp ứng hay không.
Bước 3 (Áp dụng ưu đãi & tích điểm - 2.3): Nhận danh sách sản phẩm hợp lệ từ 2.2, truy xuất thông tin khách hàng từ kho D2 để tra cứu điểm tích lũy, mã giảm giá và tính toán chiết khấu.
Bước 4 (Tính tổng tiền - 2.4): Nhận giá sau ưu đãi từ 2.3, thực hiện cộng thêm phí vận chuyển (đối với đơn từ xa) để ra tổng tiền thanh toán cuối cùng, sau đó gửi dữ liệu sang tiến trình 3.0 Xử lý thanh toán

1. Mô hình mức ngữ cảnh (Context Level):
  <img width="732" height="422" alt="BanHang_context" src="https://github.com/user-attachments/assets/4c94b3b7-02f8-4db5-befd-a2f9333cebed" />
2. Mô hình mức đỉnh (Level 1):
<img width="1319" height="612" alt="BanHang_level1" src="https://github.com/user-attachments/assets/27dc30cd-4a79-4dc8-9ce2-c052c2af6ed5" />
3. mô hình mức dưới đỉnh (Level 2):
<img width="652" height="562" alt="BanHang_level2" src="https://github.com/user-attachments/assets/290ab0a5-9689-4ff2-a4ea-b175d7d3fcc7" />


