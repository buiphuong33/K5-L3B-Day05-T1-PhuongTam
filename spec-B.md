# Phần B: §3 Khi AI sai · §5 Prototype (Phương)

> File này ghép vào `spec.md`: §3 đặt sau §2, §5 đặt sau §4 của phần A.
> Dùng chung với phần A: 2 kịch bản đắt nhất (#1 bé 18 tháng sốt lừ đừ, #2 bầu 3 tháng bị cảm) và mức tự chủ của 5 tool.
> Số ①–⑨ là số chú thích trên prototype (`prototype/index.html` và ảnh `prototype/anh-*.png`).

---

## §3. Khi AI sai (chặng 3)

### Kịch bản #1: "Con mình 18 tháng sốt 39 độ từ chiều, giờ lừ đừ gọi mãi mới mở mắt, có thuốc hạ sốt nào cho bé không?"

Đường đi: **failure / ca nguy hiểm**. Tin nhắn có dạng *mua thuốc* nhưng chứa *dấu hiệu cấp cứu ở trẻ dưới 2 tuổi*.

**AI nói (nguyên văn, đúng như trên prototype):**
> **Cần đi khám ngay.** Bé 18 tháng tuổi có dấu hiệu nguy hiểm (lừ đừ, gọi mãi mới mở mắt). Bạn hãy đưa bé đến cơ sở y tế gần nhất hoặc **gọi 115 ngay bây giờ**, đừng chờ mua thuốc ở nhà.
> Mình đã chuyển cuộc chat cho **dược sĩ trực, ưu tiên khẩn**; dược sĩ sẽ nhắn bạn ngay khi nhận ca. Mình là trợ lý AI nên **không gợi ý thuốc hay liều** cho trường hợp này.

Câu này không hứa điều AI không làm được. AI không nói "dược sĩ sẽ gọi bạn trong 1 phút", vì không tool nào bảo đảm được việc đó. AI không nêu tên thuốc, không nói liều.

**Khách thấy gì (ngoài câu chữ):**
- ③ **Banner đỏ ghim** ở đầu khung chat: "⚠ Cần đi khám ngay", có nút **Gọi 115**, **Cơ sở y tế gần nhất**, **Thu gọn**. Banner hiện **cùng lúc** với câu trả lời, không chờ dược sĩ (`khuyen_di_kham` · tự làm).
- ② Chip **"Dấu hiệu nguy hiểm · độ chắc: cao"** và dòng **"Mình dựa vào: «lừ đừ», «gọi mãi mới mở mắt», «con mình 18 tháng»"**. Đây là chữ của chính khách, để khách tự kiểm AI có đọc đúng không.
- ④ Thẻ **"Đã chuyển dược sĩ trực · ƯU TIÊN KHẨN · vị trí 1"**, có dòng **"Vì sao mình chuyển"**, bộ đếm thời gian chờ, nút **Huỷ chuyển** và **Xem tóm tắt gửi dược sĩ**.
- ⑥ Ô viền đứt **"Không có gợi ý thuốc ở đây"**. Không có thẻ sản phẩm, không có nút đặt.
- ⑤ Hộp **"Lưu thông tin sức khoẻ vào hồ sơ?"**. Chưa bấm thì không lưu.

**Khách làm gì tiếp:**
- Bấm **Gọi 115** hoặc **Cơ sở y tế gần nhất**. Đây là bước chính.
- Nếu **không làm gì**: banner vẫn ghim; "Thu gọn" chỉ thu về một dải đỏ có nút Gọi 115 (G8: gạt được nhưng không mất hẳn). Ca vẫn ở đầu hàng chờ dược sĩ.
- Nếu khách **gắt hoặc đòi tên thuốc** ("Mình chỉ cần tên thuốc hạ sốt thôi, nói nhanh đi"), AI giữ nguyên hướng: *"Mình hiểu bạn đang rất lo. Nhưng với dấu hiệu bé đang có, thuốc hạ sốt ở nhà không thay được việc khám ngay, nên mình không gợi ý thuốc lúc này. Dược sĩ trực đang được ưu tiên nhận ca của bạn. Nút Gọi 115 luôn ở trên cùng màn hình."*
- Nếu AI **đọc nhầm** (bé không lừ đừ), khách bấm **Huỷ chuyển**. Banner đi khám vẫn giữ, vì để sót ca thật đắt hơn nhiều so với cảnh báo thừa.

**Ai được báo, sau bao lâu:**
- **Dược sĩ trực**, ngay lúc AI trả lời (giây thứ 0). Ca **nhảy lên đầu hàng chờ** với nhãn KHẨN, vượt các ca thường đã chờ 4–7 phút (Màn 2, ⑨).
- Dược sĩ thấy: tóm tắt AI soạn (trẻ 18 tháng · sốt 39 độ, lừ đừ · từ chiều · dấu hiệu nguy hiểm tô đỏ). Những ô khách chưa nói ghi rõ **"chưa rõ, khách chưa nói"** (đã dùng thuốc gì, cân nặng, dị ứng). Kèm tin gốc, danh sách AI đã làm và không làm, và một tin nhắn AI soạn sẵn mà **dược sĩ sửa rồi mới gửi**.
- **Hạn của nhóm:** ca khẩn có người nhận trong **≤ 2 phút**. Quá 2 phút thì báo dược sĩ trưởng ca. *Prototype chỉ hiện bộ đếm, chưa dựng bước báo trưởng ca.* Khách không bị thiệt trong lúc chờ, vì banner 115 đã hiện từ giây 0.

**Quyết định: chọn khuyên đi khám ngay và chuyển dược sĩ song song.**

| Phương án | Kết quả | Vì sao |
|---|---|---|
| Hỏi lại thêm (bé bao nhiêu kg, đã uống gì chưa) | Loại | Mỗi câu hỏi là thêm một lượt chờ trong khi bé có dấu hiệu cấp cứu. Thông tin đã đủ để hành động; câu trả lời thêm không đổi được kết luận "đi khám" |
| Trả lời kèm giới hạn (gợi ý thuốc hạ sốt cho trẻ, dặn "nếu không đỡ thì đi khám") | Loại | `goi_y_san_pham` **không đảo lại được** khi thuốc đã dùng. Câu "nếu không đỡ thì…" còn khiến khách yên tâm ở nhà chờ, làm chậm việc đi viện, đúng loại sai đắt nhất |
| Chỉ chuyển dược sĩ | Loại | Ca nguy hiểm nằm trong hàng chờ, trái với kết quả lát cắt yêu cầu ("ca nguy hiểm không nằm trong hàng chờ") |
| **Khuyên đi khám ngay (banner) + chuyển dược sĩ khẩn** | **Chọn** | Nếu cảnh báo thừa, khách mất một chuyến đi khám và dược sĩ mất vài phút. Nếu để sót, có thể mất sức khoẻ của bé và không đảo lại được. Hai việc chạy song song nên khách không phải chờ ai |

**Loại lỗi: lỗi hệ thống.** AI đọc phần "có thuốc hạ sốt nào" mà bỏ qua "lừ đừ, gọi mãi mới mở mắt", tức là hiểu sai ý định.
- *Cách nói:* không cần xin lỗi khách, vì thiết kế phải chặn lỗi trước khi khách thấy.
- *Cách sửa:* sửa thứ tự quyết định. Kiểm dấu hiệu nguy hiểm **chạy trước** mọi tool khác. Có dấu hiệu nguy hiểm thì `goi_y_san_pham` không được gọi, dù tin nhắn hỏi mua thuốc.

---

### Kịch bản #2: "Mình đang bầu 3 tháng, bị cảm sổ mũi 2 hôm, có thuốc nào không ảnh hưởng em bé không ạ?"

Đường đi: **low-confidence / ngoài phạm vi AI được tự quyết.** Câu hỏi trông vô hại, và một câu trả lời "trông đúng" mới là chỗ nguy hiểm.

**AI nói (nguyên văn):**
> Cảm ơn bạn đã nói rõ là **bầu 3 tháng**, thông tin này rất quan trọng. Với người mang thai hoặc cho con bú, trợ lý AI **không tự gợi ý thuốc**, vì nhiều thuốc cảm thông dụng không phù hợp với thai kỳ. Mình đã chuyển bạn sang **dược sĩ trực** để được tư vấn riêng.
> Trong lúc chờ, bạn có thể: rửa mũi bằng nước muối sinh lý, uống đủ nước, nghỉ ngơi.
> Nếu bạn **sốt cao, khó thở, đau bụng hoặc ra máu**, hãy đi khám ngay.

**Khách thấy gì:**
- ② Chip vàng **"Cần dược sĩ tư vấn · độ chắc: cao"** và dòng "Mình dựa vào: «bầu 3 tháng»".
- ④ Thẻ **"Đã chuyển dược sĩ trực · Ưu tiên thường"**, dòng "Vì sao mình chuyển: người dùng thuốc đang mang thai / cho con bú, thuộc nhóm trợ lý không được tự gợi ý thuốc", nút Huỷ chuyển.
- ⑥ Ô "Không có gợi ý thuốc ở đây: trợ lý không hiện thẻ sản phẩm và không có nút đặt".
- ⑤ Hộp đồng ý lưu thông tin sức khoẻ.

**Khách làm gì tiếp:** chờ dược sĩ và làm ngay các việc không dùng thuốc. Nếu khách gắt ("Nói đại một loại đi, mình cần gấp"), AI vẫn không nêu tên thuốc nhưng cho biết **thời gian chờ dự kiến**: *"…chọn sai thì em bé là người chịu và thuốc đã uống thì không rút lại được. Dược sĩ đang ở hàng chờ, dự kiến nhắn bạn trong khoảng 3 phút."* Có dấu hiệu nặng thì quay về đường đi khám.

**Ai được báo, sau bao lâu:** dược sĩ trực, ngay lúc chuyển, ở **mức ưu tiên thường** (không có dấu hiệu cấp cứu). Dược sĩ nhận tóm tắt: người mang thai 3 tháng · cảm, sổ mũi · 2 hôm · không thấy dấu hiệu nguy hiểm · "đã dùng thuốc gì: chưa rõ". **Hạn của nhóm:** ≤ 10 phút. Quá hạn thì AI báo khách thời gian chờ thực tế và mời ghé cửa hàng gần nhất.

**Quyết định: chọn chuyển dược sĩ, kèm hướng dẫn không dùng thuốc trong lúc chờ.**

| Phương án | Kết quả | Vì sao |
|---|---|---|
| Trả lời kèm giới hạn (gợi ý một thuốc cảm "thông dụng" và dặn "hỏi bác sĩ trước khi dùng") | Loại | Câu cảnh báo không chặn được việc mua và uống. Người nhắn tin hỏi lúc tối chính là vì không muốn đi hỏi bác sĩ. Thuốc đã uống thì không đảo lại được, và người chịu là thai nhi, không phải người nhắn |
| Hỏi lại thêm (thai mấy tuần, đang dùng thuốc gì) | Loại | Khách đã nói thông tin quyết định (đang mang thai). Hỏi thêm không đổi được kết luận "phải là dược sĩ", chỉ làm khách chờ lâu hơn. Các câu đó để dược sĩ hỏi |
| Từ chối thẳng ("AI không tư vấn cho bà bầu") | Loại | Đúng về an toàn nhưng bỏ khách lại một mình, không có bước tiếp theo |
| **Chuyển dược sĩ + mẹo không dùng thuốc + dấu hiệu cần đi khám** | **Chọn** | Khách có việc làm được ngay, ca được người có thẩm quyền xử lý, và AI không đứng ra quyết định thuốc cho thai kỳ |

**Loại lỗi: lỗi ngữ cảnh** (theo PAIR: *context error*). Nếu AI gợi ý thuốc cảm thông dụng, hệ thống vẫn đang **chạy đúng thiết kế** của luồng "người lớn bị cảm", nhưng lại sai với người dùng này vì họ đang mang thai.
- *Cách nói:* không đổ cho khách, và cảm ơn khách đã nói rõ ("Cảm ơn bạn đã nói rõ là…"), để khách hiểu vì sao luồng thay đổi.
- *Cách sửa:* phải **sửa thiết kế**, không chỉ sửa câu chữ (xem mục dưới).

---

### Bảng phân loại lỗi trong lát cắt

| Loại lỗi | Ví dụ trong lát cắt | Cách nói | Cách sửa |
|---|---|---|---|
| **Hệ thống** | #1: AI bỏ sót "lừ đừ" vì tin nhắn hỏi mua thuốc | Thiết kế chặn trước khi khách thấy. Nếu đã lỡ hiện thì nói rõ "mình đã đọc sót, bé cần đi khám ngay" | Kiểm dấu hiệu nguy hiểm chạy trước mọi tool |
| **Người dùng** | Khách nhắn "có thuốc hạ sốt không shop", quên nói người dùng thuốc là ai (đúng như lời dược sĩ trong track) | Không trách khách. Hỏi lại **một câu** có nút bấm sẵn ⑦ | G10: thêm câu hỏi "thuốc cho ai dùng?" trước mọi gợi ý |
| **Ngữ cảnh** | #2: gợi ý thuốc cảm đúng với người lớn nhưng sai với người mang thai | Cảm ơn khách đã nói rõ, giải thích vì sao luồng đổi | Đổi luật: nhóm nguy cơ thì tool gợi ý không xuất hiện |

### Lỗi mà sửa câu chữ không cứu được

Ở kịch bản #2, cách sửa dễ nghĩ tới nhất là thêm câu *"Lưu ý: nên hỏi ý kiến bác sĩ trước khi dùng khi mang thai"* vào sau gợi ý. Cách này **không cứu được**, vì nút **"Đặt ngay"** vẫn nằm ngay dưới. Khách đọc lướt, bấm đặt, rồi uống.

**Thiết kế cứu nó thế nào:** khi người dùng thuốc thuộc **nhóm nguy cơ** (trẻ em, mang thai hoặc cho con bú, người cao tuổi, có bệnh mạn tính hoặc đang dùng thuốc khác) hoặc có dấu hiệu nguy hiểm, `goi_y_san_pham` **không được gọi**. Giao diện **không có thẻ sản phẩm, không có nút đặt** (⑥). Trên prototype, nút "Xem phương án đã loại" ở ca #2 hiện bản bị loại (gợi ý kèm câu cảnh báo và nút "Đặt ngay") đặt cạnh bản đã chọn để so sánh.

### Nguyên tắc HAX/PAIR: mỗi nguyên tắc trỏ vào một chỗ

| Nguyên tắc | Chỗ cụ thể |
|---|---|
| **G1** · làm rõ hệ thống làm được gì (+ Luật AI 134/2025/QH15 Đ11 k1: báo cho người dùng biết đang làm việc với AI) | ① Thanh xanh đầu khung chat: "Bạn đang chat với **trợ lý AI**… chuyển bạn tới dược sĩ thật… không chẩn đoán, không nói liều, không bán thuốc kê đơn". Tin của dược sĩ thật có nhãn riêng "Dược sĩ … · người thật" |
| **G2 + PAIR Explainability & Trust** · AI chắc tới đâu, dựa vào đâu | ② Chip độ chắc bằng chữ ("Dấu hiệu nguy hiểm · độ chắc: cao", "Gợi ý chung · độ chắc: trung bình") và dòng **"Mình dựa vào: «…»"** trích nguyên chữ của khách |
| **G10** · thu hẹp phạm vi khi nghi ngờ | ⑦ Khi tin nhắn không nói ai dùng thuốc: hỏi **một** câu "thuốc này cho ai dùng?" kèm 5 nút. Khi khách tự hỏi cho mình: ô sàng lọc tích nhanh 5 điều trước khi gợi ý |
| **G11** · giải thích vì sao | ④ Dòng "**Vì sao mình chuyển:** …" trong mọi thẻ chuyển dược sĩ; ⑥ lý do không có gợi ý thuốc |
| **PAIR Errors + Graceful Failure** | ⑨ Mỗi đường lỗi đều có đường lui: ca khẩn lên đầu hàng chờ, ô "chưa rõ" thay vì để AI đoán, dược sĩ sửa tin soạn sẵn trước khi gửi, nút "Tóm tắt sai?" |

---

## §5. Prototype (chặng 5)

- **File:** [`prototype/index.html`](prototype/index.html). Mở bằng trình duyệt, không cần cài đặt.
- **Công cụ:** HTML/CSS/JS một file, dựng cùng coding agent (Claude).
- **Phần mock:** toàn bộ. Quyết định của AI là **bộ luật từ khoá** trong file (hàm `analyze`), mô phỏng model theo thứ tự ưu tiên: dấu hiệu nguy hiểm → thuốc kê đơn → nhóm nguy cơ → đã dùng nhiều ngày không đỡ → hỏi liều → triệu chứng (hỏi lại hoặc sàng lọc) → hỏi hàng. Tên cửa hàng, sản phẩm, giá, dược sĩ đều là dữ liệu dựng.
- **Lời gọi AI thật:** không có.
- **Hai màn:** Màn 1 là khách chat; Màn 2 là dược sĩ nhận ca (bonus của track). Thanh "Chọn ca" có: #1 (ca demo bắt buộc), #2, hai ca thường (đau họng, hỏi nước muối) và **Ca lạ** (gõ tự do, hoặc chọn 6 tin gợi ý: bé 2 tuổi ho, đòi amoxicillin không đơn, uống thuốc 5 ngày không đỡ, bố 70 tuổi đau ngực, hai yêu cầu trong một tin…).
- **Bấm qua ca khó:** chọn ca #1 → bấm tin gợi ý → (thử Thu gọn banner, Huỷ chuyển rồi Chuyển lại, Đồng ý lưu) → bấm "Mình chỉ cần tên thuốc…" → "Xem phía dược sĩ →" → **Nhận ca & gửi tin** → quay lại Màn 1, thấy tin của dược sĩ hiện bên khách.

### Ảnh có đánh số

| Ảnh | Nội dung |
|---|---|
| `prototype/anh-1-c1.png` | Màn 1, ca #1 bé 18 tháng (①②③④⑤⑥) |
| `prototype/anh-2-ph.png` | Màn 2, dược sĩ nhận ca #1 (⑨) |
| `prototype/anh-3-c2.png` | Màn 1, ca #2 bầu 3 tháng, kèm phương án đã loại (②④⑤⑥) |
| `prototype/anh-4-c3.png` | Màn 1, ca thường đau họng: sàng lọc, rồi gợi ý (⑦⑧) |

| Số | Thể hiện gì | Nguyên tắc | Mức tự chủ |
|---|---|---|---|
| ① | Thanh "Bạn đang chat với trợ lý AI" + AI làm được và không làm được gì | G1 | — |
| ② | Chip độ chắc bằng chữ + "Mình dựa vào: «chữ của khách»" | G2, PAIR Explainability | — |
| ③ | Banner đỏ ghim "Cần đi khám ngay", nút Gọi 115, Thu gọn (không tắt hẳn) | G8 (gạt được), PAIR Graceful Failure | `khuyen_di_kham` · **tự làm, hiện ngay** |
| ④ | Thẻ "Đã chuyển dược sĩ" + "Vì sao mình chuyển" + **Huỷ chuyển** + xem tóm tắt gửi đi | G11 | `chuyen_duoc_si` · **tự làm có hoàn tác** |
| ⑤ | Hộp "Lưu thông tin sức khoẻ?" Đồng ý / Không; chưa bấm = không lưu; có Xoá, Đổi ý | G9 (sửa dễ) | `luu_ghi_chu_suc_khoe` · **cần khách duyệt** |
| ⑥ | Ô "Không có gợi ý thuốc ở đây" + lý do; không có nút nào | G11 | `goi_y_san_pham` bị tắt khi không đủ điều kiện · `ban_thuoc_ke_don` **cấm** (không có nút) |
| ⑦ | Hỏi lại một câu "thuốc cho ai dùng?" / ô sàng lọc tích nhanh | G10 | — |
| ⑧ | Thẻ gợi ý kèm căn cứ sàng lọc (✓ từng điều kiện), "Cách dùng: theo nhãn", nút **Hỏi dược sĩ trước**, **Không cần**, **Sửa câu trả lời sàng lọc**, **Huỷ giữ hàng** | G2, G8, G9 | `goi_y_san_pham` · **tự làm có điều kiện** |
| ⑨ | Màn dược sĩ: ca KHẨN trên đầu hàng chờ; tóm tắt có ô "chưa rõ"; AI đã làm / không làm; tin soạn sẵn dược sĩ sửa rồi gửi | PAIR Errors + Graceful Failure | Ai được báo; tách "AI soạn" khỏi "người gửi" |

Bật hoặc tắt số chú thích bằng ô "Hiện số chú thích HAX/PAIR" ở đầu trang. Bảng bên phải tô vàng các tool đã dùng trong ca đang xem.

### Quyết định: cách hiện độ chắc và bằng chứng

| Cách đã nghĩ tới | Kết quả | Vì sao |
|---|---|---|
| Phần trăm ("độ chắc 87%") | Loại | Phụ huynh đang hoảng lúc nửa đêm không biết 87% là đủ hay chưa. Con số còn tạo cảm giác chính xác giả, vì luật không tính ra xác suất thật |
| Không hiện độ chắc, chỉ hiện câu trả lời | Loại | Khách không có cách nào kiểm AI đã đọc đúng hay sai. Đi ngược PAIR "tin đúng mức" |
| **Chữ (cao / trung bình) + trích nguyên chữ khách viết** | **Chọn** | Khách tự kiểm được ngay: nếu AI trích «lừ đừ» mà bé không lừ đừ, khách bấm Huỷ chuyển. Bằng chứng là chữ của khách nên AI không bịa được nguồn |

### Quyết định: cách hiện mức tự chủ

| Cách đã nghĩ tới | Kết quả | Vì sao |
|---|---|---|
| Cảnh báo cấp cứu dạng **popup** | Loại | Khách đóng popup là cảnh báo mất. Banner ghim thu gọn được nhưng không biến mất |
| Gợi ý thuốc nhưng **làm mờ / khoá** nút đặt với nhóm nguy cơ | Loại | Vẫn để lộ tên thuốc, khách mang tên đó ra mua chỗ khác. Bỏ hẳn thẻ sản phẩm (⑥) |
| Hỏi khách **"Bạn có muốn chuyển dược sĩ không?"** trước khi chuyển | Loại | Thêm một bước chờ ở ca khẩn. Chuyển thừa chỉ tốn vài phút, nên tự làm và cho nút Huỷ chuyển |
| Tự lưu thông tin sức khoẻ, có nút Xoá sau | Loại | Xoá được nhưng rủi ro lộ đã xảy ra (bảng tool của track). Rubric riêng của track: không lưu khi khách chưa đồng ý |
| **Tự làm có hoàn tác (③④) · cần duyệt (⑤) · không có nút (⑥)** | **Chọn** | Mỗi mức trông khác nhau trên màn hình, khớp với cái giá khi sai ở §4 |

### Khi có ca lạ

Ô nhập ở Màn 1 nhận tin bất kỳ và đi theo thứ tự ưu tiên ở trên. Ca không khớp luật nào thì AI **không đoán** mà hỏi "Bạn muốn: hỏi giá / hỏi thuốc cho một triệu chứng / nói chuyện với dược sĩ". Tin có hai yêu cầu (ví dụ "còn nước muối không, với con mình sốt thì uống thuốc gì") được trả lời phần nguy hiểm hơn trước (chuyển dược sĩ vì trẻ em), rồi mới trả lời phần hỏi hàng.

**Giới hạn đã biết:** bộ luật chỉ bắt các từ khoá có sẵn. Ví dụ "mệt lả", "tím môi", nếu viết khác đi, có thể bị sót. Sản phẩm thật cần model kèm danh sách dấu hiệu nguy hiểm do dược sĩ duyệt, và một bộ eval riêng cho các cách viết khác nhau. Lỗi này ghi lại cho §6.
