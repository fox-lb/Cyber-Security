## Cấu hình tên và email người dùng.

git config —global user.name ‘username’

git config —global user.email ‘email@gmail.com’

## Hệ thống lưu trữ của GIT.

Khỏi tạo một repository : **git init**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/99b758db-d1ef-4ddc-8bf1-e5a9d45d57d3/9dbf23c6-c70b-456a-8283-62e3f3dbe2ce/Untitled.png)

1. **Thư mục làm việc (Working Directory)**: Đây là thư mục mà bạn làm việc và chỉnh sửa tập tin trong dự án của bạn. Các thay đổi trong thư mục làm việc chưa được theo dõi bởi Git cho đến khi bạn thực hiện lệnh **`git add`** để đưa chúng vào trạng thái "staging".
2. **Thư mục Staging (Staging Area)**: Đây là một vùng trung gian mà bạn sử dụng để chuẩn bị các thay đổi trước khi commit. Khi bạn chạy lệnh **`git add`**, các thay đổi sẽ được chuyển từ thư mục làm việc vào thư mục staging.
3. **Thư mục Local Repository**: Thư mục này chứa phiên bản đã commit của dự án của bạn. Khi bạn chạy **`git commit`**, các thay đổi được chuyển từ thư mục staging vào thư mục local repository và được lưu dưới dạng commit.

## Một số câu lệnh.

1. git status
    
    Hiển thị trạng thái làm việc của thư mục làm việc hiện tại và các tập tin trong dự án Git.
    
    - Các tập tin đã sửa đổi: Lệnh sẽ liệt kê các tập tin đã bị thay đổi so với phiên bản trước đó và chưa được commit.
    - Các tập tin đã được theo dõi: Nó sẽ hiển thị các tập tin đã được thêm vào trạng thái theo dõi (tracked), tức là các tập tin đã được Git theo dõi và có thay đổi so với phiên bản gốc.
    - Các tập tin mới: Lệnh cũng sẽ hiển thị các tập tin mới mà Git chưa theo dõi (untracked).
    - Các nhánh (branches): Nếu bạn đang làm việc trên một nhánh (branch), **`git status`** cũng sẽ hiển thị tên của nhánh mà bạn đang làm việc.
2. git add - git restore
    
    Lệnh **`git add`** trong hệ thống quản lý phiên bản Git được sử dụng để đưa các thay đổi từ thư mục làm việc (Working Directory) vào thư mục Staging (Staging Area) để chuẩn bị cho việc commit. Dưới đây là cú pháp cơ bản của lệnh **`git add`**:
    
    ```csharp
    
    git add tên-tập-tin
    ```
    
    - **`tên-tập-tin`**: Đây là tên của tập tin hoặc thư mục bạn muốn thêm vào thư mục Staging. Bạn có thể chỉ định tên một tập tin cụ thể hoặc sử dụng ký tự đại diện để thêm nhiều tập tin cùng lúc. Ví dụ:
        - **`git add file.txt`**: Đưa tập tin **`file.txt`** vào thư mục Staging.
        - **`git add .`**: Đưa tất cả các tập tin và thay đổi trong thư mục làm việc vào thư mục Staging.
        - **`git add *.txt`**: Đưa tất cả các tập tin có phần mở rộng **`.txt`** vào thư mục Staging.
    
    Sau khi bạn chạy lệnh **`git add`**, các thay đổi trong tập tin đã được thêm vào thư mục Staging và sẽ sẵn sàng cho việc commit bằng lệnh **`git commit`**.
    
    Lệnh **`git restore`** trong Git được sử dụng để khôi phục (restore) các tập tin trong thư mục làm việc (working directory) về trạng thái được commit hoặc trạng thái trước khi chỉnh sửa. Dưới đây là cú pháp cơ bản của lệnh **`git restore`**:
    
    ```css
    
    git restore [tùy chọn] [tên-tập-tin]
    ```
    
    - **`[tùy chọn]`**: Có thể bao gồm các tùy chọn sau:
        - **`-staged`**: Sử dụng tùy chọn này để khôi phục tập tin từ trạng thái "staged" (staging area) về trạng thái đã commit.
        - **`-worktree`**: Sử dụng tùy chọn này để khôi phục tập tin từ trạng thái đã commit về trạng thái trong thư mục làm việc.
        - **`-source=HEAD`**: Sử dụng tùy chọn này để chỉ định nguồn dữ liệu cho việc khôi phục. Trong trường hợp này, **`HEAD`** đại diện cho trạng thái đã commit.
    - **`[tên-tập-tin]`**: Tên của tập tin bạn muốn khôi phục.
