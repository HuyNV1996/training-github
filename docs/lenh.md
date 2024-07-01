# Các Lệnh Git Cơ Bản và Hay Dùng

## 1. Thiết lập thông tin người dùng

```bash
# Đặt tên người dùng
git config --global user.name "Tên của bạn"
```
## 2. Khởi tạo Repository
```sh
# Đặt email người dùng
git config --global user.email "email@example.com"
# Khởi tạo repository mới trong thư mục hiện tại
git init

# Sao chép repository từ GitHub về máy
git clone https://github.com/username/repository.git
```

## 3. Làm việc với các file
```sh
# Kiểm tra trạng thái của các file trong thư mục làm việc
git status

# Thêm file vào vùng chờ để commit
git add <tên_file>

# Thêm tất cả các file vào vùng chờ để commit
git add .

# Xóa file khỏi vùng chờ
git reset <tên_file>

# Xóa tất cả các file khỏi vùng chờ
git reset
```
## Commit các thay đổi
```sh
# Tạo commit với tin nhắn mô tả
git commit -m "Tin nhắn mô tả thay đổi"
```
### 5. Làm việc với các nhánh (Branches)
```sh
# Tạo nhánh mới
git branch <tên_nhánh>

# Chuyển sang nhánh mới
git checkout <tên_nhánh>

# Tạo và chuyển sang nhánh mới cùng lúc
git checkout -b <tên_nhánh>

# Liệt kê tất cả các nhánh
git branch

# Xóa nhánh
git branch -d <tên_nhánh>
```
## 6. Hợp nhất các nhánh (Merging)
```sh
# Chuyển về nhánh chính (thường là main)
git checkout main

# Hợp nhất nhánh khác vào nhánh hiện tại
git merge <tên_nhánh>
```
## 7. Làm việc với Remote Repository
```sh
# Thêm remote repository
git remote add origin https://github.com/username/repository.git

# Kiểm tra các remote repository
git remote -v

# Đẩy thay đổi lên remote repository
git push origin <tên_nhánh>

# Đẩy tất cả các nhánh lên remote repository
git push --all origin

# Lấy về các thay đổi từ remote repository
git pull origin <tên_nhánh>
```
### 8. Các lệnh khác
```sh
# Hiển thị lịch sử commit
git log

# Hiển thị lịch sử commit dưới dạng cây
git log --oneline --graph --all

# Hoàn tác commit cuối cùng (nhưng giữ lại thay đổi trong thư mục làm việc)
git reset --soft HEAD~1

# Hoàn tác commit cuối cùng (và loại bỏ thay đổi)
git reset --hard HEAD~1
```