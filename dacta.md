# ĐẶC TẢ HỆ THỐNG

## 1. Liệt kê các chức năng và đặc tả quy trình hoạt động, xử lý của hệ thống

### 1.1. Danh sách các chức năng

### 1.2. Đặc tả quy trình hoạt động và xử lý

#### Chức năng: Nhập hàng
- **Mục đích:** Quản lý quy trình mua hàng từ nhà cung cấp, kiểm đếm số lượng, chất lượng và cập nhật dữ liệu nhập kho vào hệ thống.
- **Đối tượng thực hiện:** Quản lý cửa hàng, Nhân viên mua/nhập hàng.
- **Quy trình hoạt động & xử lý:**  
  Quy trình nhập hàng bắt đầu khi nhân viên kiểm tra lượng tồn kho và nhận thấy các mặt hàng phụ kiện  chạm mức tối thiểu, từ đó tiến hành lập đơn đặt hàng  gửi đến nhà cung cấp. Khi nhận được hàng bàn giao, nhân viên kho cùng quản lý tiến hành đối chiếu với hóa đơn chứng từ, kiểm tra thực tế số lượng, chất lượng bao bì và tính toàn vẹn của từng sản phẩm. Nếu lô hàng đạt chuẩn, nhân viên tạo phiếu nhập kho trên hệ thống để ghi nhận công nợ và tự động cập nhật tăng số lượng tồn kho theo thời gian thực. Trường hợp phát hiện hàng hóa không đạt chuẩn hoặc thiếu hụt số lượng, nhân viên sẽ lập biên bản sự cố ngay tại chỗ để từ chối nhận hoặc yêu cầu nhà cung cấp thực hiện đổi trả.

#### Chức năng: Quản lý Kho
- **Mục đích:** Theo dõi chính xác lượng tồn kho, vị trí lưu trữ, biến động hàng hóa và kiểm soát thất thoát.
- **Đối tượng thực hiện:** Nhân viên kho, Quản lý cửa hàng.
- **Quy trình hoạt động & xử lý:**  
  Quy trình quản lý kho được vận hành liên tục nhằm kiểm soát chặt chẽ vị trí lưu trữ, số lượng và chất lượng của toàn bộ sản phẩm phụ kiện thẻ bài trong cửa hàng. Mỗi khi phát sinh giao dịch nhập, xuất, bán lẻ hoặc xuất thưởng giải đấu, hệ thống sẽ tự động cập nhật số lượng tồn khả dụng và tồn giữ chỗ theo thời gian thực. Hàng hóa khi nhập về được phân loại theo danh mục và sắp xếp vào các vị trí ngăn kệ hoặc tủ trưng bày cố định. Định kỳ, nhân viên thực hiện quét mã vạch kiểm kê thực tế để đối chiếu chéo với dữ liệu hệ thống, kịp thời phát hiện sai lệch thừa thiếu hay hàng hư hỏng để lập biên bản xử lý thất thoát. Đồng thời, hệ thống tự động theo dõi thời gian lưu kho và gửi cảnh báo khi sản phẩm chạm ngưỡng tối thiểu hoặc tồn đọng quá lâu để cửa hàng chủ động lên kế hoạch xả hàng hoặc tái nhập.

#### Chức năng: Bán Hàng
- **Mục đích:** Thực hiện quy trình tiếp nhận đơn hàng, tính tiền, áp dụng ưu đãi, thanh toán và in hóa đơn cho khách hàng.
- **Đối tượng thực hiện:** Thu ngân, Nhân viên bán hàng, Khách hàng.
- **Quy trình hoạt động & xử lý:**  
  Quy trình bán hàng bắt đầu khi khách hàng lựa chọn các sản phẩm thẻ bài, phụ kiện hoặc dịch vụ tại quầy. Nhân viên thu ngân sử dụng máy quét mã vạch để khởi tạo đơn hàng trên hệ thống, kiểm tra thông tin thành viên của khách để áp dụng voucher, khuyến mãi hoặc trừ điểm tích lũy hợp lệ. Sau khi thông báo tổng số tiền cần thanh toán, hệ thống hỗ trợ đa dạng phương thức thanh toán linh hoạt như tiền mặt, chuyển khoản quét mã QR hoặc quẹt thẻ ngân hàng. Ngay khi giao dịch thanh toán thành công, hệ thống tự động in hóa đơn giao cho khách, lưu dữ liệu vào doanh thu ca làm việc và tự động trừ số lượng tồn kho tương ứng của từng mặt hàng. Ngoài ra, quy trình còn tiếp nhận xử lý đổi trả cho khách hàng theo đúng quy định nếu sản phẩm còn nguyên bao bì và có hóa đơn mua hàng hợp lệ.

