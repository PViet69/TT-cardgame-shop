# ĐẶC TẢ HỆ THỐNG

## Giới thiệu dự án

TTshop là dự án phân tích và đặc tả hệ thống quản lý cửa hàng phụ kiện trò chơi thẻ bài, hỗ trợ hoạt động bán hàng tại quầy, bán hàng trực tuyến và phân phối qua cộng tác viên. Hệ thống bao gồm các nghiệp vụ nhập hàng, quản lý kho, bán hàng, quản lý nhân viên và cộng tác viên, cùng tổ chức giải đấu và quản lý tài trợ sự kiện.

Dự án hướng đến việc quản lý tập trung thông tin hàng hóa, đơn hàng, thanh toán và sự kiện, giúp cửa hàng theo dõi tồn kho, kiểm soát công nợ và phối hợp các hoạt động kinh doanh. Tài liệu này trình bày các quy trình nghiệp vụ, kho dữ liệu và sơ đồ luồng dữ liệu (DFD), làm cơ sở cho việc thiết kế và phát triển hệ thống.

## 1. Liệt kê các chức năng và đặc tả quy trình hoạt động, xử lý của hệ thống

### 1.1. Danh sách các chức năng
1. Chức năng Nhập hàng
2. Chức năng Quản lý Kho
3. Chức năng Bán Hàng
4. Chức năng Quản lý Nhân Viên và Cộng Tác Viên
5. Chức năng Quản lý Giải Đấu và Tài Trợ Sự Kiện
6. Chức năng quản lý nội dung Fanpage



### 1.2. Đặc tả quy trình hoạt động và xử lý

#### Chức năng: Nhập hàng
- **Mục đích:** Quản lý quy trình mua hàng từ nhà cung cấp, kiểm đếm số lượng, chất lượng và cập nhật dữ liệu nhập kho vào hệ thống.
- **Đối tượng thực hiện:** Quản lý cửa hàng, Nhân viên mua/nhập hàng.
- **Mức tồn kho tối thiểu:** Được xét riêng cho từng mặt hàng. Khi số lượng tồn kho của một mặt hàng dưới 20 sản phẩm, nhân viên xác định nhu cầu nhập thêm và lập đơn đặt hàng gửi nhà cung cấp.
- **Quy trình hoạt động & xử lý:**  
  Quy trình nhập hàng bắt đầu khi nhân viên kiểm tra lượng tồn kho và nhận thấy một mặt hàng phụ kiện có số lượng tồn kho dưới 20 sản phẩm, từ đó tiến hành lập đơn đặt hàng gửi đến nhà cung cấp. Khi nhận được hàng bàn giao, nhân viên kho cùng quản lý tiến hành đối chiếu với hóa đơn chứng từ, kiểm tra thực tế số lượng, chất lượng bao bì và tính toàn vẹn của từng sản phẩm. Nếu lô hàng đạt chuẩn, nhân viên tạo phiếu nhập kho trên hệ thống để ghi nhận công nợ và tự động cập nhật tăng số lượng tồn kho theo thời gian thực. Trường hợp phát hiện hàng hóa không đạt chuẩn hoặc thiếu hụt số lượng, nhân viên sẽ lập biên bản sự cố ngay tại chỗ để từ chối nhận hoặc yêu cầu nhà cung cấp thực hiện đổi trả.

#### Chức năng: Quản lý Kho
- **Mục đích:** Theo dõi chính xác lượng hàng tồn kho tại cửa hàng và các điểm phân phối, quản lý vị trí lưu trữ, điều phối xuất chuyển hàng cho cộng tác viên ở các khu vực và kiểm soát thất thoát hàng hóa.
- **Đối tượng thực hiện:** Nhân viên kho, Quản lý cửa hàng.
- **Quy trình hoạt động & xử lý:**  
  Quy trình quản lý kho vận hành liên tục nhằm kiểm soát biến động hàng hóa tại kho chính và các điểm lưu trữ của cộng tác viên ở xa. Số lượng tồn kho được cập nhật sau khi hoàn tất nhập hàng, bán hàng hoặc kiểm hàng (kiểm kê); việc lập đơn hoặc bắt đầu xử lý chưa làm thay đổi số lượng tồn kho. Hàng chờ đổi trả được dán tem để nhận diện, theo dõi riêng và không tính vào số lượng tồn kho thực tế, kể cả khi còn được lưu giữ tại cửa hàng. Khi cộng tác viên tại các khu vực khác có nhu cầu lấy hàng về bán, nhân viên kho lập phiếu xuất kho chuyển hàng gắn theo mã số của cộng tác viên đó, hệ thống sẽ tự động trừ lượng tồn tại kho chính và ghi nhận số lượng chuyển vào kho ký gửi của cộng tác viên. Hai tuần một lần, vào ngày thứ Ba, Nhân viên kho hoặc Quản lý cửa hàng thực hiện quét mã kiểm kê thực tế tại quầy và đối chiếu số lượng hàng ký gửi từ xa để phát hiện sai lệch, hàng hư hỏng nhằm xử lý thất thoát. Số liệu tồn kho được chốt sau khi hoàn tất quy trình kiểm kê và xử lý điều chỉnh được duyệt. Trường hợp cộng tác viên không bán hết hoặc đổi trả, kho sẽ lập phiếu nhập hoàn để thu hồi hàng về kho chính.


- **Quy tắc quản lý hàng chờ đổi trả:** Nhân viên dán tem nhận diện hàng chờ đổi trả để phân biệt với hàng trong kho thực tế. Đề xuất thông tin trên tem gồm mã mặt hàng, số lượng, lý do đổi trả, ngày ghi nhận và mã chứng từ liên quan. Khi kiểm hàng, nhân viên đối chiếu riêng hàng có tem chờ đổi trả và loại số lượng này khỏi số đếm tồn kho thực tế. Hàng chỉ được tính trở lại vào tồn kho sau khi đã xử lý đổi trả, kiểm tra đạt yêu cầu và hoàn tất nhập kho.
- **Thời điểm cập nhật tồn kho:**
  - **Sau nhập hàng:** Tăng tồn theo số lượng thực nhận đã kiểm tra đạt yêu cầu và hoàn tất ghi nhận nhập kho; không cộng hàng chờ đổi trả.
  - **Sau bán hàng:** Giảm tồn theo số lượng hàng của giao dịch bán đã hoàn tất; việc chỉ lập hoặc duyệt đơn chưa làm giảm tồn kho thực tế.
  - **Sau kiểm hàng:** Đối chiếu số lượng trên hệ thống với số đếm thực tế, không tính hàng dán tem chờ đổi trả. Nếu có chênh lệch, lập biên bản và cập nhật tồn sau khi có quyết định điều chỉnh được duyệt.


- **Bố trí hàng theo nhóm sản phẩm (category):** Hàng hóa được sắp xếp tại các khu vực riêng theo nhóm như bọc bài, deckbox, playmat, móc khóa, figure và các nhóm sản phẩm khác. Nhân viên kho bố trí hàng vào khu vực tương ứng, ghi nhận vị trí lưu trữ và cập nhật vị trí khi di chuyển hàng để thuận tiện tra cứu, lấy hàng và kiểm kê. Việc chuyển vị trí trong cùng kho không làm thay đổi tổng số lượng tồn kho. Hàng chờ đổi trả và hàng hỏng chờ duyệt loại bỏ được dán tem, để riêng khỏi hàng có thể bán.

- **Xử lý hàng hỏng phát hiện trong kho:** Khi phát hiện hàng rách, hỏng, móp méo hoặc không đạt tiêu chuẩn bán trong lúc kiểm kê hay thao tác kho, Nhân viên kho hoặc Quản lý cửa hàng ghi nhận mặt hàng, số lượng, vị trí, tình trạng và lý do đề nghị loại bỏ vào D25 — Sổ Kiểm kê và Thất thoát. Hàng được dán tem, tách riêng và không tiếp tục xuất bán trong thời gian chờ xử lý. **Chỉ được loại bỏ sau khi Quản lý cửa hàng phê duyệt.** Sau khi được duyệt, Nhân viên kho thực hiện loại bỏ, ghi nhận số lượng và thời điểm thực hiện, cập nhật giảm tồn đối với số lượng hàng hỏng còn được tính trong tồn kho và lưu nhật ký tại D24 — Sổ Nhật ký Phiếu kho. Nếu số lượng đó đã được trừ qua điều chỉnh kiểm kê được duyệt thì không trừ thêm lần nữa. Trường hợp chưa được duyệt, tiếp tục giữ riêng hàng có tem để chờ quyết định.

- **Lịch kiểm kê, người thực hiện và thời điểm chốt:** Kiểm kê hai tuần một lần, vào ngày thứ Ba, do **Nhân viên kho** hoặc **Quản lý cửa hàng** . Người thực hiện ghi nhận số đếm theo từng mặt hàng và vị trí, loại hàng có tem chờ đổi trả khỏi tồn kho thực tế. Số liệu được chốt sau khi hoàn tất kiểm kê, đối chiếu và cập nhật các điều chỉnh được duyệt. Nếu có giao dịch nhập hoặc xuất trong thời gian kiểm kê, phải đối chiếu các giao dịch đó với thời điểm đếm để tránh tính thiếu hoặc tính trùng khi chốt.

- **Quy trình xử lý chênh lệch kiểm kê:**
  1. **Đối chiếu:** Nhân viên kho hoặc Quản lý cửa hàng so sánh số đếm thực tế với số lượng trên hệ thống theo từng mặt hàng và vị trí; xác định số thừa hoặc thiếu. Hàng chờ đổi trả được kiểm tra riêng theo tem và không đưa vào số đếm tồn kho thực tế.
  2. **Kiểm tra lại:** Đếm lại mặt hàng có chênh lệch, kiểm tra vị trí lưu trữ, phiếu nhập, giao dịch bán, phiếu xuất và các điều chỉnh liên quan. Đối chiếu cả giao dịch phát sinh trong thời gian kiểm kê để xác định nguyên nhân; không tự kết luận mọi khoản thiếu là thất thoát.
  3. **Lập biên bản:** Ghi mã mặt hàng, vị trí, số lượng trên hệ thống, số đếm thực tế, mức chênh lệch, tình trạng hàng, nguyên nhân đã xác minh hoặc nội dung chưa làm rõ, chứng từ liên quan và người kiểm kê vào D25 — Sổ Kiểm kê và Thất thoát.
  4. **Quyết định xử lý:** Quản lý cửa hàng xem xét biên bản và căn cứ đối chiếu để duyệt điều chỉnh, yêu cầu kiểm tra bổ sung hoặc từ chối đề nghị. Nếu nguyên nhân là chứng từ sai hoặc chưa được ghi nhận, xử lý chứng từ liên quan và kiểm tra lại số dư, tránh vừa sửa chứng từ vừa điều chỉnh cùng một chênh lệch.
  5. **Cập nhật và chốt:** Sau khi được duyệt, thực hiện điều chỉnh tại tiến trình 3.4, cập nhật D4 — Hàng hóa và tồn kho, ghi nhật ký vào D24 — Sổ Nhật ký Phiếu kho và cập nhật kết quả xử lý trong D25. Kiểm tra lại số dư rồi chốt kỳ kiểm kê; hồ sơ còn chờ xác minh tiếp tục được theo dõi, không tự điều chỉnh khi chưa có quyết định.

