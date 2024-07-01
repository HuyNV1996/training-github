# Các Tình Huống Thực Tế và Lệnh Git Tương Ứng

## 1. Thiết lập thông tin người dùng

**Tình huống**: Bạn mới bắt đầu sử dụng Git và cần thiết lập thông tin cá nhân để các commit có thông tin người tạo.

```bash
git config --global user.name "Tên của bạn"
git config --global user.email "email@example.com"
```
## 2. Khởi tạo Repository

**Tình huống**:  Bạn muốn khởi tạo một dự án mới từ đầu hoặc sao chép một dự án từ GitHub về máy tính cá nhân.
```sh
# Khởi tạo repository mới trong thư mục hiện tại
git init

# Sao chép repository từ GitHub về máy
git clone https://github.com/username/repository.git
```
## 3. Thêm file vào Repository

**Tình huống**:  Bạn đã tạo hoặc sửa đổi các file và muốn thêm chúng vào vùng chờ để chuẩn bị commit.
```sh
# Kiểm tra trạng thái của các file trong thư mục làm việc
git status

# Thêm một file cụ thể vào vùng chờ
git add <tên_file>

# Thêm tất cả các file thay đổi vào vùng chờ
git add .
```
## 4. Commit các thay đổi
**Tình huống**:  Bạn đã thêm các thay đổi vào vùng chờ và muốn lưu lại chúng trong lịch sử phiên bản.
```sh
# Tạo commit với tin nhắn mô tả
git commit -m "Tin nhắn mô tả thay đổi"
```
## 5. Làm việc với các nhánh (Branches)
**Tình huống**:  Bạn muốn phát triển một tính năng mới mà không ảnh hưởng đến nhánh chính.
```sh
# Tạo nhánh mới
git branch <tên_nhánh>

# Chuyển sang nhánh mới
git checkout <tên_nhánh>

# Tạo và chuyển sang nhánh mới cùng lúc
git checkout -b <tên_nhánh>
```
## 6. Hợp nhất các nhánh (Merging)
**Tình huống**:  Bạn đã hoàn thành công việc trên một nhánh tính năng và muốn hợp nhất nó vào nhánh chính.
```sh
# Chuyển về nhánh chính (thường là main)
git checkout main

# Hợp nhất nhánh khác vào nhánh hiện tại
git merge <tên_nhánh>
```
## 7. Làm việc với Remote Repository
**Tình huống**:  Bạn muốn đẩy thay đổi lên GitHub hoặc lấy về các thay đổi mới nhất từ GitHub.
```sh
# Thêm remote repository
git remote add origin https://github.com/username/repository.git

# Đẩy thay đổi lên remote repository
git push origin <tên_nhánh>

# Lấy về các thay đổi từ remote repository
git pull origin <tên_nhánh>
```
## 8. Hiển thị lịch sử commit
**Tình huống**:  Bạn muốn kiểm tra lại các thay đổi đã thực hiện trong dự án.
```sh
# Hiển thị lịch sử commit
git log

# Hiển thị lịch sử commit dưới dạng cây
git log --oneline --graph --all
```
## 9. Hoàn tác các thay đổi
**Tình huống**:  Bạn đã commit một thay đổi nhưng muốn hoàn tác nó.
```sh
# Hoàn tác commit cuối cùng (nhưng giữ lại thay đổi trong thư mục làm việc)
git reset --soft HEAD~1

# Hoàn tác commit cuối cùng (và loại bỏ thay đổi)
git reset --hard HEAD~1
```
