# Các lệnh cơ bản trong git 
1. ` git config ` để set username và email của mình tập tin chính của mình 
- ` git config -- global user.name ` để kiểm tra tên 
- ` git config -- global user.email ` để kiểm tra email
- ` git config -- global user.name = "hải lương" `để set tên mới 
- ` git config -- global user.email = "luonghoanghai2005@gmail.com" `để set email mới 
2. ` git init ` để khởi tạo 1 repo 1 project mới hoặc đã có
3. ` git clone < URL > ` để copy 1 git repo từ nguồn từ xa 
4. ` git status ` để check trang thái của những file mình đã thay đổi trong thư mục 
5. ` git add ` để thay đổi đến stage/index trong thư mục 
6. ` git commit ` là một action để git lưu lại 1 snapshot của các sự thay đổi trong thư mục 
- ` git commit -m ` đây là message dùng để note những thay đổi để sau này dễ dò lại 
7. ` git push origin < branch-name> ` để gửi các commit của mình đến một kho lưu trữ từ xa 
8. ` git pull origin <branch-name> ` để tìm napj các thay đổi từ kho lưu trữ từ xa và hợp nhất chúng vào nhánh cục bộ hiện tại của mình 
9. ` git branch ` liệt kê tất cả các nhánh 
10. ` git checkout <branch> ` để chuyển sang các branch khác 
11. ` git stash ` để lưu thay đổi mà mình không muốn commit ngay lập tức 
12. ` git merge ` để hợp nhất 2 branch lại với nhau ` git merge <branch_muốn_merge> `
13. ` git remote ` để kiểm tra và liệt kê 
- ` git remote add <remote_URL> ` để thêm remote mới 
14. ` git add ` thêm file vào staging 
- `.` thêm tất cả thay đổi trong thư mục hiện taị 
- ` -A ` thêm tất cả các thay đổi trong toàn bộ repo 
- ` -U ` chỉ thêm các file đã được theo dõi ( không thêm file mới )