- **Quy trình tiếp nhận và nhập lại hàng đổi trả của khách hàng và CTV:**
  1. **Tiếp nhận yêu cầu:** Nhân viên bán tại quầy tiếp nhận yêu cầu đổi trả trực tiếp; Nhân viên bán online (Nhân viên xử lý đơn trực tuyến) tiếp nhận yêu cầu qua tin nhắn. Nhân viên ghi nhận mặt hàng, số lượng, lý do đổi trả và đối chiếu với giao dịch bán của khách hàng hoặc phiếu cấp hàng theo mã CTV. Phạm vi quy trình này là hàng khách hàng và CTV trả về cửa hàng.
  2. **Kiểm tra chất lượng và điều kiện đổi trả:** Nhân viên bán tại quầy trực tiếp kiểm tra mã hàng, bao bì, số lượng và tình trạng sản phẩm được mang đến. Nhân viên bán online kiểm tra, đối chiếu tình trạng hàng qua nội dung tin nhắn và hình ảnh hoặc video do khách hàng cung cấp, đồng thời đối chiếu thông tin đơn hàng. Với hàng CTV trả về, nhân viên phụ trách tiếp nhận kiểm tra theo cách giao nhận tương ứng và đối chiếu phiếu cấp hàng. Nhân viên lưu kết quả kiểm tra, nội dung trao đổi và căn cứ đánh giá vào hồ sơ đổi trả, sau đó chuyển Quản lý cửa hàng xem xét và xác nhận. Nếu chưa đủ thông tin, Quản lý cửa hàng yêu cầu kiểm tra bổ sung trước khi quyết định.
  3. **Nhận hàng, dán tem và theo dõi riêng:** Khi hàng được trả về cửa hàng, Nhân viên kho tiếp nhận theo hồ sơ đổi trả và dán tem nhận diện để theo dõi riêng; hàng chờ xử lý không tính vào tồn kho thực tế. Đối với yêu cầu online, nhân viên bán phụ trách đối chiếu hàng nhận được với tình trạng đã trao đổi qua tin nhắn và chuyển kết quả cho Quản lý cửa hàng xác nhận cuối cùng. Việc chấp nhận yêu cầu qua tin nhắn chưa làm tăng tồn kho khi hàng chưa được nhận về.
  4. **Quản lý xác nhận và quyết định xử lý:** Quản lý cửa hàng xem xét kết quả kiểm tra của nhân viên bán phụ trách và xác nhận phương án xử lý hàng khách hàng hoặc CTV trả về. Hàng đạt tiêu chuẩn bán lại được chuyển cho Nhân viên kho lập phiếu nhập hoàn. Hàng không đạt tiêu chuẩn bán lại, như rách, hỏng, móp méo hoặc có tình trạng khác không bảo đảm chất lượng bán, được Quản lý cửa hàng xác nhận loại bỏ; Nhân viên kho thực hiện loại bỏ và ghi nhận mặt hàng, số lượng, tình trạng, lý do, người xác nhận và thời điểm xử lý vào hồ sơ đổi trả. Hàng còn chờ quyết định tiếp tục được dán tem và theo dõi riêng. Hàng bị loại bỏ không được nhập lại hoặc cộng vào tồn kho thực tế; việc loại bỏ không làm giảm tồn thêm nếu hàng đã được loại khỏi số lượng tồn trước đó.
  5. **Hoàn tất nhập lại:** Sau khi hàng thực nhận được Quản lý cửa hàng xác nhận đạt tiêu chuẩn bán lại và hoàn tất nhập kho, Nhân viên kho cập nhật tăng tồn một lần theo số lượng đủ điều kiện, ghi nhật ký phiếu kho và cập nhật trạng thái hồ sơ đổi trả. Kết thúc trạng thái chờ đổi trả, gỡ hoặc thay tem phù hợp rồi bố trí hàng về vị trí lưu trữ. Việc đổi sản phẩm, hoàn tiền cho khách hàng hoặc điều chỉnh công nợ CTV được ghi nhận theo quy trình liên quan; không dùng riêng trạng thái hoàn tiền hoặc đối soát làm căn cứ tăng tồn.

#### Chức năng: Bán Hàng
- **Mục đích:** Quản lý và xử lý toàn diện quy trình bán hàng đa kênh bao gồm bán trực tiếp tại quầy và bán hàng trực tuyến (qua trang mạng, kênh bán hàng); tính tiền, áp dụng ưu đãi, xác nhận thanh toán, đóng gói giao vận và in hóa đơn cho khách hàng.
- **Đối tượng thực hiện:** Thu ngân, Nhân viên xử lý đơn trực tuyến, Quản lý cửa hàng, Khách hàng (tại quầy và mua từ xa), Đơn vị vận chuyển.
- **Quy trình hoạt động & xử lý:**  
  Quy trình bán hàng tiếp nhận và xử lý đơn hàng linh hoạt qua cả hai kênh trực tiếp tại quầy và bán hàng trực tuyến. Đối với khách mua tại quầy, nhân viên thu ngân quét mã vạch sản phẩm; đối với đơn hàng mua từ xa, nhân viên tiếp nhận thông tin từ hệ thống để xác nhận đơn và tạo phiếu đặt hàng. Hệ thống tự động kiểm tra lượng hàng tồn sẵn sàng bán, áp dụng phiếu giảm giá, tích điểm thành viên và tính toán phí vận chuyển. Khách hàng lựa chọn các phương thức thanh toán linh hoạt như tiền mặt, chuyển khoản qua mã phản hồi nhanh, thẻ ngân hàng hoặc thanh toán khi nhận hàng. Sau khi giao dịch bán hàng hoàn tất, hệ thống cập nhật giảm tồn kho theo số lượng thực bán. Nhân viên in hóa đơn và phiếu gửi hàng để giao cho đơn vị vận chuyển hoặc đưa trực tiếp cho khách; việc ghi nhận doanh thu thực hiện theo trạng thái giao dịch. Việc chỉ lập hoặc duyệt đơn hàng từ xa chưa làm giảm tồn kho thực tế. Quy trình hỗ trợ tiếp nhận yêu cầu đổi trả trong vòng 24 giờ sau khi khách nhận hàng, đối chiếu với giao dịch mua. Khách được đổi hàng khi giao sai màu/mẫu mã hoặc sản phẩm có lỗi không do khách hàng gây ra; được trả hàng khi sản phẩm có lỗi không do khách hàng gây ra. Nhân viên bán phụ trách kiểm tra và chuyển Quản lý cửa hàng xác nhận theo quy trình đổi trả đã mô tả ở phần quản lý kho.


- **Xử lý thiếu hoặc hết hàng khi bán online:** Nhân viên xử lý đơn trực tuyến kiểm tra lượng hàng đáp ứng đơn. Nếu thiếu hoặc hết bất kỳ mặt hàng nào trong đơn, nhân viên thông báo tình trạng và đề nghị khách hủy đơn; ghi nhận kết quả hủy, không tự tách giao hoặc chuyển sang chờ nhập hàng.
- **Xác nhận thanh toán:** Quản lý cửa hàng là người xác nhận đã nhận tiền. Với chuyển khoản, quản lý đối chiếu bill chuyển khoản của khách với thông tin đơn hàng và khoản tiền thực nhận. Nếu khách chuyển thiếu, nhân viên thông báo số tiền còn thiếu để khách tiếp tục chuyển khoản đến khi đủ; lưu các bill và tổng số tiền đã nhận theo cùng đơn hàng. Chỉ ghi nhận thanh toán hoàn tất sau khi quản lý xác nhận đã nhận đủ số tiền phải thanh toán; không ghi nhận hoàn tất chỉ dựa vào việc khách gửi bill.
- **Điều kiện hoàn tất đơn:** Đơn hàng hoàn tất khi đã ghi nhận thanh toán hoàn tất. Sau thời điểm này, cập nhật giảm tồn theo số lượng thực bán. Trạng thái giao hàng được theo dõi riêng, vì đơn hoàn tất thanh toán có thể chưa được bàn giao hoặc giao đến khách.
- **Hủy đơn và phí vận chuyển:** Khách được hủy đơn trước khi hàng được bàn giao cho đơn vị vận chuyển. Nếu mới tạo yêu cầu giao nhưng chưa bàn giao hàng, nhân viên hủy yêu cầu giao và cập nhật trạng thái đơn. Sau khi đã bàn giao, không xử lý theo quy trình hủy đơn; yêu cầu trả hàng được xét theo điều kiện đổi trả. Shop chịu phí giao hàng; khách hàng chịu phí hoàn hàng. Nếu đơn hủy đã thanh toán, ghi nhận khoản cần hoàn và theo dõi kết quả hoàn tiền. Nếu tồn đã giảm khi thanh toán hoàn tất mà hàng chưa được giao, đối chiếu và hoàn lại số lượng của đơn đã hủy một lần, không lập thêm phiếu nhập trùng.
- **Thời hạn và điều kiện đổi trả:** Khách gửi yêu cầu trong vòng **24 giờ kể từ khi nhận hàng**. Được đổi hàng nếu giao sai màu/mẫu mã hoặc sản phẩm có lỗi không phải do khách hàng gây ra; được trả hàng nếu sản phẩm có lỗi không phải do khách hàng gây ra. Nhân viên bán tại quầy kiểm tra trực tiếp; nhân viên bán online đối chiếu tin nhắn và hình ảnh/video khách cung cấp. Quản lý cửa hàng xác nhận kết quả trước khi xử lý đổi hàng hoặc hoàn tiền. Hàng trả về được dán tem và xử lý theo quy trình quản lý kho; việc nhận yêu cầu không tự làm tăng tồn.
- **Khuyến mãi và điểm tích lũy:** Không áp dụng cộng dồn ưu đãi khuyến mãi với ưu đãi sử dụng điểm tích lũy trong cùng giao dịch; nhân viên thông báo phương án áp dụng để khách xác nhận trước khi thanh toán. Khi hủy đơn hoặc trả toàn bộ đơn, hoàn nguyên tác động của giao dịch đến điểm: hoàn lại điểm đã sử dụng và thu hồi điểm được cộng từ giao dịch đó, đưa số điểm về mức trước khi mua. Việc hoàn nguyên chỉ tác động đến giao dịch bị hủy/trả, không ghi đè các biến động điểm từ giao dịch khác.

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
  Quy trình quản lý giải đấu và tài trợ bắt đầu khi ban tổ chức khởi tạo thông tin sự kiện trên hệ thống, xác định thể thức thi đấu, lệ phí tham gia và cơ cấu giải thưởng. Đồng thời, hệ thống tiếp nhận thông tin từ các nhà tài trợ (nếu có), ghi nhận gói tài trợ bằng hiện vật độc quyền (thảm đấu vô địch, bọc bài quảng bá, phụ kiện chính hãng) và cập nhật hiển thị quyền lợi biểu trưng, áp phích quảng bá trên trang sự kiện. Người chơi đăng ký thi đấu, nộp lệ phí trực tiếp hoặc thanh toán từ xa để hệ thống ghi nhận doanh thu và thực hiện điểm danh trước giờ khai mạc. Bộ môn được tổ chức thường xuyên nhất là Yu-Gi-Oh!. Ban tổ chức sử dụng Challonge để tạo và điều hành giải đấu theo thể thức Swiss, thiết lập số vòng, cách tính điểm, tiêu chí xếp hạng phụ và số người được chọn vào vòng top theo điều lệ đã công bố. Trọng tài xác nhận kết quả từng trận để ban tổ chức cập nhật trên Challonge trước khi tạo cặp đấu cho vòng tiếp theo. Sau vòng Swiss cuối cùng, ban tổ chức kiểm tra bảng xếp hạng, giải quyết khiếu nại và chốt danh sách cắt top; những người đủ điều kiện tiếp tục thi đấu loại trực tiếp để xác định kết quả chung cuộc. Hệ thống cửa hàng lưu đường dẫn giải đấu trên Challonge và kết quả đã được ban tổ chức xác nhận; nhân viên lập phiếu xuất kho các phần quà tài trợ cùng vật phẩm của cửa hàng để trao thưởng, ghi nhận người nhận và hoàn tất báo cáo sự kiện.

#### Chức năng: Quản lý nội dung Fanpage

- **Mục đích:**
   Hoạch định chiến lược, lên lịch, biên soạn, kiểm duyệt và đăng tải các nội dung truyền thông, thông tin sản phẩm, sự kiện giải đấu, chương trình khuyến mãi lên trang mạng xã hội (Fanpage) nhằm thu hút khách hàng, tăng nhận diện thương hiệu và thúc đẩy doanh số bán hàng đa kênh.
