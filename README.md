# BaseOS Connect Protocol

Use this repository when your website is not Laravel or Node.js.
Dùng repository này khi website không chạy Laravel hoặc Node.js.

Laravel and Node already speak this protocol. Install those packages instead of reading the contract.
Laravel và Node đã nói đúng giao thức này. Hãy cài package đó, không cần đọc hợp đồng.

If you are building your own connector, three files are enough to start:

| | |
|---|---|
| What a connector must do · Việc connector phải làm | [protocol/2.1/overview.md](protocol/2.1/overview.md) |
| Pair, then publish · Ghép nối, rồi đăng bài | [protocol/2.1/pairing.md](protocol/2.1/pairing.md) |
| Request shapes · Dạng dữ liệu gửi đi | [openapi/openapi.yaml](openapi/openapi.yaml) |

BaseOS calls `https://your-domain/baseos/commands` on the website.
The website calls `https://baseos.net/api/v1/connect` on BaseOS.

BaseOS gọi `https://tên-miền/baseos/commands` trên website.
Website gọi `https://baseos.net/api/v1/connect` trên BaseOS.

The pairing code is created in the BaseOS project and is not a long-term password. After pairing, store the secret the response returns.
Mã ghép tạo trong dự án BaseOS và không phải mật khẩu dùng lâu. Sau khi ghép, lưu secret trong kết quả trả về.
