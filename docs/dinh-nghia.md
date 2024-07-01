# Mô Hình GitHub và Các Thành Phần Cơ Bản

GitHub là một nền tảng để lưu trữ, theo dõi và quản lý mã nguồn của các dự án phần mềm, và nó dựa trên Git, một hệ thống kiểm soát phiên bản phân tán. Dưới đây là các thành phần chính trong mô hình GitHub:

## 1. Repository (Kho chứa)
- **Định nghĩa**: Repository (repo) là một thư mục chứa tất cả các file và lịch sử chỉnh sửa (commits) của dự án.
- **Cách sử dụng**: Bạn tạo repository để bắt đầu một dự án mới hoặc để lưu trữ một dự án hiện có.
- **Ví dụ**: Bạn có thể có một repository tên là "MyWebsite" chứa tất cả mã nguồn của trang web cá nhân.

## 2. Branch (Nhánh)
- **Định nghĩa**: Branch là một phiên bản của repository. Mặc định, repository sẽ có một nhánh chính gọi là `main` (trước đây gọi là `master`).
- **Cách sử dụng**: Tạo branch mới để phát triển tính năng mới hoặc sửa lỗi mà không ảnh hưởng đến nhánh chính.
- **Ví dụ**: Bạn có thể tạo một branch tên là `feature-login` để phát triển chức năng đăng nhập.

## 3. Commit (Ghi lại)
- **Định nghĩa**: Commit là một bản ghi của các thay đổi đã thực hiện trong repository. Mỗi commit đi kèm với một tin nhắn mô tả những thay đổi đó.
- **Cách sử dụng**: Sau khi thay đổi file, bạn tạo commit để lưu lại các thay đổi đó.
- **Ví dụ**: Bạn chỉnh sửa file `index.html` và tạo một commit với tin nhắn "Thêm tiêu đề vào trang chủ".

## 4. Pull Request (Yêu cầu kéo)
- **Định nghĩa**: Pull request là một yêu cầu để hợp nhất các thay đổi từ một branch vào branch khác (thường là từ branch tính năng vào branch `main`).
- **Cách sử dụng**: Sau khi hoàn thành công việc trên một branch, bạn tạo pull request để yêu cầu người khác xem xét và hợp nhất các thay đổi của bạn.
- **Ví dụ**: Sau khi hoàn thành chức năng đăng nhập trên branch `feature-login`, bạn tạo pull request để hợp nhất nó vào branch `main`.

## 5. Issues (Vấn đề)
- **Định nghĩa**: Issues là các báo cáo về lỗi, yêu cầu tính năng hoặc các nhiệm vụ cần hoàn thành trong dự án.
- **Cách sử dụng**: Sử dụng issues để theo dõi các công việc cần làm, trao đổi và giải quyết các vấn đề phát sinh.
- **Ví dụ**: Bạn có thể tạo một issue với tiêu đề "Sửa lỗi hiển thị trên trang chủ" để thông báo về một lỗi cần khắc phục.

## 6. Merge (Hợp nhất)
- **Định nghĩa**: Merge là quá trình kết hợp các thay đổi từ một branch vào branch khác.
- **Cách sử dụng**: Sau khi pull request được chấp nhận, bạn thực hiện merge để tích hợp các thay đổi vào branch chính.
- **Ví dụ**: Hợp nhất branch `feature-login` vào branch `main` sau khi pull request được chấp nhận.

## 7. Git (Hệ thống kiểm soát phiên bản)
- **Định nghĩa**: Git là một hệ thống quản lý phiên bản phân tán, cho phép bạn theo dõi sự thay đổi của các file trong dự án.
- **Cách sử dụng**: Git quản lý các phiên bản của file, cho phép bạn chuyển đổi giữa các phiên bản, hoàn tác các thay đổi và làm việc cộng tác với người khác.
- **Ví dụ**: Bạn có thể sử dụng Git để lưu lại lịch sử chỉnh sửa của dự án và phối hợp với nhóm của bạn.

## 8. Collaboration (Hợp tác)
- **Định nghĩa**: Collaboration trên GitHub cho phép nhiều người cùng làm việc trên cùng một dự án, quản lý các phiên bản và đồng bộ hóa các thay đổi.
- **Cách sử dụng**: Mời người khác vào repository của bạn, làm việc trên các branch khác nhau, tạo pull request và sử dụng issues để trao đổi.
- **Ví dụ**: Bạn và đồng nghiệp của bạn cùng làm việc trên dự án "MyWebsite", mỗi người phát triển các tính năng khác nhau trên các branch riêng biệt.