- **Đối tượng thực hiện:**
   Nhân viên Marketing, Quản lý cửa hàng, Nền tảng Fanpage.
- **Quy trình hoạt động & xử lý:**
   Quy trình quản lý nội dung Fanpage bắt đầu từ việc Nhân viên Marketing tiến hành lập kế hoạch nội dung định kỳ (tuần/tháng) dựa trên lịch sự kiện giải đấu, các đợt nhập hàng mới hoặc chương trình khuyến mãi. Nhân viên tiến hành soạn thảo nội dung (bài viết, hình ảnh, video ngắn, thiết kế banner) và tạo yêu cầu đăng bài trên hệ thống.
   Sau khi hoàn tất, yêu cầu sẽ được chuyển đến Quản lý cửa hàng để kiểm tra chất lượng, tính chính xác về thông tin sản phẩm/giá bán và thuần phong mỹ tục:
      - Nếu bài viết đạt yêu cầu, Quản lý tiến hành phê duyệt và hệ thống sẽ tự động đăng tải theo lịch hẹn (hoặc đăng ngay lập tức).
      - Nếu bài viết chưa đạt, hệ thống trả về trạng thái yêu cầu chỉnh sửa kèm theo nhận xét của quản lý để nhân viên cập nhật lại.
   Sau khi bài viết được phát hành, hệ thống ghi nhận các chỉ số tương tác ban đầu (lượt thích, bình luận, chia sẻ) để phục vụ công tác đánh giá hiệu quả chiến dịch truyền thông. Trường hợp phát sinh thông tin sai lệch hoặc cần gỡ bỏ, quản lý hoặc nhân viên có quyền thực hiện thao tác cập nhật hoặc ẩn/gỡ bài viết trên hệ thống.
---

## 2. Mô tả các kho dữ liệu (Data Store)

| Mã | Tên kho dữ liệu | Mô tả |
| --- | --- | --- |
| D1 | Hồ sơ sự kiện | Lưu thông tin và kết quả giải đấu. |
| D2 | Danh sách đăng ký giải đấu | Lưu đăng ký và điểm danh người tham gia. |
| D3 | Thông tin tài trợ | Lưu các khoản tài trợ cho sự kiện. |
| D4 | Hàng hóa và tồn kho | Lưu thông tin hàng hóa và số lượng tồn. |
| D5 | Danh mục sản phẩm và giá bán | Lưu danh mục sản phẩm và giá bán. |
| D6 | Mã giảm giá và khuyến mãi | Lưu các ưu đãi bán hàng. |
| D7 | Đơn hàng và hóa đơn | Lưu đơn bán hàng và hóa đơn. |
| D8 | Giao dịch thanh toán | Lưu các giao dịch thu, chi và hoàn tiền. |
| D9 | Hồ sơ giao hàng | Lưu thông tin và trạng thái giao hàng. |
| D10 | Hồ sơ đổi trả và hoàn tiền | Lưu đổi trả và hoàn tiền cho khách hàng. |
| D11 | Đối soát cộng tác viên | Lưu kết quả đối soát hàng và tiền với cộng tác viên. |
| D12 | Đơn đặt hàng nhập | Lưu đơn mua hàng từ nhà cung cấp. |
| D13 | Phiếu nhập kho | Lưu các lần nhập hàng vào kho. |
| D14 | Công nợ nhà cung cấp | Lưu khoản phải trả và nợ còn lại của nhà cung cấp. |
| D15 | Biên bản sự cố và đổi trả nhà cung cấp | Lưu sự cố nhập hàng và kết quả đổi trả. |
| D16 | Kế hoạch nội dung Fanpage | Lưu trữ lịch trình, kế hoạch nội dung tổng thể, mục tiêu chiến dịch và phân công nhân sự thực hiện. |
| D17 | Kho lưu trữ bài viết & tài nguyên truyền thông | Lưu trữ nội dung chi tiết các bài viết, trạng thái bài viết. |
| D18 | Chỉ số tương tác & hiệu suất nội dung | Lưu trữ dữ liệu về lượt tiếp cận, tương tác (like, share, comment) và hiệu quả chuyển đổi từ các bài đăng trên Fanpage. |
| D19 | Hồ sơ nhân viên & CTV | Lưu thông tin nhân viên, cộng tác viên, mức lương và tỉ lệ hoa hồng. |
| D20 | Lịch làm việc | Lưu ca làm việc đã xếp và kết quả duyệt ca, nghỉ. |
| D21 | Chấm công | Lưu dữ liệu chấm công, giờ công thực tế để tính lương và đánh giá. |
| D22 | Bảng lương & hoa hồng | Lưu bảng lương nhân viên và kết quả tính hoa hồng cộng tác viên. |
| D23 | Vị trí lưu trữ | Lưu thông tin khu vực, kệ, ngăn và vị trí lưu trữ hợp lệ. |
| D24 | Sổ Nhật ký Phiếu kho | Lưu lịch sử nhập, xuất và điều chỉnh hàng hóa. |
| D25 | Sổ Kiểm kê và Thất thoát | Lưu kết quả kiểm kê, chênh lệch và xử lý thất thoát. |


## 3. Xây dựng mô hình DFD cho từng chức năng

### Chức năng: Nhập Hàng

####  Bảng danh sách câu hỏi và trả lời

##### **a. Danh sách câu hỏi và trả lời liên quan đến các ô xử lý (Process)**

1. **Mức 1 được phân rã thành bao nhiêu tiến trình?**
   Có 5 tiến trình: 1.1 Lập đơn đặt hàng; 1.2 Kiểm nhận hàng; 1.3 Lập phiếu nhập, cập nhật tồn kho và công nợ; 1.4 Xử lý sự cố, đổi trả; 1.5 Thanh toán nhà cung cấp.
2. **Tiến trình 1.1 được phân rã thành những tiến trình nào?**
   1.1.1 Kiểm tra tồn kho, xác định nhu cầu nhập; 1.1.2 Lập thông tin đơn đặt hàng; 1.1.3 Lưu và gửi đơn đặt hàng.
3. **Tiến trình 1.2 được phân rã thành những tiến trình nào?**
   1.2.1 Tiếp nhận thông tin hàng và chứng từ; 1.2.2 Đối chiếu đơn, kiểm đếm số lượng; 1.2.3 Đánh giá chất lượng, tổng hợp kiểm nhận.
4. **Tiến trình 1.3 được phân rã thành những tiến trình nào?**
   1.3.1 Lập phiếu nhập kho; 1.3.2 Cập nhật số lượng tồn kho; 1.3.3 Ghi nhận công nợ, trạng thái đơn nhập.
5. **Tiến trình 1.4 được phân rã thành những tiến trình nào?**
   1.4.1 Lập biên bản sự cố; 1.4.2 Lập và gửi yêu cầu đổi trả; 1.4.3 Ghi nhận kết quả xử lý đổi trả.
6. **Tiến trình 1.5 được phân rã thành những tiến trình nào?**
   1.5.1 Đối chiếu công nợ cần thanh toán; 1.5.2 Lập thông tin thanh toán nhà cung cấp; 1.5.3 Xác nhận, ghi giao dịch và cập nhật công nợ.
7. **Nếu lô hàng chỉ có một phần đạt yêu cầu thì xử lý thế nào?**
   1.2.3 chuyển phần đạt sang 1.3 để nhập kho; phần lỗi hoặc thiếu hụt chuyển sang 1.4 để lập biên bản và yêu cầu xử lý.
8. **Nếu chứng từ không khớp đơn đặt hàng hoặc chưa xác định được đơn thì xử lý ở đâu?**
   1.2.2 đối chiếu và yêu cầu làm rõ trước khi ghi nhận nhập kho. Trường hợp thiếu thông tin đơn hoặc chứng từ chưa có nhánh xử lý riêng trên sơ đồ.

##### **b. Danh sách câu hỏi và trả lời liên quan đến các dòng dữ liệu (Data Flow)**

1. **Nhà cung cấp gửi và nhận những dữ liệu gì?**
   Nhà cung cấp nhận đơn đặt hàng, biên bản/yêu cầu đổi trả và thông tin thanh toán; gửi thông tin hàng/chứng từ, kết quả xử lý đổi trả và xác nhận thanh toán.
2. **Luồng 1.2 → 1.3 mang dữ liệu gì?**
   Thông tin hàng nhập đã kiểm nhận đạt, gồm hàng được chấp nhận, số lượng thực nhận, giá nhập và chứng từ liên quan.
3. **Luồng 1.2 → 1.4 mang dữ liệu gì?**
   Thông tin hàng lỗi, thiếu hụt và kết quả kiểm tra để lập biên bản sự cố.
4. **Nếu nhà cung cấp giao hàng thay thế thì dữ liệu đi đâu?**
   Thông tin hàng thay thế và chứng từ đi vào 1.2 để kiểm nhận lại; phản hồi đổi trả vào 1.4 không trực tiếp làm tăng tồn kho.
5. **Nếu chưa nhận được xác nhận thanh toán thì có giảm công nợ không?**
   Chưa giảm công nợ; cần giữ trạng thái chờ xác nhận. Nhánh chờ hoặc thanh toán thất bại chưa được thể hiện riêng trên sơ đồ.
6. **Các luồng giữa mức 0 và mức 1 đã cân bằng chưa?**
   Mức 0 hiện chưa nêu thông tin thanh toán, xác nhận thanh toán và kết quả xử lý đổi trả có ở mức 1; cần bổ sung vào nội dung hai luồng tổng hợp để giữ cách vẽ hai mũi tên.

##### **c. Danh sách câu hỏi và trả lời liên quan đến các kho dữ liệu (Data Store)**

1. **Các kho dữ liệu nào được dùng trong nhập hàng?**
   D4 Hàng hóa và tồn kho; D8 Giao dịch thanh toán; D12 Đơn đặt hàng nhập; D13 Phiếu nhập kho; D14 Công nợ nhà cung cấp; D15 Biên bản sự cố và đổi trả nhà cung cấp.
2. **Vì sao lập đơn nhập dùng D4 mà không dùng D5?**
   D4 đã cung cấp thông tin hàng hóa và số lượng tồn để xác định nhu cầu nhập. D5 phục vụ danh mục và giá bán, không cần cho quy trình này.
3. **Các tiến trình chính tra cứu/cập nhật những kho nào?**
   1.1 đọc D4, ghi D12; 1.2 đọc D12; 1.3 ghi D13, cập nhật D4, D12 và D14; 1.4 ghi/cập nhật D15; 1.5 đọc/cập nhật D14 và ghi D8.
4. **D8 và D14 khác nhau thế nào?**
   D8 lưu từng giao dịch thanh toán; D14 theo dõi khoản phải trả và số công nợ còn lại của nhà cung cấp.
5. **Nếu thanh toán một phần công nợ thì cập nhật kho nào?**
   1.5.3 ghi số tiền đã thanh toán vào D8 và giảm khoản nợ tương ứng trong D14; phần chưa trả vẫn được theo dõi.
6. **Nếu cùng một phiếu nhập được ghi nhận hai lần thì cần xử lý thế nào?**
   Cần kiểm tra phiếu đã ghi nhận tại D13 trước khi cập nhật D4 và D14 để tránh tăng tồn và công nợ hai lần. Sơ đồ hiện chưa thể hiện luồng kiểm tra trùng này.

##### **d. Danh sách câu hỏi và trả lời liên quan đến các thực thể ngoài (External Entity)**

1. **Thực thể ngoài của chức năng nhập hàng là ai?**
   Nhà cung cấp là thực thể ngoài, xuất hiện một lần trong mỗi sơ đồ có trao đổi dữ liệu với nhà cung cấp.
2. **Vì sao nhân viên và quản lý không được vẽ thành thực thể ngoài?**
   Trong phạm vi mô hình đang chọn, họ là người vận hành nội bộ, thực hiện lập đơn, kiểm nhận và ghi nhận dữ liệu trên hệ thống.
