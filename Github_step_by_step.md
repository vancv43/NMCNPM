
HƯỚNG DẪN SỬ DỤNG GITHUB TỪNG BƯỚC 

 Hướng dẫn sử dụng git bằng bằng dòng lệnh
Đây là bài viết dành cho người mới bắt đầu sừ dụng git, phù hợp cho học sinh, sinh viên, người mới ra trường, hoặc mới đi làm.

Yêu cầu:

Git đã được cài đặt trên máy.
Cửa sổ dòng lệnh (Terminal/CMD)
1. Git là gì?
Git là một hệ thống quản lý phiên bản phân tán (Distributed Version Control System - DVCS) được sử dụng để theo dõi sự thay đổi trong mã nguồn của phần mềm trong quá trình phát triển. Nó cho phép nhiều người làm việc trên cùng một dự án mà không gặp phải vấn đề xung đột mã nguồn.

2. Công dụng của Git
Theo dõi sự thay đổi: Git cho phép bạn theo dõi tất cả các thay đổi trong mã nguồn, giúp bạn biết được ai đã thực hiện thay đổi gì và khi nào.
Phối hợp nhóm: Git cho phép nhiều lập trình viên làm việc trên cùng một dự án mà không lo sợ về việc xung đột mã nguồn.
Quản lý phiên bản: Git lưu trữ tất cả các phiên bản của mã nguồn, cho phép bạn dễ dàng quay lại phiên bản cũ nếu cần thiết.
Phân nhánh và gộp nhánh: Git cho phép tạo ra các nhánh để phát triển các tính năng mới, sửa lỗi, mà không ảnh hưởng đến nhánh chính (main branch). Khi hoàn thành, bạn có thể gộp (merge) nhánh đó vào nhánh chính.
3. Cách hoạt động của Git
1. Khái niệm cơ bản
Repository (Kho chứa): Là nơi lưu trữ mã nguồn và lịch sử thay đổi của dự án. Một repository có thể nằm trên máy tính của bạn (local repository) hoặc trên máy chủ (remote repository).
Commit: Là một phiên bản của mã nguồn. Mỗi commit chứa thông tin về sự thay đổi, người thực hiện thay đổi và thời gian thực hiện.
Branch (Nhánh): Là một dòng phát triển độc lập. Nhánh chính thường được gọi là main hoặc master.
Merge: Là hành động gộp các thay đổi từ nhánh này vào nhánh khác.
Clone: Là việc sao chép một repository từ máy chủ về máy tính cá nhân.
Push: Là hành động gửi các commit từ local repository lên remote repository.
Pull: Là hành động cập nhật local repository với các thay đổi từ remote repository.
2. Các lệnh Git cơ bản
git init: Khởi tạo một repository mới.
git clone [URL]: Sao chép một repository từ remote về máy tính cá nhân.
git add [file]: Thêm một file vào danh sách chuẩn bị commit.
git commit -m "message": Tạo một commit với thông điệp mô tả thay đổi.
git push: Gửi các commit từ local repository lên remote repository.
git pull: Cập nhật local repository với các thay đổi từ remote repository.
git branch: Liệt kê các nhánh hiện có hoặc tạo nhánh mới.
git checkout [branch]: Chuyển đổi giữa các nhánh.
git merge [branch]: Gộp các thay đổi từ nhánh chỉ định vào nhánh hiện tại.
4. Quy trình làm việc cơ bản với Git
Khởi tạo repository: Sử dụng git init để khởi tạo repository hoặc git clone để sao chép repository từ remote.
Tạo và làm việc trên nhánh mới: Sử dụng git branch để tạo nhánh mới và git checkout để chuyển sang nhánh đó.
Thực hiện thay đổi và commit: Sử dụng git add để thêm các file thay đổi vào danh sách chuẩn bị commit, và git commit để tạo commit.
Gộp nhánh: Khi hoàn thành công việc, sử dụng git merge để gộp các thay đổi từ nhánh đó vào nhánh chính.
Đồng bộ với remote repository: Sử dụng git push để gửi các commit từ local repository lên remote repository và git pull để cập nhật local repository với các thay đổi từ remote repository.
5. Giải thích chi tiết về git commit, git push, và git pull
1. git commit
git commit là lệnh dùng để ghi lại các thay đổi trong kho lưu trữ (repository). Mỗi commit là một phiên bản của mã nguồn, chứa các thông tin như:

Các thay đổi đã thực hiện.
Ai đã thực hiện thay đổi.
Thời gian thay đổi.
a. Cú pháp cơ bản:

git commit -m "Thông điệp mô tả thay đổi"
b. Quy trình:

Thực hiện thay đổi trong mã nguồn.
Sử dụng lệnh git add [file] hoặc git add . để thêm các thay đổi vào staging area.
Chạy lệnh git commit để lưu các thay đổi vào lịch sử của repository.
c. Ví dụ:

git add .
git commit -m "Sửa lỗi và cải tiến hiệu suất"
2. git push
git push là lệnh dùng để gửi các commit từ kho lưu trữ cục bộ (local repository) lên kho lưu trữ từ xa (remote repository). Điều này giúp đồng bộ mã nguồn của bạn với các thành viên khác trong nhóm.

a. Cú pháp cơ bản:

git push origin [branch]

# Hoặc dùng cú pháp rút gọn
git push
b. Quy trình:

Đảm bảo đã commit các thay đổi cần thiết.
Chạy lệnh git push để gửi các commit lên remote repository.
c. Ví dụ:

git push origin main
3. git pull
git pull là lệnh dùng để cập nhật kho lưu trữ cục bộ với các thay đổi từ kho lưu trữ từ xa. Nó kết hợp hai lệnh git fetch (tải về các thay đổi từ remote) và git merge (gộp các thay đổi vào nhánh hiện tại).

a. Cú pháp cơ bản:

git pull origin [branch]
b. Quy trình:

Chạy lệnh git pull để tải về và gộp các thay đổi từ remote repository vào local repository.
c. Ví dụ:

git pull origin main
6. Tại sao cần commit rồi push?
1. Quản lý phiên bản cục bộ:

Commit giúp bạn lưu lại các thay đổi cục bộ trên máy tính, tạo ra các điểm phục hồi mà bạn có thể quay lại nếu cần thiết. Mỗi commit là một phiên bản mới của mã nguồn, giúp bạn theo dõi lịch sử phát triển của dự án.
2. Đồng bộ với nhóm:

Push gửi các commit từ máy tính của bạn lên remote repository, cho phép các thành viên khác trong nhóm có thể thấy và sử dụng các thay đổi của bạn. Điều này giúp mọi người trong nhóm làm việc trên cùng một phiên bản của mã nguồn, tránh xung đột và đảm bảo sự nhất quán.
7. Tại sao cần pull?
1. Cập nhật mã nguồn mới nhất:

Pull giúp bạn tải về các thay đổi mới nhất từ remote repository, đảm bảo rằng bạn đang làm việc với phiên bản mới nhất của mã nguồn. Điều này rất quan trọng khi làm việc trong nhóm để tránh xung đột và lỗi không mong muốn.
2. Giảm xung đột:

Khi nhiều người làm việc trên cùng một dự án, các xung đột mã nguồn có thể xảy ra. Pull giúp bạn nhận các thay đổi của người khác trước khi tiếp tục làm việc, giúp giảm thiểu xung đột khi bạn push các thay đổi của mình lên.
8. Cấu hình tên người dùng và địa chỉ email
Tên người dùng và địa chỉ email sẽ được sử dụng trong mỗi commit để xác định ai đã thực hiện thay đổi đó.

Thiết lập tên người dùng:

git config --global user.name "Tên của bạn"
Thiết lập địa chỉ email:

git config --global user.email "email@example.com"
Ví dụ:

git config --global user.name "Nguyễn Văn A"
git config --global user.email "nguyenvana@example.com"
Kiểm tra tên người dùng:

git config --global user.name
Kiểm tra địa chỉ email:

git config --global user.email
9. Cấu hình kho lưu trữ từ xa (origin)
Liên kết kho lưu trữ từ xa (remote repository) giúp bạn đẩy (push) và kéo (pull) mã nguồn từ một máy chủ khác, như GitHub, GitLab, hoặc Bitbucket.

Thêm liên kết kho lưu trữ từ xa:

git remote add origin [URL]
Ví dụ: Nếu bạn có một kho lưu trữ trên GitHub với URL https://github.com/username/repository.git, bạn có thể thêm nó vào 1 local repository như sau:

# cd /path/to/local/repository
git remote add origin https://github.com/username/repository.git
Cập nhật liên kết kho lưu trữ từ xa:

git remote set-url origin [URL mới]
Ví dụ: Nếu bạn muốn cập nhật URL của origin từ https://github.com/username/old-repo.git sang https://github.com/username/new-repo.git, bạn thực hiện như sau:

git remote set-url origin https://github.com/username/new-repo.git
Kiểm tra liên kết kho lưu trữ từ xa: Bạn có thể kiểm tra lại liên kết kho lưu trữ từ xa để đảm bảo rằng nó đã được thiết lập đúng.

git remote -v
Ví dụ:

git remote -v
# Output:
# origin  https://github.com/username/repository.git (fetch)
# origin  https://github.com/username/repository.git (push)
10. Hướng dẫn cách tạo, chuyển, và xoá nhánh
1. Tạo nhánh mới
Tạo nhánh mới giúp bạn phát triển tính năng hoặc sửa lỗi một cách độc lập mà không ảnh hưởng đến nhánh chính (main/master).

Lệnh tạo nhánh:

git branch [tên nhánh]
Ví dụ:

git branch feature/new-feature
2. Chuyển sang nhánh khác
Chuyển sang nhánh khác cho phép bạn làm việc trên nhánh đó.

Lệnh chuyển nhánh:

git checkout [tên nhánh]
Ví dụ:

git checkout feature/new-feature
Hoặc bạn có thể kết hợp tạo và chuyển sang nhánh mới bằng một lệnh duy nhất:

Lệnh tạo và chuyển sang nhánh mới:

git checkout -b [tên nhánh]
Ví dụ:

git checkout -b feature/new-feature
3. Xóa nhánh
Xóa nhánh giúp bạn dọn dẹp các nhánh không cần thiết sau khi hoàn thành công việc.

Lệnh xóa nhánh cục bộ:

git branch -d [tên nhánh]
Ví dụ:

git branch -d feature/new-feature
Nếu nhánh chưa được gộp (merged) và bạn vẫn muốn xóa, sử dụng lệnh sau:

git branch -D [tên nhánh]
Ví dụ:

git branch -D feature/new-feature
Lệnh xóa nhánh từ xa:

git push origin --delete [tên nhánh]
Ví dụ:

git push origin --delete feature/new-feature
11. Quay lại một thời điểm trong lịch sử
1. Kiểm tra một commit cũ mà không thay đổi lịch sử hiện tại (git checkout)
Phương pháp này cho phép bạn xem lại mã nguồn tại một commit cũ mà không thay đổi lịch sử của nhánh hiện tại. Sau khi kiểm tra, bạn có thể quay lại nhánh trước đó.

Lệnh:

git checkout [commit-hash]
Ví dụ:

git checkout 1a2b3c4d
Quay lại nhánh trước đó:

git checkout [branch-name]
2. Tạo nhánh mới từ một commit cũ
Phương pháp này tạo một nhánh mới từ một commit cũ. Điều này hữu ích khi bạn muốn phát triển hoặc sửa lỗi dựa trên phiên bản cũ mà không ảnh hưởng đến nhánh hiện tại.

Lệnh:

git checkout -b [new-branch-name] [commit-hash]
Ví dụ:

git checkout -b feature/from-old-commit 1a2b3c4d
3. Đặt lại nhánh hiện tại về một commit cũ (git reset)
Phương pháp này thay đổi lịch sử của nhánh hiện tại, đặt lại trạng thái của repository về một commit trước đó. Có hai loại reset: --soft và --hard.

Soft reset: Giữ lại các thay đổi trong staging area (các thay đổi sẽ chưa được commit).
Hard reset: Xóa bỏ tất cả các thay đổi và quay lại trạng thái hoàn toàn của commit đó.
Soft reset:

git reset --soft [commit-hash]
Hard reset:

git reset --hard [commit-hash]
Ví dụ:

git reset --soft 1a2b3c4d
git reset --hard 1a2b3c4d
4. Sử dụng git revert
Phương pháp này tạo ra một commit mới để đảo ngược các thay đổi từ một commit trước đó mà không thay đổi lịch sử hiện tại. Đây là cách an toàn để quay lại mà không làm mất các commit sau đó.

Lệnh:

git revert [commit-hash]
Ví dụ:

git revert 1a2b3c4d
12. Gộp nhánh (merge)
1. Chuẩn bị trước khi gộp nhánh
Trước khi gộp nhánh, bạn cần đảm bảo rằng nhánh hiện tại đã cập nhật các thay đổi mới nhất từ kho lưu trữ từ xa (remote repository).

Cập nhật nhánh hiện tại:

git pull origin [branch-name]
Ví dụ:

git pull origin main
2. Gộp nhánh
Giả sử bạn muốn gộp nhánh feature/new-feature vào nhánh main.

Bước 1: Chuyển sang nhánh chính (hoặc nhánh bạn muốn gộp vào):

git checkout main
Bước 2: Gộp nhánh tính năng vào nhánh chính:

git merge feature/new-feature
3. Xử lý xung đột (nếu có)
Trong quá trình gộp nhánh, nếu có xung đột (conflict), Git sẽ thông báo cho bạn biết các tệp bị xung đột và yêu cầu bạn giải quyết.

Bước 1: Kiểm tra các tệp bị xung đột (conflict):

git status
Bước 2: Giải quyết xung đột (conflict) Mở các tệp bị xung đột, tìm kiếm các dấu hiệu của Git (<<<<<<<, =======, >>>>>>>) và giải quyết xung đột bằng cách giữ lại các thay đổi mong muốn.

Bước 3: Sau khi giải quyết xung đột, thêm các tệp đã được sửa lại vào staging area:

git add [file-name]
Ví dụ:

git add file-with-conflict.txt
Bước 4: Hoàn thành quá trình gộp nhánh sau khi đã giải quyết xung đột:

git commit
4. Đẩy các thay đổi lên kho lưu trữ từ xa
Sau khi gộp nhánh thành công và giải quyết xung đột (nếu có), bạn nên đẩy các thay đổi lên kho lưu trữ từ xa.

Lệnh đẩy:

git push origin main
13. Cách dùng stash
Tính năng stash trong Git cho phép bạn lưu trữ tạm thời các thay đổi trong thư mục làm việc của mình mà không cần phải commit chúng. Điều này rất hữu ích khi bạn đang làm việc dở trên một tính năng hoặc sửa lỗi và cần chuyển sang một nhánh khác để giải quyết công việc khẩn cấp. Sau khi hoàn thành công việc khẩn cấp, bạn có thể quay lại và khôi phục các thay đổi tạm thời mà bạn đã lưu trữ.

1. Lưu trữ các thay đổi tạm thời (git stash)
Khi bạn muốn lưu trữ các thay đổi hiện tại mà không cần commit, bạn có thể sử dụng lệnh git stash.

Lệnh:

git stash
Ví dụ:

git stash
# Output: Saved working directory and index state WIP on main: 1a2b3c4d Your commit message
2. Xem danh sách các stash (git stash list)
Bạn có thể xem lại các thay đổi đã được lưu trữ bằng lệnh git stash list.

Lệnh:

git stash list
Ví dụ:

git stash list
# Output:
# stash@{0}: WIP on main: 1a2b3c4d Your commit message
# stash@{1}: WIP on main: 5e6f7g8h Another commit message
3. Khôi phục các thay đổi đã lưu trữ (git stash apply)
Để khôi phục lại các thay đổi từ stash mà không xóa chúng khỏi danh sách stash, sử dụng lệnh git stash apply.

Lệnh:

git stash apply [stash-id]
Ví dụ:

git stash apply stash@{0}
Nếu bạn không chỉ định stash-id, Git sẽ mặc định áp dụng stash mới nhất (stash@{0}).

4. Khôi phục và xóa stash (git stash pop)
Nếu bạn muốn khôi phục lại các thay đổi từ stash và đồng thời xóa nó khỏi danh sách stash, sử dụng lệnh git stash pop.

Lệnh:

git stash pop [stash-id]
Ví dụ:

git stash pop stash@{0}
5. Xóa stash (git stash drop)
Nếu bạn muốn xóa một stash cụ thể mà không áp dụng nó, sử dụng lệnh git stash drop.

Lệnh:

git stash drop [stash-id]
Ví dụ:

git stash drop stash@{0}
Nếu bạn không chỉ định stash-id, Git sẽ mặc định xóa stash mới nhất (stash@{0}).

6. Xóa tất cả các stash (git stash clear)
Nếu bạn muốn xóa tất cả các stash cùng một lúc, sử dụng lệnh git stash clear.

Lệnh:

git stash clear