3. git commit
    
    Lệnh **`git commit`** trong hệ thống quản lý phiên bản Git được sử dụng để tạo một commit, hoặc một sự thay đổi đã được lưu trữ trong kho lưu trữ Git của bạn. Commits là một cách để ghi lại các thay đổi trong dự án của bạn và bổ sung lịch sử của mã nguồn. Dưới đây là cú pháp cơ bản của lệnh **`git commit`**:
    
    ```sql
    
    git commit -m "Nội dung commit"
    ```
    
    - **`m`**: Tùy chọn này cho phép bạn gắn một thông điệp commit . Thông điệp commit nên mô tả ngắn gọn về những thay đổi mà commit này thực hiện. Thông điệp commit rất quan trọng để giúp bạn và các thành viên khác trong nhóm hiểu rõ nội dung của commit.
4. git log
    
    Lệnh **`git log`** trong hệ thống quản lý phiên bản Git được sử dụng để xem lịch sử các commit trong dự án Git.
    
    Khi bạn chạy lệnh này, Git sẽ hiển thị danh sách các commit trong dự án, bao gồm thông tin về mỗi commit như mã xác định (hash), tác giả, thời gian, và thông điệp commit.
    
    Một số tùy chọn thêm cho lệnh **`git log`** bao gồm:
    
    - **`-oneline`**: Hiển thị thông tin commit dưới dạng mỗi commit một dòng, chỉ bao gồm mã xác định và thông điệp commit.
    - **`-author="tên-tác-giả"`**: Lọc commit theo tên của tác giả.
    - **`-since="thời-gian"`**: Hiển thị commit từ một thời điểm cụ thể.
    - **`-until="thời-gian"`**: Hiển thị commit cho đến một thời điểm cụ thể.
    - **`-grep="từ-khoá"`**: Lọc commit theo từ khoá trong thông điệp commit.
    - **`-graph`**: Hiển thị lịch sử commit dưới dạng biểu đồ đồ thị.

## Branch trong Git.

Nhánh (branch) trong Git là một phiên bản riêng của mã nguồn trong dự án, cho phép bạn làm việc với mã nguồn mà không ảnh hưởng đến phiên bản chính. Nhánh giúp quản lý và phát triển dự án dễ dàng, thử nghiệm tính năng mới, và duy trì tính cách ly giữa các tính năng và phiên bản khác nhau, giúp đảm bảo tính ổn định và an toàn trong quá trình phát triển.

1. Tạo branch con trong branch đang đứng :
    
    git checkout -b <branch_name> → branch con sau khi tạo sẽ có các commit của branch cha.
    
2. Chuyển branch
    
    git checkout <branch_name>
    
3. Merge thay đổi của branch phụ vào branch chính 
    
    git merge <sub_branch_name>
    
4. Quay lại code/ dữ liệu cũ :
    
    git checkout <hash_commit_id>
    

## Kết nối Local repository với Github repository.

1. Đẩy Local repository (Kho lưu trữ trên máy cá nhân) lên Github :
    
    ```
    git remote add origin <github_repository_name.git>
    git branch -M main
    git push -u origin main
    ```
    
2. Lấy repository trên github về :
    
    git pull
    
3. Không muốn push 1 file nào đó lên Github.
    
    → git ignore
    
    → tạo file .gitignore → thêm các tên file không muốn push vào file .gitignore.