3. **Nếu nhà cung cấp chưa phản hồi hoặc từ chối đổi trả thì xử lý thế nào?**
   Theo dõi hồ sơ chờ xử lý hoặc ghi nhận kết quả từ chối trong D15; không tự nhập kho phần hàng bị từ chối. Các nhánh này chưa được vẽ riêng.
4. **Nếu nhà cung cấp xác nhận số tiền nhận được khác số tiền đã ghi thì xử lý thế nào?**
   1.5.3 cần đối chiếu và làm rõ chênh lệch trước khi xác nhận giao dịch, giảm công nợ. Nhánh sai lệch thanh toán chưa được thể hiện riêng trên sơ đồ.

#### Mô hình mức ngữ cảnh (Context Level)

![DFD Mức 0 - Nhập hàng](./images/nhaphang/DFD_muc0.png)


#### Mô hình mức đỉnh (Level 1)

![DFD Mức 1 - Nhập hàng](./images/nhaphang/DFD_muc1.png)


#### Mô hình mức dưới đỉnh (Level 2)

![DFD Mức 2 - 1.1 Lập đơn đặt hàng](./images/nhaphang/DFD_muc2_LapDon_DatHang.png)

![DFD Mức 2 - 1.2 Kiểm nhận hàng](./images/nhaphang/DFD_muc2_KiemNhan_Hang.png)

![DFD Mức 2 - 1.3 Lập phiếu nhập, cập nhật tồn kho và công nợ](./images/nhaphang/DFD_muc2_LapPhieuNhap_CapNhatKho_CongNo.png)

![DFD Mức 2 - 1.4 Xử lý sự cố, đổi trả](./images/nhaphang/DFD_muc2_XuLySuCo_DoiTra.png)

![DFD Mức 2 - 1.5 Thanh toán nhà cung cấp](./images/nhaphang/DFD_muc2_ThanhToan_NhaCungCap.png)


### Chức năng: Bán Hàng

####  Bảng danh sách câu hỏi và trả lời
##### **a. Danh sách câu hỏi và trả lời liên quan đến các ô xử lý (Process)**

1. **Mức 1 được phân rã thành bao nhiêu tiến trình?**
   Có 5 tiến trình: 2.1 Tiếp nhận và kiểm tra đơn hàng; 2.2 Xử lý thanh toán và lập hóa đơn; 2.3 Gửi yêu cầu và theo dõi giao hàng; 2.4 Xử lý đổi trả và hoàn tiền; 2.5 Cấp hàng và đối soát cộng tác viên.
2. **Tiến trình 2.1 được phân rã thành những tiến trình nào?**
   Có 4 tiến trình: 2.1.1 Tiếp nhận thông tin đặt hàng; 2.1.2 Kiểm tra sản phẩm và giá; 2.1.3 Kiểm tra tồn kho; 2.1.4 Kiểm tra khuyến mãi và tính tổng đơn.
3. **2.2 được phân rã thành những tiến trình nào?**
   2.2.1 Tiếp nhận đơn hàng và phương thức thanh toán; 2.2.2 Ghi nhận giao dịch thanh toán; 2.2.3 Xác nhận thanh toán và lập hóa đơn; 2.2.4 Trả kết quả và chuyển đơn giao.
4. **2.3, 2.4 và 2.5 mỗi tiến trình có bao nhiêu tiến trình con?**
   Mỗi tiến trình có 4 tiến trình con. 2.3 gồm tiếp nhận đơn đã thanh toán, chuẩn bị/gửi yêu cầu giao, cập nhật mã vận đơn/trạng thái và thông báo tình trạng giao hàng. 2.4 gồm tiếp nhận yêu cầu đổi trả, kiểm tra điều kiện, ghi nhận đổi trả/yêu cầu hoàn tiền và xử lý hoàn tiền/thông báo kết quả. 2.5 gồm tiếp nhận yêu cầu cấp hàng, kiểm tra tồn kho/cấp hàng, đối chiếu báo cáo doanh số và ghi nhận chuyển tiền/kết quả đối soát.
5. **Nếu sản phẩm hết hàng hoặc chỉ một phần đơn đủ hàng, tiến trình nào xử lý?**
   2.1.3 kiểm tra tồn kho. Với đơn online thiếu hoặc hết hàng, Nhân viên xử lý đơn trực tuyến thông báo khách hủy đơn và ghi nhận kết quả; không tự tách giao hoặc cho chờ nhập hàng. DFD cần thể hiện luồng thông báo và kết quả hủy.
6. **Nếu thanh toán thất bại, tiến trình nào trả kết quả và có chuyển đơn giao không?**
   2.2.2 ghi nhận giao dịch và số tiền thực nhận; nếu chuyển thiếu, thông báo khách chuyển bổ sung và lưu các bill cùng đơn. Quản lý cửa hàng xác nhận đã nhận đủ tiền tại 2.2.3 trước khi ghi nhận thanh toán hoàn tất; 2.2.4 trả kết quả. Đơn thanh toán thất bại hoặc đang chờ không được ghi nhận hoàn tất thanh toán; DFD cần bổ sung nhánh chờ, chuyển thiếu và kết quả xác nhận của quản lý.
7. **Nếu yêu cầu đổi trả không đủ điều kiện hoặc hoàn tiền lỗi thì xử lý ở đâu?**
   2.4.2 kiểm tra điều kiện; 2.4.4 xử lý hoàn tiền và thông báo. Cần bổ sung đầu ra từ chối có lý do và trạng thái hoàn tiền chờ/thất bại nếu hệ thống hỗ trợ xử lý lại.

##### **b. Danh sách câu hỏi và trả lời liên quan đến các dòng dữ liệu (Data Flow)**

1. **Khách hàng gửi những dữ liệu gì vào hệ thống?**
   Khách tại quầy gửi thông tin mua hàng và yêu cầu đổi trả; khách trực tuyến gửi thông tin đặt hàng, người nhận, phương thức thanh toán và yêu cầu đổi trả.
2. **Hệ thống trả dữ liệu gì cho khách hàng?**
   Thông tin thanh toán/hóa đơn, xác nhận đơn hàng, mã vận đơn khi có giao hàng, hoặc kết quả đổi trả và thông tin hoàn tiền.
3. **Cộng tác viên gửi và nhận dữ liệu gì?**
   CTV gửi yêu cầu cấp hàng, báo cáo doanh số và thông tin chuyển tiền; hệ thống gửi xác nhận cấp hàng, thông tin tồn kho, kết quả đối soát và số tiền phải nộp.
4. **Nếu mã giảm giá sai, hết hạn hoặc không đạt điều kiện thì luồng phản hồi nào cần có?**
   2.1.4 nên trả lý do không áp dụng và tổng tiền tính lại để khách xác nhận. Sơ đồ hiện có luồng điều kiện khuyến mãi nhưng chưa thể hiện nhánh từ chối mã.
5. **Nếu cổng thanh toán không phản hồi thì khách và hệ thống nhận trạng thái gì?**
   Cần có trạng thái đang chờ hoặc chưa xác định; không gửi xác nhận thanh toán thành công hay yêu cầu giao hàng cho đến khi có kết quả cuối. Nhánh này chưa có trên sơ đồ.
6. **Nếu đơn vị vận chuyển chưa trả mã vận đơn hoặc báo giao thất bại thì luồng dữ liệu đi đâu?**
   2.3.3 cập nhật trạng thái/mã vận đơn vào D9; 2.3.4 thông báo khách. Cần thể hiện trạng thái chờ, giao thất bại hoặc hoàn hàng nếu nằm trong phạm vi hệ thống.
7. **Nếu CTV nộp thiếu tiền so với doanh số đối chiếu thì dữ liệu chênh lệch đi đâu?**
   2.5.4 cần ghi nhận số phải nộp, số thực nhận, phần chênh lệch và trạng thái đối soát vào D11; cần có luồng thông báo/đề nghị bổ sung nếu quy trình yêu cầu.
8. **Nếu khách hủy đơn sau khi đã gửi yêu cầu giao hàng thì cần trao đổi dữ liệu gì?**
   Nếu mới gửi yêu cầu giao nhưng chưa bàn giao hàng, nhân viên hủy yêu cầu giao và cập nhật trạng thái đơn/giao hàng. Khi hàng đã được bàn giao cho đơn vị vận chuyển, không chấp nhận hủy theo quy trình này; yêu cầu trả hàng được kiểm tra theo điều kiện đổi trả. Shop chịu phí giao; khách chịu phí hoàn hàng. DFD cần bổ sung các phản hồi tương ứng.

##### **c. Danh sách câu hỏi và trả lời liên quan đến các kho dữ liệu (Data Store)**

1. **Các kho dữ liệu nào xuất hiện trong các sơ đồ bán hàng?**
   D4 Hàng hóa và tồn kho; D5 Danh mục sản phẩm và giá bán; D6 Mã giảm giá và khuyến mãi; D7 Đơn hàng và hóa đơn; D8 Giao dịch thanh toán; D9 Hồ sơ giao hàng; D10 Hồ sơ đổi trả và hoàn tiền; D11 Đối soát cộng tác viên.
2. **Các tiến trình chính tra cứu/cập nhật những kho nào?**
   2.1 tra cứu D4–D6; 2.2 ghi/tra cứu D7–D8; 2.3 cập nhật D9; 2.4 tra cứu D7, cập nhật D8 khi hoàn tiền và ghi D10; 2.5 tra cứu/cập nhật D4, đối chiếu D7 và cập nhật D11.
3. **D8 cần lưu gì để phân biệt giao dịch thành công, thất bại, đang chờ và hoàn tiền?**
   Nên có mã giao dịch, mã đơn, số tiền, phương thức, thời điểm và trạng thái. Sơ đồ hiện chưa nêu rõ các trạng thái chi tiết.
4. **D9 và D10 cần lưu gì để xử lý lỗi giao hàng hoặc hoàn tiền?**
   D9 nên lưu mã vận đơn, trạng thái gần nhất, thời điểm cập nhật và lý do giao thất bại. D10 nên lưu điều kiện/kết quả đổi trả, số tiền và trạng thái hoàn tiền cùng lịch sử xử lý.
5. **D11 cần lưu gì khi số tiền CTV nộp không khớp?**
   Nên lưu doanh số báo cáo, số phải nộp, số thực nhận, chênh lệch, trạng thái và ghi chú xử lý để tiếp tục đối soát.
6. **Khi hủy đơn hoặc nhận hàng đổi trả, lúc nào D4 được cập nhật?**
   Khi hủy đơn trước bàn giao, chỉ hoàn lại lượng tồn đã giảm từ đơn đó, sau khi đối chiếu hàng vẫn còn tại cửa hàng; không tăng tồn nếu đơn chưa từng làm giảm tồn. Với hàng đổi trả, chỉ tăng tồn sau khi nhận hàng thực tế, được Quản lý cửa hàng xác nhận đạt tiêu chuẩn bán lại và hoàn tất nhập kho. Hàng chờ xử lý hoặc bị loại bỏ không được cộng tồn; mỗi lần hoàn tồn chỉ ghi nhận một lần.

##### **d. Danh sách câu hỏi và trả lời liên quan đến các thực thể ngoài (External Entity)**

1. **Các thực thể ngoài của hệ thống bán hàng là ai?**
   Khách hàng tại quầy, khách hàng trực tuyến, cộng tác viên và đơn vị vận chuyển.
2. **Vai trò và dữ liệu trao đổi của từng thực thể là gì?**
   Hai nhóm khách hàng đặt mua/yêu cầu đổi trả; CTV yêu cầu cấp hàng, gửi báo cáo doanh số và chuyển tiền; đơn vị vận chuyển nhận thông tin giao hàng và trả mã vận đơn/trạng thái.
3. **Khách hàng cần nhận gì khi đơn bị từ chối, thanh toán lỗi hoặc đổi trả không đạt điều kiện?**
   Cần nhận trạng thái kèm lý do và bước tiếp theo (sửa đơn, thử thanh toán lại hoặc bổ sung thông tin). Những phản hồi lỗi này cần được thêm vào sơ đồ.
