# Quy ước làm việc nhóm

## Quy trình cho mỗi task
1. Nhận Issue được giao (tab **Issues**, lọc theo `Assignee: me`)
2. Kéo thẻ trên bảng **Projects** sang cột **In Progress**
3. Tạo nhánh từ `main` mới nhất:
   ```bash
   git checkout main
   git pull origin main
   git checkout -b feature/<so-issue>-<mo-ta-ngan>
   ```
4. Code → commit → push:
   ```bash
   git add .
   git commit -m "feat: mô tả ngắn (#<so-issue>)"
   git push -u origin feature/<so-issue>-<mo-ta-ngan>
   ```
5. Tạo **Pull Request** vào `main`, ghi `Closes #<so-issue>`, chọn Reviewer
6. Sửa theo góp ý (commit + push lên cùng nhánh) cho tới khi được **Approve**
7. Merge (Squash and merge) → xoá nhánh → mọi người `git pull origin main`

## Đặt tên nhánh
| Loại | Mẫu | Ví dụ |
|---|---|---|
| Tính năng | `feature/<so>-<mo-ta>` | `feature/12-login-page` |
| Sửa lỗi | `fix/<so>-<mo-ta>` | `fix/18-wrong-password-msg` |
| Tài liệu | `docs/<so>-<mo-ta>` | `docs/20-readme` |

## Commit message
| Tiền tố | Dùng khi |
|---|---|
| `feat:` | Thêm tính năng |
| `fix:` | Sửa lỗi |
| `docs:` | Sửa tài liệu |
| `style:` | Định dạng code, không đổi logic |
| `refactor:` | Viết lại code, không đổi chức năng |
| `test:` | Thêm / sửa test |
| `chore:` | Việc lặt vặt (cấu hình, thư viện…) |

## Quy tắc chung
- **Không push thẳng lên `main`**
- Mỗi PR chỉ làm **một việc**, càng nhỏ càng tốt
- `git pull origin main` thường xuyên để tránh conflict
- Hạn chế hai người sửa cùng một file cùng lúc; nếu cần, báo nhau trước
