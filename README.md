# Automation — trang chính sách quyền riêng tư

Website tĩnh tiếng Việt cho ứng dụng Meta **Automation**, không cần build hoặc cài thư viện.

## Nội dung

- `index.html`: chính sách quyền riêng tư.
- `data-deletion.html`: hướng dẫn thu hồi quyền và yêu cầu xóa dữ liệu.
- `.nojekyll`: phục vụ trực tiếp các tệp tĩnh trên GitHub Pages.

## Xác nhận trước khi công khai

Nội dung được soạn theo thông tin chủ ứng dụng cung cấp: đăng bài, đọc bình luận và số liệu tương tác; không lưu dữ liệu Facebook trên máy chủ; không chuyển dữ liệu sang AI/bên thứ ba. Liên hệ công khai: **toriop.dev@gmail.com**. Đơn vị vận hành: **Trần Vinh Quang**.

Hãy đối chiếu với ứng dụng thực tế, đặc biệt database, log, bản sao lưu, cache và dịch vụ bên ngoài. Nếu chúng ghi lại nội dung Facebook, cần sửa chính sách trước khi công khai. Token là thông tin xác thực nhạy cảm: kiểm tra riêng việc lưu token, không đưa token hoặc app secret vào repo/trang web. Bản thảo này không thay thế tư vấn pháp lý và không bảo đảm Meta phê duyệt ứng dụng.

## Xem tại máy của bạn

Trong thư mục repo:

```sh
python3 -m http.server 8080 --bind 127.0.0.1
```

Mở http://127.0.0.1:8080/ trên chính máy chạy lệnh. Không cần mở cổng nội bộ ra Internet.

## Đẩy lên GitHub

Repo local đã được khởi tạo với nhánh `main`, chưa có commit hoặc remote.
Tạo một repository **Public**, tên `automation-privacy` trên tài khoản GitHub của bạn. Không chọn thêm README, license hoặc .gitignore khi tạo remote trống.

Sau khi xem duyệt nội dung, chạy trong thư mục repo:

```sh
git add index.html data-deletion.html .nojekyll README.md
git commit -m "Add Automation privacy policy and data deletion instructions"
git remote add origin git@github.com:YOUR_GITHUB_USERNAME/automation-privacy.git
git push -u origin main
```

Thay `YOUR_GITHUB_USERNAME` bằng tên tài khoản thật. Nếu tải file ZIP, giải nén và chạy `git init -b main` trước các lệnh trên vì ZIP không chứa thư mục `.git`.

## Bật GitHub Pages

1. Vào repo trên GitHub → **Settings → Pages**.
2. Trong **Build and deployment**, chọn **Deploy from a branch**.
3. Chọn nhánh **main**, thư mục **/ (root)** rồi **Save**.
4. Chờ triển khai; lấy URL thực tế mà GitHub hiển thị và mở thử bằng cửa sổ ẩn danh.

Với repo `automation-privacy`, địa chỉ thông thường là:

- Privacy Policy URL: `https://YOUR_GITHUB_USERNAME.github.io/automation-privacy/`
- User Data Deletion Instructions URL: `https://YOUR_GITHUB_USERNAME.github.io/automation-privacy/data-deletion.html`

Đây là mẫu URL, không phải website đã triển khai. Nếu dùng custom domain hoặc đổi tên repo, dùng URL thực tế của GitHub Pages.

## Điền vào Meta

Trong **App settings → Basic**:

- Điền link trang chính sách vào **Privacy Policy URL**.
- Nếu có trường **User data deletion**, chọn kiểu **Data deletion instructions URL** và điền link `data-deletion.html`. Đây là trang hướng dẫn, không phải callback API; không chọn kiểu callback.
- Lưu thay đổi, quay lại **Publish** và kiểm tra các yêu cầu còn lại.

Website này không chứa chức năng đăng nhập Facebook, không lưu token và không phải backend ứng dụng Automation.