4. **Nếu CTV không gửi báo cáo hoặc chứng từ chuyển tiền đúng kỳ thì thực thể nào khởi tạo nhắc nhở?**
   Cần xác định hệ thống hay nhân viên phụ trách đối soát sẽ nhắc CTV; quy trình quá hạn hiện chưa có trong sơ đồ.
5. **Nếu đơn vị vận chuyển báo giao thất bại, giao nhầm hoặc hoàn hàng thì ai cần được thông báo?**
   Hệ thống cần cập nhật D9 và thông báo khách trực tuyến cùng nhân viên xử lý đơn; cần xác nhận phạm vi và bổ sung các luồng thông báo tương ứng.

#### Mô hình mức ngữ cảnh (Context Level)

![DFD Mức 0 - Bán hàng](./images/banhang/DFD_muc0.png)

#### Mô hình mức đỉnh (Level 1)

![DFD Mức 1 - Bán hàng](./images/banhang/DFD_muc1.png)

#### Mô hình mức dưới đỉnh (Level 2)

![DFD Mức 2 - 2.1 Tiếp nhận và kiểm tra đơn hàng](./images/banhang/DFD_muc2_1_TiepNhanKiemTraDonHang.png)

![DFD Mức 2 - 2.2 Thanh toán và lập hóa đơn](./images/banhang/DFD_muc2_2_ThanhToanLapHoaDon.png)

![DFD Mức 2 - 2.3 Theo dõi giao hàng](./images/banhang/DFD_muc2_3_TheoDoiGiaoHang.png)

![DFD Mức 2 - 2.4 Đổi trả và hoàn tiền](./images/banhang/DFD_muc2_4_DoiTraHoanTien.png)

![DFD Mức 2 - 2.5 Cấp hàng và đối soát cộng tác viên](./images/banhang/DFD_muc2_5_CapHangDoiSoatCTV.png)

### Chức năng: Tổ Chức Giải Đấu & Tài Trợ Sự Kiện

####  Bảng danh sách câu hỏi và trả lời
Câu hỏi 1: Xác định các tác nhân ngoài tương tác trực tiếp với chức năng "Tổ Chức Giải Đấu & Tài Trợ Sự Kiện"?
Trả lời:Các tác nhân ngoài bao gồm: Người tham gia (đăng ký, nộp lệ phí, thi đấu), Nhà tài trợ (cung cấp kinh phí, hiện vật tài trợ), và Trọng tài sự kiện (cập nhật tỷ số, kết quả thi đấu). Quản lý giải đấu là người vận hành bên trong hệ thống.

Câu hỏi 2: Kho lưu trữ dữ liệu chính nào được sử dụng trong quá trình xử lý giải đấu và tài trợ?
Trả lời: Các kho dữ liệu chính gồm: Kho thông tin sự kiện/giải đấu, Kho dữ liệu người tham gia & đăng ký, Kho tài trợ, và liên kết với Kho hàng/Tồn kho (khi xuất vật phẩm trao thưởng).

Câu hỏi 3: Luồng dữ liệu chính đi từ người tham gia vào hệ thống trong quy trình này là gì?
Trả lời: Thông tin đăng ký tham gia giải đấu, thông tin xác nhận nộp lệ phí (hoặc thanh toán lệ phí).

Câu hỏi 4: Nhiệm vụ của tiến trình xử lý kết quả và trao thưởng trong mô hình mức đỉnh là gì?
Trả lời: Hệ thống tự động tổng kết bảng xếp hạng chung cuộc dựa trên tỷ số do trọng tài cập nhật, đồng thời tạo phiếu xuất kho các phần quà tài trợ và vật phẩm của cửa hàng để trao thưởng cho đấu thủ chiến thắng.

#### Mô hình mức ngữ cảnh (Context Level)

![DFD Mức ngữ cảnh - Giải đấu và Tài trợ](./images/giaidau/DFD_muc0.png)

#### Mô hình mức đỉnh (Level 1)

![DFD Mức 1 - Giải đấu và Tài trợ](./images/giaidau/DFD_muc1.png)

#### Mô hình mức dưới đỉnh (Level 2)

![DFD Mức 2 - Quản lí Đăng kí & Điểm danh](./images/giaidau/DFD_muc2_DangKy_DiemDanh.png)

![DFD Mức 2 - Quản lí Tài trợ sự kiện](./images/giaidau/DFD_muc2_TaiTroSK.png)

![DFD Mức 2 - Xếp lịch & Vận hành thi đấu](./images/giaidau/DFD_muc2_XepLich_VanHanh.png)

![DFD Mức 2 - Tổng kết và trao thưởng](./images/giaidau/DFD_muc2_TongKet_TraoThuong.png)

---

### Chức năng: Quản lý Kho

#### Mô hình mức ngữ cảnh (Context Level)

![DFD mức ngữ cảnh — Quản lý Kho nội bộ](./images/quanlykho/DFD_muc0.png)

#### Mô hình mức đỉnh (Level 1)

![DFD mức 1 — Quản lý Kho nội bộ](./images/quanlykho/DFD_muc1.png)

#### Mô hình mức dưới đỉnh (Level 2)

**1.0 — Tiếp nhận và bố trí hàng**

![DFD mức 2 — 1.0 Tiếp nhận và bố trí hàng](./images/quanlykho/DFD_muc2_1_TiepNhanBoTriHang.png)

**2.0 — Thực hiện xuất kho**

![DFD mức 2 — 2.0 Thực hiện xuất kho](./images/quanlykho/DFD_muc2_2_XuatKho.png)

**3.0 — Kiểm kê và điều chỉnh**

![DFD mức 2 — 3.0 Kiểm kê và điều chỉnh](./images/quanlykho/DFD_muc2_3_KiemKeDieuChinh.png)

**4.0 — Theo dõi tồn và báo cáo kho**

![DFD mức 2 — 4.0 Theo dõi tồn và báo cáo kho](./images/quanlykho/DFD_muc2_4_TheoDoiBaoCao.png)

#### Bảng danh sách câu hỏi và trả lời

##### **a. Danh sách câu hỏi và trả lời liên quan đến các ô xử lý (Process)**

1. **Mức 1 gồm những tiến trình nào?**
   1.0 Tiếp nhận và bố trí hàng; 2.0 Thực hiện xuất kho; 3.0 Kiểm kê và điều chỉnh; 4.0 Theo dõi tồn và báo cáo kho.

2. **Tiến trình 1.0 được phân rã như thế nào?**
   1.1 Tiếp nhận và xác định vị trí; 1.2 Xác minh xếp hàng thực tế; 1.3 Ghi nhận nhập và phản hồi.

3. **Tiến trình 2.0 được phân rã như thế nào?**
   2.1 Kiểm tra lệnh xuất và tồn; 2.2 Hướng dẫn và xác minh xuất; 2.3 Ghi nhận xuất và phản hồi.

4. **Khi lệnh xuất bị từ chối hoặc chưa đủ hàng, tiến trình nào phản hồi?**
   2.1 chuyển “Kết quả từ chối / chưa đủ hàng” cho 2.3 để trả “Kết quả xử lý xuất kho” về Phân hệ Bán hàng / Giải đấu.

5. **Tiến trình 3.0 xử lý kiểm kê và điều chỉnh như thế nào?**
   3.1 Đối chiếu kiểm kê; 3.2 Lập và cập nhật biên bản; 3.3 Tiếp nhận quyết định xử lý; 3.4 Thực hiện xử lý được duyệt.

6. **Tiến trình 4.0 được phân rã như thế nào?**
   4.1 Tổng hợp tồn theo vị trí; 4.2 Tổng hợp biến động và kiểm kê; 4.3 Lập báo cáo theo yêu cầu.

##### **b. Danh sách câu hỏi và trả lời liên quan đến các dòng dữ liệu (Data Flow)**

1. **Phân hệ Nhập hàng trao đổi dữ liệu gì với Kho?**
   Gửi “Thông tin hàng đã kiểm nhận” vào 1.1; nhận “Kết quả nhập kho” từ 1.3.

2. **Các luồng nội bộ trong phân rã 1.0 là gì?**
   1.1 → 1.2: “Thông tin nhập và vị trí đề xuất”; 1.2 → 1.3: “Kết quả xác minh, Số lượng và vị trí thực tế”.

3. **Phân hệ Bán hàng / Giải đấu trao đổi dữ liệu gì với Kho?**
   Gửi “Lệnh xuất kho đã duyệt” vào 2.1; nhận “Kết quả xử lý xuất kho” từ 2.3.

4. **Các luồng nội bộ trong phân rã 2.0 là gì?**
   2.1 → 2.2: “Lệnh đủ hàng và vị trí lấy hàng”; 2.2 → 2.3: “Kết quả xác minh xuất thực tế”; 2.1 → 2.3: “Kết quả từ chối / chưa đủ hàng”.

5. **Nhân viên kho gửi và nhận những dữ liệu gì?**
   Gửi “Xác nhận xếp hàng thực tế” vào 1.2, “Xác nhận xuất hàng thực tế” vào 2.2 và “Số lượng và tình trạng hàng” vào 3.1. Nhận “Hướng dẫn xếp hàng” từ 1.1, “Hướng dẫn lấy hàng” từ 2.2, “Kết quả đối chiếu” từ 3.1 và “Thông tin số lượng hàng” từ 4.1.

6. **Quản lý cửa hàng gửi và nhận những dữ liệu gì?**
   Nhận “Yêu cầu xử lý” từ 3.2 và “Báo cáo số lượng hàng và biến động” từ 4.3; gửi “Quyết định xử lý” vào 3.3 và “Yêu cầu báo cáo kho” vào 4.3.

7. **Các luồng nội bộ trong phân rã 3.0 là gì?**
   3.1 → 3.2: “Số đếm, tình trạng và chênh lệch”; 3.2 → 3.3: “Hồ sơ đề nghị xử lý”; 3.3 → 3.4: “Quyết định đã đối chiếu với hồ sơ chênh lệch”; 3.4 → 3.2: “Kết quả xử lý và trạng thái duyệt”.

8. **Tiến trình lập báo cáo nhận dữ liệu tổng hợp nào?**
   4.3 nhận “Số lượng hàng đã tổng hợp” từ 4.1 và “Biến động và kết quả kiểm kê đã tổng hợp” từ 4.2 để lập báo cáo theo yêu cầu của quản lý.

##### **c. Danh sách câu hỏi và trả lời liên quan đến các kho dữ liệu (Data Store)**

1. **D4 (Hàng hóa và tồn kho) nhận và cung cấp dữ liệu gì?**
   Nhận “Số lượng và vị trí sau nhập” từ 1.3, “Số lượng còn lại sau xuất” từ 2.3 và “Số lượng sau điều chỉnh được duyệt” từ 3.4. Cung cấp “Số lượng có thể xuất và vị trí hàng” cho 2.1, “Số lượng ghi nhận theo vị trí” cho 3.1 và “Số lượng hàng theo mặt hàng và vị trí” cho 4.1.

2. **D23 (Vị trí lưu trữ) cung cấp dữ liệu gì?**
   Cung cấp “Vị trí lưu trữ hợp lệ” cho 1.1 để xác định vị trí bố trí hàng.

3. **D24 (Sổ Nhật ký Phiếu kho) nhận và cung cấp dữ liệu gì?**
   Nhận “Nhật ký nhập” từ 1.3, “Nhật ký xuất” từ 2.3 và “Nhật ký điều chỉnh” từ 3.4; cung cấp “Lịch sử biến động kho” cho 4.2.

4. **D25 (Sổ Kiểm kê và Thất thoát) nhận và cung cấp dữ liệu gì?**
   Nhận “Biên bản, chênh lệch, Kết quả và trạng thái duyệt” từ 3.2; cung cấp “Hồ sơ chênh lệch chờ xử lý” cho 3.3 và “Kết quả kiểm kê và thất thoát” cho 4.2.

##### **d. Danh sách câu hỏi và trả lời liên quan đến các thực thể ngoài (External Entity)**

