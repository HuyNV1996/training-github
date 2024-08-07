# Quy trình Git Flow khi có nhiều coder tham gia dự án

Quy trình Git Flow là một mô hình quản lý branch rất phổ biến cho các dự án có nhiều lập trình viên tham gia. Dưới đây là các bước cơ bản của Git Flow và cách sử dụng các nhánh production, develop và feature.

## Các nhánh chính

1. **master (production)**:
   - Đây là nhánh chứa mã nguồn luôn ở trạng thái ổn định và có thể triển khai ra môi trường production.
   - Mỗi khi có một phiên bản mới (release), nhánh master sẽ được cập nhật từ nhánh develop.

2. **develop**:
   - Đây là nhánh chứa mã nguồn mới nhất đã được kiểm thử nhưng chưa triển khai ra môi trường production.
   - Tất cả các tính năng mới (feature) sẽ được gộp (merge) vào nhánh develop trước khi được gộp vào nhánh master.

## Các nhánh hỗ trợ

1. **feature/**:
   - Mỗi tính năng mới sẽ được phát triển trên một nhánh riêng biệt xuất phát từ nhánh develop.
   - Tên nhánh thường có dạng `feature/ten-tinh-nang`.
   - Sau khi hoàn thành và kiểm thử tính năng, nhánh feature sẽ được gộp vào nhánh develop.

2. **release/**:
   - Khi chuẩn bị phát hành một phiên bản mới, một nhánh release sẽ được tạo từ nhánh develop.
   - Tên nhánh thường có dạng `release/ten-phien-ban`.
   - Nhánh release sẽ được sử dụng để kiểm thử cuối cùng và sửa lỗi nếu có.
   - Sau khi hoàn thành, nhánh release sẽ được gộp vào cả nhánh master và develop.

3. **hotfix/**:
   - Khi cần sửa lỗi khẩn cấp trong môi trường production, một nhánh hotfix sẽ được tạo từ nhánh master.
   - Tên nhánh thường có dạng `hotfix/ten-loi`.
   - Sau khi hoàn thành sửa lỗi, nhánh hotfix sẽ được gộp vào cả nhánh master và develop.

## Quy trình làm việc

1. **Khởi tạo dự án**:
   ```bash
   git init
   git checkout -b develop
    ```
2. **Tạo nhánh feature**:
   ```bash
    git checkout develop
    git checkout -b feature/ten-tinh-nang
    ```
- Phát triển tính năng trên nhánh feature.
- Gộp nhánh feature vào develop sau khi hoàn thành:
```bash
    git checkout develop
    git merge feature/ten-tinh-nang
    git branch -d feature/ten-tinh-nang
```

3. **Tạo nhánh release:**:
```bash
    git checkout develop
    git checkout -b release/ten-phien-ban
```
- Kiểm thử và sửa lỗi trên nhánh release.
- Gộp nhánh release vào master và develop sau khi hoàn thành:
```bash
git checkout master
git merge release/ten-phien-ban
git tag -a ten-phien-ban -m "Release ten-phien-ban"
git checkout develop
git merge release/ten-phien-ban
git branch -d release/ten-phien-ban
```
3. **Tạo nhánh hotfix:**:
```bash
    git checkout master
    git checkout -b hotfix/ten-loi
```
- Sửa lỗi trên nhánh hotfix.
- Gộp nhánh hotfix vào master và develop sau khi hoàn thành:
```bash
git checkout master
git merge hotfix/ten-loi
git tag -a ten-phien-ban-sau-hotfix -m "Hotfix ten-loi"
git checkout develop
git merge hotfix/ten-loi
git branch -d hotfix/ten-loi
```

## Kéo mã nguồn mới nhất từ các coder khác

Để các lập trình viên có thể kéo mã nguồn mới nhất từ các coder khác, quy trình làm việc thường bao gồm các bước sau đây:

### 1. Cập nhật nhánh `develop` từ remote repository

Trước khi bắt đầu công việc mới hoặc khi muốn đảm bảo mã nguồn của mình đang làm việc là mới nhất, bạn nên cập nhật nhánh `develop` từ remote repository.

```bash
git checkout develop
git pull origin develop
```
### 2. Kéo các thay đổi vào nhánh làm việc (nhánh `feature`)
Sau khi cập nhật nhánh develop, bạn cần đồng bộ nhánh làm việc (nhánh feature) của mình với nhánh develop để đảm bảo mã nguồn mới nhất được áp dụng.
```bash
git checkout feature/ten-tinh-nang
git merge develop
```
Hoặc nếu bạn muốn đảm bảo lịch sử commit của mình được rõ ràng hơn, bạn có thể sử dụng `rebase` thay vì merge:
```bash
git checkout feature/ten-tinh-nang
git rebase develop
```

### 3. Giải quyết xung đột (nếu có)
Nếu có xung đột trong quá trình merge hoặc rebase, bạn sẽ cần phải giải quyết chúng thủ công. Các bước giải quyết xung đột cơ bản:

- Mở các file bị xung đột và chỉnh sửa để giữ lại các thay đổi mong muốn.

- Sau khi giải quyết xung đột, bạn đánh dấu các file đã được giải quyết:

```bash
git add <file-da-giai-quyet>
```
Kết thúc quá trình merge hoặc rebase:

```bash
git commit
``
Hoặc với rebase:

```bash
git rebase --continue
```
### 4. Đẩy các thay đổi lên remote repository
Sau khi cập nhật và giải quyết xung đột (nếu có), bạn cần đẩy các thay đổi của nhánh feature lên remote repository để các lập trình viên khác có thể thấy được tiến độ của bạn.

```bash
git push origin feature/ten-tinh-nang
```
### 5. Quy trình làm việc hàng ngày
Dưới đây là quy trình làm việc hàng ngày mà một lập trình viên có thể tuân theo để đảm bảo mã nguồn của mình luôn được đồng bộ và cập nhật:

#### 1. Bắt đầu ngày làm việc:

- Chuyển sang nhánh develop và kéo mã nguồn mới nhất:

```bash
git checkout develop
git pull origin develop
```
- Chuyển sang nhánh feature của mình và cập nhật mã nguồn mới nhất từ nhánh develop:

```bash
git checkout feature/ten-tinh-nang
git merge develop
# Hoặc git rebase develop
```
#### 2.Trong quá trình làm việc:

Thường xuyên commit các thay đổi cục bộ:

```bash
git add .
git commit -m "Mô tả thay đổi"
```
Đồng bộ mã nguồn với remote repository:

```bash
git push origin feature/ten-tinh-nang
```
#### 3.Kết thúc ngày làm việc:

- Đảm bảo tất cả các thay đổi đã được commit và đẩy lên remote repository:

```bash
git add .
git commit -m "Cập nhật cuối ngày"
git push origin feature/ten-tinh-nang
```

## Tóm lại
Việc thường xuyên cập nhật nhánh develop và đồng bộ với nhánh feature của mình sẽ giúp bạn luôn làm việc với mã nguồn mới nhất, giảm thiểu xung đột và giúp đội ngũ phát triển phối hợp hiệu quả hơn.