#### Chức năng: Quản Lý Nhân Viên và Cộng Tác Viên
- **Mục đích:** Quản lý hồ sơ, phân quyền tài khoản, theo dõi ca làm việc và kiểm soát hiệu suất bán hàng của nhân viên; đồng thời quản lý danh mục sản phẩm phân phối, doanh số và chính sách hoa hồng cho đội ngũ cộng tác viên bán hàng (CTV kinh doanh thẻ bài & phụ kiện).
- **Đối tượng thực hiện:** Quản lý cửa hàng / Quản trị viên (Admin), Nhân viên bán hàng, Cộng tác viên bán hàng.
- **Quy trình hoạt động & xử lý:**  
  Quy trình quản lý nhân sự tập trung  vào hoạt động bán hàng của cửa hàng. Quản lý thực hiện lưu trữ hồ sơ, cấp tài khoản và phân quyền cho nhân viên bán hàng tại quầy cùng các cộng tác viên bán hàng online hoặc phân phối phụ kiện card game. Đối với nhân viên bán hàng, hệ thống hỗ trợ quản lý lịch phân ca, ghi nhận chấm công theo ca làm việc và theo dõi doanh thu đơn hàng bán được trong từng ca trực. Đối với cộng tác viên, hệ thống cấp mã định danh hoặc liên kết giới thiệu để ghi nhận các đơn hàng phát sinh từ danh mục sản phẩm phụ kiện mà CTV phụ trách bán. Cuối mỗi kỳ quyết toán, hệ thống tự động tổng hợp ca công của nhân viên, đối soát doanh số bán hàng thực tế của từng nhân viên và CTV, từ đó tự động tính toán lương cứng, thưởng doanh số và tỷ lệ phần trăm hoa hồng bán hàng một cách minh bạch, chính xác.

#### Chức năng: Quản Lý Giải Đấu
- **Mục đích:** 
  - Tổ chức, vận hành và điều phối các sự kiện, giải đấu giao lưu/tranh tài tại shop từ khâu đăng ký, bốc thăm chia cặp đến tổng kết trao thưởng.
  - Nhằm Tối ưu hóa lợi nhuận và thúc đẩy doanh thu cho shop 
- **Đối tượng thực hiện:** Quản lý giải đấu, Trọng tài sự kiện, Người tham gia (Player).
- **Quy trình hoạt động & xử lý:**  
  Quy trình quản lý giải đấu bắt đầu khi ban tổ chức thiết lập thông tin sự kiện trên hệ thống, bao gồm tên giải, thể thức thi đấu, số lượng người tham gia tối đa, cơ cấu giải thưởng và lệ phí tham gia (entry fee). Hệ thống mở cổng đăng ký tiếp nhận thông tin người chơi và thu lệ phí để trực tiếp ghi nhận doanh thu cho cửa hàng. Vào ngày diễn ra sự kiện, ban tổ chức thực hiện điểm danh người chơi, sau đó hệ thống sẽ tự động bốc thăm và chia cặp thi đấu (pairing) theo từng vòng đấu. Sau mỗi trận, trọng tài hoặc ban tổ chức cập nhật kết quả và tỷ số trực tiếp lên phần mềm để hệ thống tự động tính điểm và xếp hạng. Khi giải đấu kết thúc, hệ thống công bố bảng xếp hạng chung cuộc và tự động tạo phiếu xuất kho quà tặng bao gồm phụ kiện card game, thẻ bài hoặc voucher mua sắm cho người đạt giải.


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



### Chức năng: Tổ Chức Giải Đấu

####  Bảng danh sách câu hỏi và trả lời
Câu hỏi:
Trả lời:

#### Mô hình mức ngữ cảnh (Context Level)


#### Mô hình mức đỉnh (Level 1)


#### Mô hình mức dưới đỉnh (Level 2)

---