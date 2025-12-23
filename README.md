# 🤖 GenAI Content Rewriter & TTS

Ứng dụng web sử dụng Streamlit để viết lại nội dung bằng Google Gemini AI và chuyển đổi thành giọng nói tiếng Việt.

## 📋 Tính năng chính

- ✅ **Web Scraping**: Trích xuất nội dung từ bất kỳ URL nào
- ✅ **AI Rewriting**: Viết lại nội dung với 5 phong cách khác nhau
- ✅ **Tùy chỉnh độ dài**: Từ 1,000 đến 50,000 từ
- ✅ **Text-to-Speech**: Chuyển đổi thành giọng nói tiếng Việt tự nhiên
- ✅ **Chunking thông minh**: Tự động chia nội dung dài để xử lý
- ✅ **Export nhiều định dạng**: TXT, DOCX, MP3

## 🚀 Cách lấy Google Gemini API Key

### Bước 1: Truy cập Google AI Studio
1. Mở trình duyệt và truy cập: [https://makersuite.google.com/app/apikey](https://makersuite.google.com/app/apikey)
2. Đăng nhập bằng tài khoản Google của bạn

### Bước 2: Tạo API Key
1. Click vào nút **"Create API Key"** hoặc **"Get API Key"**
2. Chọn project (hoặc tạo project mới)
3. Copy API Key được tạo ra
4. **LƯU Ý**: Giữ API Key an toàn, không chia sẻ công khai

### Bước 3: Kiểm tra giới hạn
- Free tier: 60 requests/minute
- Đủ cho hầu hết các use case cá nhân

## 💻 Cài đặt và Chạy ứng dụng

### Yêu cầu hệ thống
- Python 3.8 trở lên
- pip (Python package manager)
- Internet connection

### Bước 1: Clone hoặc tải code
```bash
# Nếu dùng git
git clone <repository-url>
cd genai-content-rewriter

# Hoặc tải file zip và giải nén
```

### Bước 2: Tạo môi trường ảo (khuyến nghị)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### Bước 3: Cài đặt thư viện
```bash
pip install -r requirements.txt
```

**Lưu ý**: Nếu gặp lỗi với `newspaper3k`, cài bổ sung:
```bash
pip install lxml_html_clean
```

### Bước 4: Chạy ứng dụng
```bash
streamlit run app.py
```

### Bước 5: Mở trình duyệt
- Ứng dụng sẽ tự động mở tại: `http://localhost:8501`
- Nếu không tự động mở, copy URL từ terminal và paste vào trình duyệt

## 📖 Hướng dẫn sử dụng

### 1. Cấu hình ban đầu
- Nhập **Gemini API Key** vào sidebar (bên trái)
- Chọn **phong cách viết** (Hài hước, Chuyên gia, Kể chuyện, Tối giản, Học thuật)
- Chọn **độ dài mục tiêu** (slider từ 1,000 - 50,000 từ)
- Chọn **giọng đọc** (Nam/Nữ)

### 2. Scrape nội dung
- Vào tab **"📥 Input"**
- Dán URL bài viết vào ô input
- Click **"🌐 Scrape Content"**
- Xem preview nội dung đã scrape

### 3. Viết lại nội dung
- Vào tab **"✍️ Rewrite"**
- Click **"✨ Rewrite Now"**
- Đợi AI xử lý (có thể mất 30s - 2 phút tùy độ dài)
- Xem kết quả và tải về định dạng TXT hoặc DOCX

### 4. Tạo Audio
- Vào tab **"🔊 Audio"**
- Click **"🎙️ Generate Audio"**
- Nghe thử trên trình duyệt
- Tải về file MP3

## 🛠️ Xử lý lỗi thường gặp

### Lỗi 1: "ModuleNotFoundError"
**Nguyên nhân**: Chưa cài đủ thư viện
```bash
pip install -r requirements.txt --upgrade
```

### Lỗi 2: "API Key invalid"
**Giải pháp**:
- Kiểm tra lại API Key đã copy đúng chưa
- Đảm bảo không có khoảng trắng thừa
- Tạo API Key mới nếu cần

### Lỗi 3: "Cannot scrape URL"
**Giải pháp**:
- Kiểm tra URL có đúng định dạng không
- Thử URL khác (một số site chặn bot)
- Kiểm tra kết nối internet

### Lỗi 4: "Token limit exceeded"
**Giải pháp**:
- Ứng dụng đã có chunking tự động
- Nếu vẫn lỗi, giảm độ dài mục tiêu
- Chờ 1 phút rồi thử lại (rate limit)

### Lỗi 5: "Edge TTS connection error"
**Giải pháp**:
- Kiểm tra kết nối internet
- Restart ứng dụng
- Thử giọng đọc khác

## 📦 Cấu trúc Project

```
genai-content-rewriter/
│
├── app.py                 # File chính của ứng dụng
├── requirements.txt       # Danh sách thư viện
├── README.md             # File hướng dẫn này
│
└── temp_audio*.mp3       # File audio tạm (tự động xóa)
```

## 🎯 Các phong cách viết

1. **Hài hước**: Tạo nội dung vui nhộn, dí dỏm
2. **Chuyên gia**: Phong cách chuyên nghiệp, authority
3. **Kể chuyện**: Sinh động, có cảm xúc, narrative
4. **Tối giản**: Súc tích, đi thẳng vào vấn đề
5. **Học thuật**: Nghiêm túc, có trích dẫn, formal

## 🔊 Giọng đọc tiếng Việt

- **Nam Minh**: Giọng nam, rõ ràng, chuyên nghiệp
- **Hoài My**: Giọng nữ, tự nhiên, dễ nghe

## ⚡ Tips sử dụng hiệu quả

1. **Với bài dài** (>5000 từ):
   - App tự động chia chunks
   - Chờ xử lý từng phần (có progress bar)
   - Audio sẽ chia thành nhiều file

2. **Tối ưu chất lượng**:
   - Chọn URL từ nguồn uy tín
   - Điều chỉnh độ dài phù hợp với nội dung
   - Thử nhiều phong cách để tìm phù hợp nhất

3. **Tiết kiệm API calls**:
   - Scrape và rewrite cùng lúc nếu hài lòng với preview
   - Lưu kết quả ra file để không phải regenerate

## 🆘 Support

Nếu gặp vấn đề:
1. Kiểm tra lại các bước cài đặt
2. Đọc phần "Xử lý lỗi thường gặp"
3. Kiểm tra log trong terminal
4. Đảm bảo Python version >= 3.8

## 📄 License

Ứng dụng này được tạo cho mục đích học tập và nghiên cứu. Vui lòng tuân thủ điều khoản sử dụng của Google Gemini API.

## 🌟 Nâng cấp trong tương lai

- [ ] Hỗ trợ nhiều ngôn ngữ hơn
- [ ] Tích hợp thêm AI models
- [ ] Export sang PDF
- [ ] Lưu lịch sử rewrite
- [ ] Batch processing nhiều URL

---

**Chúc bạn sử dụng hiệu quả! 🚀**
