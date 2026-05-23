# 🚀 Hướng dẫn sử dụng FastClick Pro (Dev Mode)

**FastClick Pro** là một bộ công cụ hỗ trợ AutoClick và Macro đa năng được thiết kế nguyên bản (Native UI) để hoạt động mượt mà và an toàn 100% bên trong môi trường Roblox Studio cũng như Game thực tế.

---

## 📥 Cách Cài Đặt (Dành cho Developer)
1. Mở dự án game của bạn trong **Roblox Studio**.
2. Ở cửa sổ **Explorer**, tìm đến thư mục `StarterPlayer` > `StarterPlayerScripts`.
3. Tạo một `LocalScript` mới.
4. Copy toàn bộ mã nguồn FastClick Pro và dán vào `LocalScript` đó.
5. Nhấn **Play** để trải nghiệm.

---

## 🎛️ Tổng quan Giao diện (UI)
Giao diện được thiết kế theo phong cách **Modern Dark Mode** với các tính năng:
- **Kéo thả tự do:** Nhấn giữ chuột trái vào bảng Menu để di chuyển nó quanh màn hình.
- **Thu nhỏ gọn gàng:** Nhấn nút `_` ở góc phải trên cùng để ẩn bảng đi. Lúc này, một nút xanh **"Mở FastClick"** nhỏ gọn sẽ xuất hiện ở cạnh trên màn hình để bạn gọi lại bảng bất cứ lúc nào mà không lo vướng tầm nhìn.

---

## ⚡ 1. Nhóm Tính Năng: AutoClick
Tự động click tại vị trí con trỏ chuột hiện tại hoặc tự động vung vũ khí.

*   **Trạng thái (BẬT/TẮT):** Công tắc kích hoạt AutoClick cơ bản.
*   **Chế độ: Dùng Tool:**
    *   *TẮT:* Giả lập click chuột thật trên màn hình (Click vào UI, part, v.v.).
    *   *BẬT:* Bỏ qua chuột, chỉ liên tục sử dụng (Activate) vật phẩm/vũ khí bạn đang cầm trên tay. Rất hữu ích khi xoay camera mà không lo bị click nhầm.
*   **Tốc độ (s):** Thời gian nghỉ giữa mỗi lần click.
    *   *Lưu ý:* Hệ thống có tính năng **Safety Limit** (Khoá an toàn). Tốc độ tối thiểu được phép nhập là `0.015` giây (để tránh làm crash game).
    *   *Tính năng ẩn:* Có tích hợp **Humanized Click** (Độ trễ dao động ngẫu nhiên siêu nhỏ) để hành vi giống con người hơn, tránh bị hệ thống Anti-Cheat quét.
*   **Số lần (0 = Vô hạn):** Tự động tắt sau khi click đủ số lần chỉ định.

---

## 📍 2. Nhóm Tính Năng: Tọa Độ & Macro Chuỗi (Sequence)
Ghi nhớ các vị trí trên màn hình và click tuần tự theo chu kỳ.

**Cách thiết lập chuỗi:**
1. Di chuyển chuột đến điểm thứ nhất cần click, ấn phím **`P`** trên bàn phím.
2. Hệ thống sẽ báo đã lưu thành công kèm tọa độ (X, Y).
3. Lặp lại bước 1 cho các điểm tiếp theo.
4. Để xóa làm lại từ đầu, bấm nút đỏ **"🗑️ Xóa toàn bộ"**.

**Chạy chuỗi:**
*   **Trạng thái chuỗi:** Bật công tắc để tool bắt đầu click lần lượt từ Điểm 1, Điểm 2, Điểm 3... rồi quay vòng. Tốc độ click lấy từ mục AutoClick ở trên.
*   **Số vòng (0 = Vô hạn):** Tự động tắt sau khi hoàn thành đủ số vòng chu kỳ đã nhập.

---

## 🛠️ 3. Nhóm Tính Năng: Tiện Ích (Utilities)

### 🛡️ Chống AFK
Roblox mặc định sẽ kick bạn ra khỏi game nếu không có thao tác trong 20 phút.
*   **Cách hoạt động:** Khi Bật tính năng này, cứ mỗi khi game phát hiện bạn chuẩn bị AFK, hệ thống sẽ tự động gõ một phím ảo (F15) để "đánh lừa" Roblox rằng bạn vẫn đang ngồi máy, giúp bạn treo game xuyên đêm không bị văng.

### 📡 Lệnh Follow (Hệ thống Radar)
Cho phép người chơi khác điều khiển nhân vật của bạn chạy đến chỗ họ.
*   **Cách hoạt động:** Khi gạt công tắc Bật, radar sẽ chuyển sang trạng thái chờ.
*   Nếu có người chơi chat từ khóa `follow`, nhân vật của bạn sẽ tự động dò tìm vị trí của họ và chạy tới.
*   **Màn hình Radar:** Bảng UI sẽ hiển thị Real-time tên người đang gọi, tọa độ XYZ của họ, hiệu ứng loading và tự động báo "✅ Đã tới mục tiêu" khi tiếp cận thành công (khoảng cách <= 4 studs).

---

## 💬 4. Bảng Lệnh Chat (Chat Commands)
Bạn hoặc người chơi khác có thể gõ các lệnh này vào khung Chat trong game để điều khiển Tool mà không cần mở Menu.

| Lệnh đầy đủ | Lệnh rút gọn (Alias) | Chức năng |
| :--- | :--- | :--- |
| `!start` | Không có | Bật AutoClick cơ bản |
| `!stop` | Không có | Tắt AutoClick cơ bản |
| `!start_seq` | `!ss` hoặc `!play` | Bật click theo Chuỗi (Sequence) |
| `!stop_seq` | `!xs` hoặc `!pause`| Tắt click theo Chuỗi |
| `follow` | Không có | Gọi nhân vật chạy tới vị trí người chat (Yêu cầu phải Bật radar Follow trước) |

> **Mẹo:** Các lệnh rút gọn như `!ss` giúp bạn thao tác cực nhanh trong những tình huống cần combat hoặc farm quái gấp.