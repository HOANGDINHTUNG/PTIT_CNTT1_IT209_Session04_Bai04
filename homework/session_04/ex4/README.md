# Bài 4: Quản lý tệp tin bỏ qua (.gitignore) và Sửa lịch sử (Amend)

## 1. Cách gỡ bỏ file khỏi cache của Git
Khi lỡ commit nhầm một file nhạy cảm (như `credentials.txt`), nhưng ta không muốn xoá vật lý file đó trên máy mà chỉ muốn xoá sự theo dõi của Git, ta sử dụng lệnh sau:

```bash
git rm --cached credentials.txt
```

Lệnh `--cached` giúp gỡ bỏ tệp tin khỏi **Staging Area** và bộ nhớ theo dõi của Git nhưng vẫn giữ nguyên file trên đĩa cứng.

Sau khi xoá, chúng ta cấu hình file `.gitignore` chứa nội dung là `credentials.txt` để đảm bảo từ nay trở đi Git sẽ hoàn toàn "phớt lờ" sự tồn tại của file này.

## 2. Kết quả sử dụng Amend sửa lịch sử commit
Sau khi đã gỡ bỏ file ra khỏi theo dõi và add `.gitignore` vào, chúng ta chạy lệnh sửa đổi thông điệp commit để xoá dấu vết commit nhầm trước đó:

```bash
git commit --amend -m "Initial commit without secrets"
```

Dưới đây là kết quả của lệnh `git log -n 1` để chứng minh đã sửa đổi thông điệp commit thành công:

```
commit d32a240628b78344c926108ded9e16de4ab6667a
Author: Student <student@example.com>
Date:   Mon Oct 5 20:47:53 2026 +0700

    Initial commit without secrets
```
