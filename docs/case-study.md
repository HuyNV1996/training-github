# Tình huống làm việc cá nhân, thiết lập ban đầu

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
# Tình Huống Khi Làm Việc Trong Teams
## 1. Hoàn tác các thay đổi
**Tình huống**:  Bạn và đồng đội cùng làm việc trên cùng một dự án và cần đồng bộ hóa các thay đổi của nhau.
```sh
# Lấy về các thay đổi mới nhất từ remote repository
git pull origin main

# Giải quyết xung đột (nếu có) và hợp nhất các thay đổi
git merge

# Đẩy thay đổi của bạn lên remote repository
git push origin main
```
## 2. Phát triển tính năng mới
**Tình huống**:  Bạn được giao phát triển một tính năng mới và cần làm việc trên nhánh riêng.
```sh
# Tạo và chuyển sang nhánh mới cho tính năng
git checkout -b feature/new-feature

# Làm việc trên tính năng mới và commit các thay đổi
git commit -am "Develop new feature"

# Chuyển về nhánh chính và hợp nhất các thay đổi sau khi hoàn thành tính năng
git checkout main
git merge feature/new-feature

# Đẩy thay đổi lên remote repository
git push origin main
```

## 3. Tạo Pull Request
**Tình huống**:  Bạn đã hoàn thành một tính năng hoặc sửa lỗi và muốn gửi yêu cầu kéo (Pull Request) để nhờ đồng đội kiểm tra và hợp nhất vào nhánh chính.
```sh
# Đẩy nhánh của bạn lên remote repository
git push origin feature/new-feature

# Tạo Pull Request trên GitHub
# Vào repository của bạn trên GitHub, chuyển đến tab "Pull Requests" và nhấp vào nút "New Pull Request"
```
## 4. Giải quyết xung đột
**Tình huống**:  Khi hợp nhất các nhánh, có thể xảy ra xung đột và bạn cần giải quyết chúng.
```sh
# Kiểm tra các file có xung đột
git status

# Mở file có xung đột và giải quyết bằng cách giữ hoặc loại bỏ các thay đổi không mong muốn

# Thêm các file đã giải quyết xung đột vào vùng chờ
git add <file>

# Hoàn thành hợp nhất
git commit
```
# Các Thời Điểm Quan Trọng Cần Commit, Pull, Push
## Khi Nào Cần Commit
- Trước khi bắt đầu làm việc: Tạo một commit để lưu lại trạng thái hiện tại của dự án trước khi bắt đầu làm việc.
- Sau khi hoàn thành một tính năng nhỏ: Commit những thay đổi của bạn để lưu lại công việc đã hoàn thành.
- Sau mỗi lần thay đổi lớn hoặc quan trọng: Đảm bảo rằng mọi thay đổi quan trọng đều được lưu lại bằng cách commit.
- Trước khi chuyển sang nhánh khác hoặc trước khi hợp nhất nhánh: Tạo commit để lưu lại công việc hiện tại trước khi chuyển sang nhánh khác hoặc hợp nhất các thay đổi.
## Khi Nào Cần Pull
- Trước khi bắt đầu làm việc mỗi ngày: Lấy về các thay đổi mới nhất từ remote repository để đảm bảo bạn đang làm việc trên phiên bản cập nhật nhất.
- Trước khi bắt đầu làm việc trên một tính năng hoặc sửa lỗi: Đảm bảo rằng bạn có phiên bản mới nhất trước khi bắt đầu làm việc để tránh xung đột.
- Trước khi hợp nhất nhánh: Lấy về các thay đổi mới nhất từ nhánh chính để đảm bảo rằng nhánh của bạn không bị lỗi thời và không gây xung đột khi hợp nhất.
## Khi Nào Cần Push
- Sau khi hoàn thành một tính năng hoặc sửa lỗi: Đẩy các thay đổi của bạn lên remote repository để các đồng đội có thể kiểm tra và hợp nhất.
- Khi tạo Pull Request: Đảm bảo rằng mọi thay đổi đã được đẩy lên remote repository trước khi tạo Pull Request.
- Sau khi giải quyết xung đột: Đẩy các thay đổi sau khi giải quyết xung đột để đảm bảo rằng remote repository luôn có phiên bản mới nhất.

# Workflow trong Teams sử dụng GitFlow

## Mô hình GitFlow

### 1. Nhánh `main`

- **Tên khác**: `master`, `production`
- **Mục đích**: Nhánh chính chứa mã nguồn sản phẩm hoạt động, ổn định và sẵn sàng cho môi trường sản xuất.

### 2. Nhánh `develop`

- **Mục đích**: Nhánh phát triển chứa tất cả các tính năng mới đang được phát triển. Đây là nơi tích hợp các thay đổi từ các nhánh tính năng trước khi đưa vào nhánh chính.

### 3. Nhánh `feature`

- **Mục đích**: Mỗi tính năng mới được phát triển sẽ có một nhánh `feature` riêng. Nhánh này được tạo từ `develop` và sau khi hoàn thành, sẽ được hợp nhất lại vào `develop`.

### 4. Nhánh `release`

- **Mục đích**: Chuẩn bị cho việc phát hành phiên bản mới. Nhánh `release` được tạo từ `develop`, cho phép kiểm tra cuối cùng và chuẩn bị cho việc triển khai sản phẩm.

### 5. Nhánh `hotfix`

- **Mục đích**: Sửa lỗi gấp trong sản phẩm đang hoạt động trên nhánh `main` hoặc `master`.

## Áp dụng trong môi trường làm việc nhóm

### Quy trình và Quản lý Nhánh

- **Thông tin cá nhân và quyền truy cập**: Đảm bảo cấu hình Git cho từng thành viên với thông tin cá nhân đầy đủ và quyền truy cập phù hợp.

- **Quản lý nhánh**: Tuân thủ quy tắc đặt tên và quản lý các nhánh Git để giữ cho dự án có tổ chức và dễ quản lý.

- **Kiểm tra và xác nhận**: Mỗi thay đổi trước khi hợp nhất vào nhánh chính phải được kiểm tra và xác nhận bởi ít nhất một thành viên khác trong nhóm.

- **Theo dõi vấn đề**: Sử dụng issues để theo dõi và giải quyết các vấn đề trong quá trình phát triển.

Mô hình GitFlow là một cách hiệu quả để quản lý và phát triển dự án phần mềm trong một môi trường làm việc nhóm. Bạn có thể điều chỉnh và tùy biến để phù hợp với nhu cầu cụ thể của dự án.