1. **Sơ đồ kho nội bộ có những thực thể ngoài nào?**
   Nhân viên kho, Quản lý cửa hàng, Phân hệ Nhập hàng và Phân hệ Bán hàng / Giải đấu.

2. **Vì sao Phân hệ Nhập hàng và Phân hệ Bán hàng / Giải đấu là thực thể ngoài?**
   Hai phân hệ nằm ngoài phạm vi quản lý kho nội bộ, cung cấp thông tin hàng đã kiểm nhận hoặc lệnh xuất kho đã duyệt và nhận kết quả xử lý.

3. **Nhân viên kho có vai trò gì?**
   Thực hiện xếp, lấy hàng theo hướng dẫn; xác nhận thao tác thực tế và cung cấp số lượng, tình trạng hàng để đối chiếu kiểm kê.

4. **Quản lý cửa hàng có vai trò gì?**
   Quyết định xử lý chênh lệch và yêu cầu báo cáo kho; nhận yêu cầu xử lý cùng báo cáo số lượng hàng và biến động.

---


### Chức năng: Quản lý Nhân Viên và Cộng Tác Viên

#### Bảng danh sách câu hỏi và trả lời

##### **a. Danh sách câu hỏi và trả lời liên quan đến các ô xử lý (Process)**

1. **Mức ngữ cảnh có bao nhiêu tiến trình và được phân rã như thế nào ở mức 1?**
   Mức ngữ cảnh có một tiến trình: 4 — Hệ thống Quản lý Nhân viên và Cộng tác viên. Mức 1 phân rã thành bốn tiến trình: 4.1 Quản lý hồ sơ nhân viên & CTV; 4.2 Phân ca & Chấm công; 4.3 Tính lương & Hoa hồng; 4.4 Đánh giá & Báo cáo nhân sự.
2. **Tiến trình 4.1 có nhiệm vụ gì và được phân rã thành những tiến trình nào?**
   4.1 tiếp nhận thông tin cá nhân của Nhân viên và CTV, kiểm tra rồi lưu hồ sơ vào D19. Mức 2 gồm 4.1.1 Tiếp nhận & Kiểm tra thông tin và 4.1.2 Lưu hồ sơ nhân viên & CTV. Sơ đồ hiện không có bước phê duyệt hồ sơ.
3. **Tiến trình 4.2 được phân rã thành những tiến trình nào?**
   Có bốn tiến trình: 4.2.1 Tiếp nhận đăng kí ca; 4.2.2 Tiếp nhận yêu cầu nghỉ; 4.2.3 Xếp lịch & Xử lý duyệt ca, nghỉ; 4.2.4 Ghi nhận chấm công.
4. **Ai quyết định duyệt ca, duyệt nghỉ và tiến trình nào xử lý quyết định đó?**
   Quản lí cửa hàng quyết định duyệt. 4.2.3 tổng hợp yêu cầu ca, nghỉ và danh sách nhân viên, gửi yêu cầu cần duyệt cho Quản lí, nhận kết quả duyệt, thông báo cho Nhân viên và ghi lịch làm việc vào D20.
5. **Nếu Nhân viên xin nghỉ thì yêu cầu được xử lý như thế nào?**
   4.2.2 tiếp nhận yêu cầu nghỉ và chuyển cho 4.2.3. Sau khi nhận quyết định từ Quản lí, 4.2.3 gửi lịch làm việc, thông báo duyệt nghỉ cho Nhân viên và cập nhật D20.
6. **Tiến trình 4.2.4 thực hiện việc gì?**
   4.2.4 nhận dữ liệu chấm công từ Nhân viên và ghi vào D21. Sơ đồ hiện chỉ thể hiện ghi nhận chấm công, chưa có luồng đọc D20 để đối chiếu với lịch làm việc.
7. **Tiến trình 4.3 được phân rã như thế nào?**
   4.3.1 Tổng hợp giờ công & Doanh số nhận giờ công từ D21 và báo cáo doanh số từ CTV. 4.3.2 Tính lương & Hoa hồng sử dụng dữ liệu tổng hợp, mức lương và tỉ lệ hoa hồng từ D19, cùng mức hoa hồng từ Quản lí. 4.3.3 Lập phiếu lương & Ghi nhận hoa hồng gửi kết quả cho Nhân viên, CTV và lưu bảng lương, hoa hồng vào D22.
8. **Tiến trình 4.4 được phân rã như thế nào?**
   4.4.1 Tổng hợp dữ liệu nhân sự đọc dữ liệu chấm công từ D21 và dữ liệu lương, hoa hồng từ D22. 4.4.2 Đánh giá hiệu suất tạo kết quả đánh giá cho Nhân viên và chuyển kết quả đánh giá hiệu suất cho 4.4.3 Lập báo cáo nhân sự. 4.4.3 gửi báo cáo cho Quản lí cửa hàng.
9. **Sơ đồ hiện có đủ dữ liệu để đánh giá đi muộn hoặc nghỉ không đúng lịch không?**
   Chưa thể hiện đủ: 4.4 chỉ đọc D21 và D22, chưa đọc lịch làm việc từ D20. Nếu bổ sung đối chiếu công thực tế với lịch dự kiến, cần cập nhật luồng dữ liệu ở cả mức 1 và mức 2.

##### **b. Danh sách câu hỏi và trả lời liên quan đến các dòng dữ liệu (Data Flow)**

1. **Nhân viên gửi những dữ liệu gì vào hệ thống?**
   Thông tin cá nhân vào 4.1; đăng kí ca, yêu cầu nghỉ và dữ liệu chấm công vào 4.2. Ở mức 2, các luồng lần lượt vào 4.1.1, 4.2.1, 4.2.2 và 4.2.4.
2. **Hệ thống trả những dữ liệu gì cho Nhân viên?**
   Lịch làm việc, thông báo duyệt nghỉ từ 4.2; phiếu lương từ 4.3; kết quả đánh giá từ 4.4. Ở mức 2, các luồng lần lượt do 4.2.3, 4.3.3 và 4.4.2 cung cấp.
3. **CTV gửi và nhận những dữ liệu gì?**
   CTV gửi thông tin cá nhân vào 4.1.1 và báo cáo doanh số vào 4.3.1; nhận mức hoa hồng từ 4.3.3. Theo nghiệp vụ đã mô tả, CTV dùng mức hoa hồng để tự trừ khi chuyển tiền lại cho cửa hàng; sơ đồ không biểu diễn việc chuyển tiền thực tế.
4. **Quản lí cửa hàng gửi và nhận những dữ liệu gì?**
   Quản lí gửi duyệt ca, duyệt nghỉ vào 4.2.3 và mức hoa hồng vào 4.3.2; nhận ca, nghỉ cần duyệt từ 4.2.3 và báo cáo nhân sự từ 4.4.3.
5. **Các luồng nội bộ trong phân rã 4.1 và 4.2 là gì?**
   4.1.1 → 4.1.2: “Thông tin đã kiểm tra”; 4.2.1 → 4.2.3: “Yêu cầu ca”; 4.2.2 → 4.2.3: “Yêu cầu nghỉ”.
6. **Các luồng nội bộ trong phân rã 4.3 và 4.4 là gì?**
   4.3.1 → 4.3.2: “Giờ công và doanh số tổng hợp”; 4.3.2 → 4.3.3: “Kết quả tính lương, hoa hồng”; 4.4.1 → 4.4.2: “Dữ liệu nhân sự tổng hợp”; 4.4.2 → 4.4.3: “Kết quả đánh giá hiệu suất”.
7. **Lịch làm việc và dữ liệu chấm công được ghi theo những luồng nào?**
   Ở mức 1, 4.2 ghi “Lịch làm việc” vào D20 và “Dữ liệu chấm công” vào D21. Ở mức 2, hai luồng tương ứng do 4.2.3 và 4.2.4 thực hiện.
8. **Các luồng giữa mức ngữ cảnh, mức 1 và mức 2 được cân bằng như thế nào?**
   Các luồng vào, ra với từng thực thể ở mức ngữ cảnh được phân bổ cho các tiến trình tương ứng ở mức 1. Khi phân rã mức 2, giữ nguyên dữ liệu trao đổi qua ranh giới tiến trình cha; chỉ thêm luồng nội bộ giữa các tiến trình con. Ví dụ, “Đăng kí ca, Yêu cầu nghỉ” vào 4.2 được tách thành hai luồng vào 4.2.1 và 4.2.2.
9. **Luồng “Mức hoa hồng” từ Quản lí và luồng cùng tên gửi cho CTV có vai trò gì?**
   Luồng Quản lí → 4.3.2 cung cấp mức hoa hồng dùng khi tính; luồng 4.3.3 → CTV thông báo mức hoa hồng sau xử lý. Các sơ đồ hiện giữ tên “Mức hoa hồng”; cần phân biệt vai trò hai luồng khi đặc tả chi tiết công thức tính.

##### **c. Danh sách câu hỏi và trả lời liên quan đến các kho dữ liệu (Data Store)**

1. **Chức năng sử dụng những kho dữ liệu nào?**
   D19 Hồ sơ nhân viên & CTV; D20 Lịch làm việc; D21 Chấm công; D22 Bảng lương & hoa hồng. Các mã này tiếp nối danh mục kho dữ liệu chung D1–D18 của hệ thống.
2. **D19 nhận và cung cấp những dữ liệu gì?**
   4.1.2 ghi “Thông tin nhân viên & CTV” vào D19. D19 cung cấp “Danh sách nhân viên” cho 4.2.3 và “Mức lương, Tỉ lệ hoa hồng” cho 4.3.2.
3. **D20 lưu dữ liệu gì và được cập nhật bởi tiến trình nào?**
   D20 lưu lịch làm việc do 4.2.3 ghi sau xử lý xếp lịch, duyệt ca và nghỉ. Các sơ đồ hiện chưa thể hiện luồng đọc từ D20.
4. **D21 được ghi và đọc bởi những tiến trình nào?**
   4.2.4 ghi “Dữ liệu chấm công” vào D21. 4.3.1 đọc “Giờ công” để tính lương; 4.4.1 đọc “Dữ liệu chấm công” để tổng hợp dữ liệu nhân sự.
5. **D22 được ghi và đọc bởi những tiến trình nào?**
   4.3.3 ghi “Bảng lương, Hoa hồng” vào D22; 4.4.1 đọc “Dữ liệu lương, Hoa hồng” để tổng hợp và đánh giá nhân sự.
6. **Vì sao lịch làm việc và chấm công được tách thành hai kho?**
   D20 lưu lịch dự kiến, còn D21 lưu công thực tế. Hai loại dữ liệu có mục đích khác nhau; việc tách kho giúp phân biệt rõ luồng xếp lịch với luồng ghi nhận chấm công.
7. **Kho dữ liệu trong DFD có phải là một cơ sở dữ liệu riêng không?**
   Không bắt buộc. Kho dữ liệu là nơi lưu trữ logic trong DFD. Khi triển khai, D19 có thể ánh xạ vào các bảng NHAN_VIEN và CONG_TAC_VIEN; D20 vào LICH_LAM_VIEC; D21 vào CHAM_CONG; D22 vào BANG_LUONG và HOA_HONG. Các nhóm bảng có thể cùng nằm trong một cơ sở dữ liệu; sơ đồ DFD không quyết định số cơ sở dữ liệu vật lý.

##### **d. Danh sách câu hỏi và trả lời liên quan đến các thực thể ngoài (External Entity)**

1. **Các thực thể ngoài tương tác với chức năng này là ai?**
   Nhân viên, Cộng tác viên và Quản lí cửa hàng.
2. **Vai trò của Nhân viên trong chức năng này là gì?**
   Nhân viên cung cấp thông tin cá nhân, đăng kí ca, yêu cầu nghỉ và dữ liệu chấm công; nhận lịch làm việc, thông báo duyệt nghỉ, phiếu lương và kết quả đánh giá.
