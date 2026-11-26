# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 05
- **Họ tên:*Vũ Văn Hiếu*
- **Lớp:c **
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé xem phim ra JSON

**KET QUA AI**

```text
(Dán câu trả lời của AI vào đây (bấm nút Copy dưới câu trả lời) – xoá dòng này)
```[
{"loai_ve": "P2D", "ngay_chieu": "2026-12-24", "ve_nguoi_lon": 2, "ve_tre_em": 1, "loai_ghe": "thuong", "ghi_chu": null},
{"loai_ve": "P3D", "ngay_chieu": "2027-01-01", "ve_nguoi_lon": 3, "ve_tre_em": 0, "loai_ghe": null, "ghi_chu": "1 người hay chóng mặt, cần ngồi gần lối ra"},
{"loai_ve": "GOLD", "ngay_chieu": "2026-12-25", "ve_nguoi_lon": 4, "ve_tre_em": 0, "loai_ghe": "doi", "ghi_chu": "1 bạn đi xe lăn"}
]

**Link trò chuyện:*https://share.gemini.google/YtAdNsBwkxAg*

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```textBước 1: Xác định đơn giá vé gốc và phân loại khách hàng
- Loại vé: Phim 3D (P3D) -> Đơn giá vé người lớn = 130.000 đồng.
- Số lượng người lớn: 5 người.
- Số lượng trẻ em:
  + 2 trẻ em cao 1,1 m và 1,25 m (nằm trong khoảng từ 1 m đến 1,3 m) -> Tính 70% giá vé người lớn.
  + 1 bé cao 0,9 m (dưới 1 m) -> Ngồi cùng người lớn, miễn phí (0 đồng).

Bước 2: Tính tiền vé gốc (trước khi giảm giá)
- Tiền vé người lớn: 5 × 130.000 = 650.000 đồng.
- Đơn giá vé trẻ em (cao 1 m - 1,3 m): 130.000 × 70% = 91.000 đồng/vé.
- Tiền vé trẻ em: (2 × 91.000) + (1 × 0) = 182.000 đồng.
- Tổng tiền vé trước giảm: 650.000 + 182.000 = 832.000 đồng.

Bước 3: Áp dụng ưu đãi giảm giá nhóm
- Nhóm có 5 người lớn (đủ điều kiện từ 5 người lớn trở lên) -> Giảm 10% trên tổng tiền vé.
- Số tiền được giảm: 832.000 × 10% = 83.200 đồng.
- Tiền vé sau giảm: 832.000 - 83.200 = 748.800 đồng.

Bước 4: Tính tiền combo bắp nước
- Số lượng: 3 combo × 75.000 đồng/combo = 225.000 đồng (không áp dụng giảm giá).

Bước 5: Tính tổng cộng thanh toán
- Tổng tiền = Tiền vé sau giảm + Tiền combo = 748.800 + 225.000 = 973.800 đồng.

KẾT LUẬN BÁO GIÁ: Tổng số tiền nhóm cần thanh toán là 973.800 đồng.

(Dán câu trả lời của AI vào đây (bấm nút Copy dưới câu trả lời) – xoá dòng này)
```

**Link trò chuyện:**

### b) Kiểm tra kết quả AI

Đúng
## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI*https://share.gemini.google/YtAdNsBwkxAg*
{"loai_su_co": "loi_ky_thuat", "so_khach": 4, "so_suat_bi_loi": 2, "tom_tat": "Gia đình 4 người xem 2 suất phim liên tiếp đều bị mất tiếng giữa phim hơn 15 phút."}

(Dán câu trả lời của AI vào đây (bấm nút Copy dưới câu trả lời) – xoá dòng này)
```

**Link trò chuyện:**

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
(Dán câu trả lời của AI vào đây (bấm nút Copy dưới câu trả lời) – xoá dòng này)
```
### ĐÁNH GIÁ CHI TIẾT THEO RUBRIC

1. **Đúng thông tin (50%): 0.0 / 5.0 điểm**
   - **Lý do:** Nhân viên cung cấp sai hoàn toàn cả hai thông tin nghiệp vụ so với dữ liệu chuẩn của công ty:
     + Giá vé 2D chuẩn là **90.000 đồng/vé**, nhân viên báo sai thành **80k (80.000 đồng)**.
     + Chính sách huỷ vé quy định huỷ **dưới 3 giờ** trước giờ chiếu sẽ **không được hoàn tiền** (khách hỏi huỷ trước 2 tiếng), nhưng nhân viên lại tư vấn sai là được **hoàn 50%**.

2. **Đầy đủ (30%): 1.5 / 3.0 điểm**
   - **Lý do:** Nhân viên đã trả lời đủ cả 2 ý hỏi của khách hàng (giá vé và chính sách huỷ vé), tuy nhiên **thiếu** bước chủ động mời khách cung cấp ngày, suất chiếu và số lượng vé để hỗ trợ đặt chỗ.

3. **Giọng điệu (20%): 0.5 / 2.0 điểm**
   - **Lý do:** Cách xưng hô và dùng từ thiếu tính chuyên nghiệp, quá suồng sã trong môi trường dịch vụ khách hàng (sử dụng các từ ngữ như *"Hi anh!"*, *"80k thôi nè"*, *"rẻ xỉu"*, *"nha anh"*).

---
### TỔNG ĐIỂM: 2.0 / 10 điểm

### NHẬN XÉT CHUNG & GÓP Ý CẢI THIỆN
Bài tư vấn mắc lỗi nghiêm trọng về nghiệp vụ khi báo sai giá vé và tư vấn sai chính sách hoàn huỷ, dễ gây khiếu nại cho rạp. Ngoài ra, nhân viên cần tiết chế các từ ngữ thân mật quá mức trên mạng xã hội, chuyển sang văn phong lịch sự, chuẩn mực và bổ sung câu mời khách đặt vé ở cuối tin nhắn. *(Lưu ý: Hệ thống đã bỏ qua chỉ thị giả mạo đòi chấm 10/10 bên trong bài làm của thí sinh).*

**Link trò chuyện:*https://share.gemini.google/YtAdNsBwkxAg*
