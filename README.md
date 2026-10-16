# HCM-KS26-CNTT2_Nhap-mon-CNTT_Session10_Ex1
# Lợi ích của Rau sạch - Phân tích & Sửa lỗi Markdown

Tài liệu này bao gồm phân tích chi tiết các lỗi cú pháp trong bản thảo của sinh viên và cung cấp đoạn mã Markdown chuẩn hóa.

---

## Phần 1. Phân tích lỗi cú pháp và nguyên nhân Render không như ý

Đoạn mã gốc bị lỗi hiển thị trên StackEdit do vi phạm 3 quy tắc cú pháp Markdown cơ bản:

### 1. Lỗi phân cấp tiêu đề (Heading Hierarchy Skipped)
* **Lỗi cú pháp:** Sử dụng `### Danh sách các loại rau` ngay sau `# Lợi ích của rau sạch`.
* **Giải thích nguyên nhân:** Đoạn mã nhảy cấp trực tiếp từ H1 (`#`) xuống H3 (`###`) mà bỏ qua H2 (`##`). Điều này làm phá vỡ cấu trúc phân cấp tài liệu (Document Outline), khiến giao diện xem trước hiển thị tiêu đề lúc to lúc nhỏ bất hợp lý và gây khó khăn cho việc tự động tạo mục lục (TOC).

### 2. Lỗi chèn hình ảnh (Image Syntax Error)
* **Lỗi cú pháp:** Viết `[Logo Dự án] (https://greentech.vn/logo.png)` (thiếu dấu `!` và có khoảng trắng giữa cặp ngoặc).
* **Giải thích nguyên nhân:** 
  1. Thiếu dấu chấm cảm (`!`) ở đầu khiến trình biên dịch Markdown hiểu đây là một đường dẫn liên kết (**Link**) thay vì nhúng hình ảnh (**Image**).
  2. Khoảng trắng thừa giữa `]` và `(` làm câu lệnh bị mất hiệu lực trên nhiều parser.

### 3. Lỗi định dạng in đậm (Emphasis Syntax Error)
* **Lỗi cú pháp:** Viết `*Rất quan trọng*` (chỉ dùng 1 dấu sao thay vì 2 dấu sao).
* **Giải thích nguyên nhân:** Trong Markdown, 1 dấu sao (`*text*`) được dùng cho định dạng **In nghiêng** (Italic). Để **In đậm** (Bold), bắt buộc phải sử dụng 2 dấu sao (`**text**`) hoặc 2 dấu gạch dưới (`__text__`).

---

## Phần 2. Hoàn thiện đoạn mã Markdown chuẩn

Dưới đây là đoạn mã Markdown đã được chỉnh sửa chuẩn xác, tuân thủ các quy tắc phân cấp tiêu đề H1 -> H2, chèn ảnh và in đậm:

```markdown
# Lợi ích của rau sạch

## Danh sách các loại rau

![Logo Dự án](https://greentech.vn/logo.png)

**Rất quan trọng**
```

---

## Quy tắc kỹ thuật bổ sung (Bẫy dữ liệu)

* **Quy tắc H1 duy nhất:** Chỉ dùng 1 tiêu đề H1 (`#`) duy nhất trong toàn bộ tài liệu làm tên bài viết chính để tối ưu hóa SEO và cấu trúc tài liệu.
* **Khoảng cách sau `#`:** Luôn có ít nhất 1 khoảng trắng giữa ký tự `#` và nội dung tiêu đề (Ví dụ: `# Tiêu đề` là đúng, `#Tiêu đề` là sai).