3. **Vai trò của CTV trong chức năng này là gì?**
   CTV cung cấp thông tin cá nhân và báo cáo doanh số; nhận mức hoa hồng. CTV được quản lý qua mã định danh, không có tài khoản đăng nhập hệ thống theo đặc tả nghiệp vụ.
4. **Vai trò của Quản lí cửa hàng trong chức năng này là gì?**
   Quản lí duyệt ca, duyệt nghỉ và cung cấp mức hoa hồng; nhận yêu cầu ca, nghỉ cần duyệt và báo cáo nhân sự.


#### Mô hình mức ngữ cảnh (Context Level)

![DFD mức ngữ cảnh — Nhân viên và CTV](./images/nhansu/DFD_muc0.png)

Ảnh mức ngữ cảnh được thay bằng ảnh cập nhật do người dùng cung cấp.



#### Mô hình mức đỉnh (Level 1)

![DFD mức 1 — Nhân viên và CTV, D19–D22](./images/nhansu/DFD_muc1.png)

Ảnh mức 1 được cập nhật theo bố cục do người dùng cung cấp, làm cơ sở phân tích phân rã mức 2.

Mỗi thực thể ngoài và mỗi kho dữ liệu chỉ xuất hiện một lần trong từng sơ đồ DFD. D20 chỉ lưu lịch; D21 lưu chấm công. [Ảnh phác thảo gốc](./diagram_sketch/2_Level_1%20%281%29.png) dùng D1–D3 cục bộ và chưa tách hai kho này.



#### Mô hình mức dưới đỉnh (Level 2)

**4.1 — Quản lý hồ sơ nhân viên & CTV**

![DFD mức 2 — 4.1 Quản lý hồ sơ nhân viên & CTV](./images/nhansu/DFD_muc2_4_1_QuanLyHoSo.png)

**4.2 — Phân ca & Chấm công**

![DFD mức 2 — 4.2 Phân ca & Chấm công](./images/nhansu/DFD_muc2_4_2_PhanCaChamCong.png)

**4.3 — Tính lương & Hoa hồng**

![DFD mức 2 — 4.3 Tính lương & Hoa hồng](./images/nhansu/DFD_muc2_4_3_TinhLuongHoaHong.png)

[Ảnh 4.3 được cung cấp trước đó](./images/nhansu/DFD_muc2_4_3_TinhLuongHoaHong_ban1.png)

**4.4 — Đánh giá & Báo cáo nhân sự**

![DFD mức 2 — 4.4 Đánh giá & Báo cáo nhân sự](./images/nhansu/DFD_muc2_4_4_DanhGiaBaoCao.png)


### Chức năng: Quản lý nội dung Fanpage

#### Bảng danh sách câu hỏi và trả lời

##### **a. Danh sách câu hỏi và trả lời liên quan đến các ô xử lý (Process)**

1. **Nhiệm vụ của tiến trình theo dõi và đo lường hiệu suất trong mô hình là gì?**
   Hệ thống tự động thu thập các chỉ số tương tác thực tế (lượt tiếp cận, thích, bình luận, chia sẻ) từ nền tảng Fanpage, ghi nhận vào kho dữ liệu hiệu suất để tổng hợp báo cáo gửi về cho nhân viên marketing và quản lý cửa hàng.
2. **Mức 1 được phân rã thành những tiến trình nào?**
   Có 4 tiến trình: 1.1 Lập kế hoạch nội dung; 1.2 Soạn thảo và kiểm duyệt nội dung; 1.3 Đăng tải và phân phối nội dung; 1.4 Theo dõi tương tác và đo lường hiệu suất.
3. **Tiến trình 1.1 được phân rã thành những tiến trình nào?**
   1.1.1 Xác định mục tiêu, chủ đề và đối tượng; 1.1.2 Xây dựng lịch và phân bổ nội dung; 1.1.3 Hoàn thiện và lưu kế hoạch.
4. **Tiến trình 1.2 được phân rã thành những tiến trình nào?**
   1.2.1 Tiếp nhận kế hoạch, ý tưởng và tài nguyên; 1.2.2 Soạn nội dung, thiết kế ấn phẩm; 1.2.3 Kiểm tra nội dung và gửi duyệt; 1.2.4 Tiếp nhận kết quả, cập nhật trạng thái.
5. **Tiến trình 1.3 được phân rã thành những tiến trình nào?**
   1.3.1 Kiểm tra bài đã duyệt và lịch đăng; 1.3.2 Đăng bài lên nền tảng Fanpage; 1.3.3 Ghi nhận kết quả và cập nhật trạng thái.
6. **Tiến trình 1.4 được phân rã thành những tiến trình nào?**
   1.4.1 Thu thập số liệu bài đăng; 1.4.2 Tổng hợp và đánh giá hiệu suất; 1.4.3 Lưu chỉ số và lập báo cáo.
7. **Nếu quản lý yêu cầu chỉnh sửa bài viết thì tiến trình nào tiếp nhận kết quả?**
   1.2.4 tiếp nhận trạng thái và nhận xét của quản lý, cập nhật trạng thái bài viết và trả kết quả duyệt, yêu cầu chỉnh sửa cho Nhân viên Marketing.

##### **b. Danh sách câu hỏi và trả lời liên quan đến các dòng dữ liệu (Data Flow)**

1. **Luồng dữ liệu chính đi từ Nhân viên Marketing vào hệ thống trong quy trình này là gì?**
   Kế hoạch nội dung định kỳ, ý tưởng, văn bản, hình ảnh/banner thiết kế, yêu cầu lên lịch đăng bài và các yêu cầu gỡ bài hoặc cập nhật phát sinh.
2. **Quản lý cửa hàng gửi và nhận những dữ liệu gì?**
   Quản lý nhận bài viết cần duyệt và báo cáo hiệu quả; gửi kết quả phê duyệt, trạng thái bài viết, nhận xét và yêu cầu chỉnh sửa.
3. **Nền tảng Fanpage gửi và nhận những dữ liệu gì?**
   Nền tảng nhận bài viết chính thức; gửi mã bài đăng, trạng thái đăng và số liệu tương tác gồm lượt tiếp cận, thích, bình luận, chia sẻ.
4. **Luồng 1.2.2 → 1.2.3 mang dữ liệu gì?**
   Bản nháp nội dung và ấn phẩm được chuyển sang bước kiểm tra nội dung và gửi duyệt.
5. **Luồng 1.3.1 → 1.3.2 mang dữ liệu gì?**
   Bài đã duyệt sau bước kiểm tra bài viết và lịch đăng, để tiến hành đăng lên nền tảng Fanpage.
6. **Luồng 1.4.2 → 1.4.3 mang dữ liệu gì?**
   Chỉ số tương tác đã tổng hợp và kết quả so sánh mục tiêu, phục vụ lưu chỉ số và lập báo cáo.

##### **c. Danh sách câu hỏi và trả lời liên quan đến các kho dữ liệu (Data Store)**

1. **Kho lưu trữ dữ liệu chính nào được sử dụng trong quá trình quản lý nội dung Fanpage?**
   Các kho dữ liệu chính gồm: Kho kế hoạch nội dung Fanpage (D16), Kho bài viết & tài nguyên truyền thông (D17), và Kho chỉ số tương tác & hiệu suất nội dung (D18).
2. **D16 cung cấp dữ liệu cho tiến trình nào?**
   1.1.3 ghi kế hoạch vào D16; 1.2.1 đọc kế hoạch nội dung từ D16 để tiếp nhận và chuẩn bị soạn thảo.
3. **D17 được đọc và cập nhật ở những bước nào?**
   1.2.4 ghi bài viết và trạng thái vào D17; 1.3.1 đọc bài viết đã duyệt và yêu cầu gỡ bài từ D17; 1.3.3 cập nhật trạng thái đăng vào D17.
4. **D18 được đọc và cập nhật ở những bước nào?**
   1.4.3 ghi dữ liệu thống kê tổng hợp vào D18; 1.4.2 đọc dữ liệu tương tác đã lưu để tổng hợp và đánh giá hiệu suất.
5. **D17 và D18 khác nhau thế nào?**
   D17 lưu bài viết, tài nguyên truyền thông và trạng thái bài viết; D18 lưu số liệu tương tác và hiệu suất để phục vụ đánh giá, báo cáo.

##### **d. Danh sách câu hỏi và trả lời liên quan đến các thực thể ngoài (External Entity)**

1. **Xác định các tác nhân ngoài tương tác trực tiếp với chức năng "Quản lý nội dung Fanpage"?**
   Các tác nhân ngoài bao gồm: Nhân viên Marketing (lên kế hoạch, soạn thảo và gửi yêu cầu đăng bài), Quản lý cửa hàng (kiểm duyệt, phê duyệt hoặc yêu cầu chỉnh sửa nội dung), và Nền tảng Fanpage (môi trường mạng xã hội nhận bài viết hiển thị và trả về dữ liệu tương tác).
2. **Nhân viên Marketing nhận những kết quả gì từ hệ thống?**
   Kết quả duyệt, yêu cầu chỉnh sửa hoặc gỡ bài, cùng báo cáo hiệu quả nội dung.
3. **Những tác nhân nào nhận báo cáo hiệu quả nội dung?**
   Quản lý cửa hàng và Nhân viên Marketing nhận báo cáo do tiến trình 1.4.3 lập.

#### Mô hình mức ngữ cảnh (Context Level)

![DFD Mức ngữ cảnh - Quản lí nội dung Fanpage](./images/quanlyfanpage/DFD_muc0.png)

#### Mô hình mức đỉnh (Level 1)

![DFD Mức 1 - Quản lí nội dung Fanpage](./images/quanlyfanpage/DFD_muc1.png)

#### Mô hình mức dưới đỉnh (Level 2)

![DFD Mức 2 - 1.1 Lập kế hoạch nội dung](./images/quanlyfanpage/DFD_muc2_1_LapKeHoach.png)

![DFD Mức 2 - 1.2 Soạn thảo và kiểm duyệt nội dung](./images/quanlyfanpage/DFD_muc2_2_SoanThaoKiemDuyet.png)

![DFD Mức 2 - 1.3 Đăng tải và phân phối nội dung](./images/quanlyfanpage/DFD_muc2_3_DangTaiPhanPhoi.png)

![DFD Mức 2 - 1.4 Theo dõi tương tác và đo lường hiệu suất](./images/quanlyfanpage/DFD_muc2_4_TheoDoiTuongTac.png)
---

## 4. Phân tích những hạn chế đang tồn tại trong hệ thống và đề xuất các giải pháp cải tiến

### 4.1. Hạn chế trong quản lý cộng tác viên

Quản lý cộng tác viên (CTV) vẫn nằm ngoài phạm vi triển khai hiện tại của hệ thống (out of scope). Mặc dù các phần đặc tả nghiệp vụ và DFD đã đề cập đến hồ sơ CTV, cấp hàng, đối soát và tính hoa hồng, các nội dung này mới mô tả nhu cầu nghiệp vụ và hướng mở rộng, chưa đồng nghĩa với việc hệ thống đã hỗ trợ đầy đủ quy trình quản lý CTV.

CTV không có tài khoản đăng nhập mà được quản lý thông qua mã định danh. Thông tin hàng đã bán, hàng còn tồn và số tiền nộp về phụ thuộc vào báo cáo của CTV và việc cập nhật của quản lý. Cách làm này có các hạn chế:

- **Dữ liệu cập nhật chậm:** Cửa hàng khó nắm bắt kịp thời lượng hàng thực tế tại từng CTV khi chưa nhận được báo cáo.
- **Đối soát phụ thuộc vào thao tác thủ công:** Việc tổng hợp hàng đã cấp, hàng đã bán, hàng hoàn trả và tiền đã nộp dễ xảy ra sai sót hoặc bỏ sót chứng từ.
- **Khó kiểm soát công nợ và thất thoát:** Báo cáo chậm hoặc thiếu thông tin khiến việc xác định khoản còn phải nộp, hàng hư hỏng và trách nhiệm xử lý chênh lệch gặp khó khăn.
- **Thiếu quy trình xử lý ngoại lệ:** Việc nhắc báo cáo quá hạn, xử lý nộp thiếu tiền và giải quyết chênh lệch chưa được đặc tả đầy đủ; thông tin tính hoa hồng cũng cần được đối chiếu thống nhất với kết quả bán hàng và thanh toán.

### 4.2. Đề xuất giải pháp cải tiến

Trong phạm vi hiện tại, cửa hàng có thể chuẩn hóa biểu mẫu báo cáo và quy trình đối soát bên ngoài hệ thống. Mỗi báo cáo cần ghi mã CTV, kỳ đối soát, số lượng hàng nhận, hàng bán, hàng hoàn trả, hàng còn tồn, hàng hư hỏng và chứng từ nộp tiền. Quản lý quy định thời hạn gửi báo cáo, người kiểm tra và cách xử lý chênh lệch để giảm sai sót khi tổng hợp.

Ở giai đoạn mở rộng, đề xuất bổ sung chức năng quản lý CTV với các nội dung:

1. **Quản lý hồ sơ và hàng ký gửi theo mã CTV:** Liên kết hồ sơ CTV với phiếu cấp hàng, phiếu nhập hoàn và số lượng tồn tại từng CTV để theo dõi xuyên suốt quá trình giao nhận.
2. **Chuẩn hóa đối soát hàng và tiền:** Tổng hợp dữ liệu theo kỳ, đối chiếu hàng đã cấp với hàng bán, hàng hoàn và hàng còn tồn; xác định số tiền phải nộp sau khi trừ hoa hồng theo chính sách đã thống nhất, so sánh với số tiền thực nộp và ghi nhận chênh lệch.
3. **Bổ sung nhắc hạn và xử lý ngoại lệ:** Theo dõi báo cáo quá hạn, tiền chưa nộp, hàng hư hỏng hoặc thiếu hụt; ghi nhận người xác nhận, hướng xử lý và trạng thái giải quyết.
4. **Lập báo cáo và lưu lịch sử thay đổi:** Cung cấp báo cáo doanh số, hoa hồng, công nợ và hàng tồn theo CTV; lưu lịch sử cập nhật để phục vụ kiểm tra và giải quyết sai lệch.


### 4.3. Hạn chế trong quy trình tổ chức giải đấu và quản lý tài trợ

Cửa hàng sử dụng Challonge để tạo và điều hành các giải đấu, trong đó Yu-Gi-Oh! là bộ môn được tổ chức thường xuyên nhất. Giải đấu áp dụng vòng Swiss, sau đó cắt top theo bảng xếp hạng và điều lệ giải để tổ chức vòng loại trực tiếp. Việc chia cặp và cập nhật kết quả được thực hiện trên Challonge; hệ thống cửa hàng quản lý thông tin sự kiện, đăng ký, lệ phí, tài trợ và trao thưởng.

Phần đặc tả trước đây chưa làm rõ cách phối hợp giữa hai hệ thống và các quy tắc vận hành, dẫn đến những hạn chế cần giải quyết:

- **Chưa quy định đầy đủ cấu hình giải:** Chưa xác định cách chốt số vòng Swiss, số người vào top, cách tính điểm và tiêu chí phân hạng khi bằng điểm. Swiss là thể thức thi đấu; số người được cắt top phải được xác định theo điều lệ áp dụng cho từng giải.
- **Dễ lệch thông tin người tham gia:** Danh sách đăng ký, thanh toán và điểm danh tại cửa hàng cần được đối chiếu với danh sách thi đấu trên Challonge, đặc biệt khi có người bỏ cuộc hoặc đăng ký muộn.
- **Chưa làm rõ trách nhiệm xác nhận kết quả:** Cần phân biệt người báo kết quả, trọng tài xác nhận và người cập nhật trên Challonge; kết quả nhập sai có thể ảnh hưởng đến cặp đấu vòng sau và danh sách cắt top.
- **Chưa có bước chốt bảng xếp hạng trước khi cắt top:** Cần quy định thời hạn tiếp nhận khiếu nại và thẩm quyền sửa kết quả trước khi chuyển sang vòng loại trực tiếp.
- **Chưa theo dõi đầy đủ tài trợ và trao thưởng:** Cần phân biệt khoản tài trợ đã cam kết với tiền hoặc hiện vật thực nhận, đồng thời đối chiếu phần thưởng đã công bố với số lượng thực tế có thể bàn giao.

### 4.4. Đề xuất cải tiến quy trình tổ chức giải đấu và quản lý tài trợ

#### 4.4.1. Chuẩn hóa điều lệ và khởi tạo giải đấu

Quản lý giải đấu lập thông tin sự kiện trên hệ thống cửa hàng, gồm tên giải, bộ môn, thời gian, địa điểm, số người tối đa, hạn đăng ký, lệ phí và cơ cấu giải thưởng. Với Yu-Gi-Oh!, điều lệ phải ghi rõ định dạng thi đấu và bộ quy định áp dụng, gồm quy định về bộ bài, danh sách bài cấm/giới hạn, thời gian trận đấu và cách xử lý khi hết giờ.

Ban tổ chức tạo giải Swiss trên Challonge, lưu mã hoặc đường dẫn giải vào hồ sơ sự kiện và kiểm tra cấu hình trước khi bắt đầu. Số vòng Swiss, điểm thắng/hòa/thua, cách xử lý lượt miễn đấu (bye), thứ tự tiêu chí phân hạng khi bằng điểm và số người vào top phải phù hợp với điều lệ đã công bố. Không mặc định cơ chế xếp hạng sẵn có của Challonge đáp ứng toàn bộ quy định Yu-Gi-Oh!; ban tổ chức phải đối chiếu và xác nhận cách tính được sử dụng.

Số vòng và mức cắt top được xác định theo số người tham gia cùng quy định áp dụng cho loại giải. Điều lệ cần công bố rõ cách xử lý đăng ký muộn và ảnh hưởng đến số vòng hoặc mức cắt top; mọi thay đổi chỉ được thực hiện nếu quy định áp dụng cho phép. Với giải chính thức, sử dụng hướng dẫn của đơn vị tổ chức có thẩm quyền cho đúng khu vực và loại sự kiện.

#### 4.4.2. Đăng ký, thu lệ phí và điểm danh

Nhân viên tiếp nhận thông tin đăng ký, kiểm tra trùng người tham gia và ghi nhận trạng thái lệ phí. Trước giờ khai mạc, nhân viên điểm danh và đối chiếu danh sách đủ điều kiện thi đấu với danh sách trên Challonge bằng mã người tham gia, tránh chỉ đối chiếu theo tên hiển thị.

Khi đóng đăng ký, ban tổ chức chốt danh sách và cấu hình giải theo điều lệ. Trường hợp đến muộn, không tham dự, xin rút hoặc yêu cầu hoàn lệ phí được ghi nhận và xử lý theo chính sách đã công bố; không tự đưa người chưa đủ điều kiện vào danh sách thi đấu.

#### 4.4.3. Điều hành các vòng Swiss

Ban tổ chức sử dụng Challonge để tạo cặp đấu từng vòng và công bố cặp đấu, số bàn cùng thời gian bắt đầu. Người chơi báo kết quả; trọng tài xác nhận kết quả hoặc quyết định xử lý tranh chấp trước khi người được phân công cập nhật trên Challonge.

Trước khi tạo vòng tiếp theo, ban tổ chức kiểm tra các trận đã hoàn tất, kết quả còn thiếu và trường hợp rút khỏi giải. Việc sửa kết quả phải được trọng tài hoặc quản lý giải đấu xác nhận, ghi rõ lý do và kiểm tra ảnh hưởng đến bảng xếp hạng, cặp đấu đã công bố. Trường hợp bỏ cuộc, vắng mặt, được miễn đấu hoặc vi phạm được xử lý theo điều lệ và quyết định của trọng tài.

#### 4.4.4. Chốt bảng xếp hạng và cắt top

Sau vòng Swiss cuối cùng, ban tổ chức kiểm tra kết quả, điểm số và các tiêu chí phân hạng đã công bố. Bảng xếp hạng tạm thời được công bố để tiếp nhận khiếu nại trong thời hạn quy định; trọng tài giải quyết các trường hợp còn tranh chấp trước khi quản lý giải đấu xác nhận danh sách chính thức.

Ban tổ chức chọn số người đứng đầu theo mức cắt top đã công bố, chẳng hạn Top 4 hoặc Top 8 nếu phù hợp với điều lệ. Không tự chọn người vào top khi bằng điểm; phải áp dụng đúng thứ tự tiêu chí phân hạng. Trường hợp người đủ điều kiện không tiếp tục thi đấu, xử lý theo điều lệ và quyết định của trọng tài trước khi chốt nhánh đấu.

Những người vào top được xếp hạt giống theo quy định đã công bố và thi đấu loại trực tiếp trên Challonge. Ban tổ chức có thể cấu hình giải hai giai đoạn hoặc tạo nhánh loại trực tiếp riêng được liên kết với giải Swiss. Kết quả vòng Swiss và kết quả vòng top được lưu riêng để phân biệt thứ hạng sau Swiss với thành tích chung cuộc. Hệ thống cửa hàng tiếp nhận kết quả do nhân viên cập nhật và xác nhận; đồng bộ tự động với Challonge là hướng mở rộng nếu được triển khai sau này.

#### 4.4.5. Tiếp nhận tài trợ và bàn giao phần thưởng

Nhân viên ghi nhận từng gói tài trợ với nhà tài trợ, nội dung cam kết, giá trị hoặc số lượng hiện vật, thời hạn bàn giao và quyền lợi truyền thông. Khi nhận tài trợ, nhân viên đối chiếu với cam kết, lưu chứng từ và cập nhật số thực nhận; hiện vật phải được kiểm nhận trước khi ghi nhận vào kho.

Trước giải, quản lý kiểm tra khả năng đáp ứng cơ cấu giải thưởng từ tài trợ thực nhận và nguồn hàng của cửa hàng. Nếu nhà tài trợ giao thiếu, giao chậm hoặc hiện vật không đạt yêu cầu, nhân viên ghi nhận chênh lệch và chuyển quản lý xử lý phương án bổ sung, thay thế hoặc thông báo điều chỉnh theo điều lệ.

Sau khi xác nhận kết quả chung cuộc, nhân viên lập danh sách người nhận thưởng, tạo phiếu xuất kho cho hiện vật và ghi nhận chi trả đối với giải thưởng bằng tiền. Mỗi lần bàn giao cần có xác nhận người nhận; phần thưởng chưa nhận được theo dõi riêng, tránh ghi nhận đã bàn giao khi mới lập danh sách trao thưởng.

#### 4.4.6. Tổng kết và lưu hồ sơ sự kiện

Khi kết thúc sự kiện, quản lý đối chiếu số người đăng ký và thực tế tham gia, lệ phí đã thu và hoàn, tài trợ đã nhận, chi phí tổ chức, phần thưởng đã giao và số còn lại. Hồ sơ lưu kèm đường dẫn Challonge, kết quả Swiss, danh sách cắt top, kết quả chung cuộc, quyết định xử lý khiếu nại và chứng từ liên quan.

Báo cáo tổng kết phục vụ đánh giá hiệu quả sự kiện, thực hiện quyền lợi đã cam kết với nhà tài trợ và cải tiến các giải tiếp theo. Các bước bổ sung cần được đối chiếu và cập nhật vào DFD tương ứng khi chốt đặc tả chi tiết.

Nguồn tham khảo cho đề xuất:

- [Challonge — Các thể thức thi đấu, Swiss và giải hai giai đoạn](https://kb.challonge.com/en/article/learn-about-challonge-competition-formats-1f8j1cf/).
- [Konami — Cập nhật chính sách giải đấu Yu-Gi-Oh! TCG phiên bản 2.5](https://www.yugioh-card.com/eu/tournament-policy-ver-2-5-updates-and-changes/). Tài liệu này dùng để tham khảo; điều lệ thực tế cần chọn đúng bộ quy định cho khu vực và loại giải của cửa hàng.
