I) GIT LOCAL
1 GIT luôn có 1)working space 2) state area  3)git local
-working space: thư mục đang làm việc
-git local: thư mục git ở local đang quản lý
-stage area chỉ là trung gian, không thuộc git local

* git add <file> : thêm tất cả các file đến stage area
* git add . : thêm tất cả các file đến stage area

*git commit -m "<desc>": thêm tất cả các file trong stage area đến git local
(commit 1, commit 2, commit 3, ....)

*git checkout <name commit>: chuyển đến trạng thái code ở commit nào đó

*git init: để tạo ra git local

*git config --global user.name "<USER NAME>": muốn khai báo và thay đổi username
*git config --global user.email "<EMAIL>" : muốn khai báo và thay đổi email

khi file đã có sẵn trong stage area, mà file đó ta sửa đổi, thì nó trạng thái sửa đổi(M), còn file thêm mới có trạng thái thêm mới(A)(add new), còn file còn ở working space thì nó sẽ là U

II) GIT REMOTE
có tên mặc định là origin, có thể đặt tên cho remote
* git push -u <ten-remote> master: push code từ local lên remote

* git clone: lập trình viên B là người mới vào, copy bản sao trên remote
để kết nối(git clone chỉ dùng cho lần đầu để kết nối)

*git pull: khi ông B đã kết nối, và muốn cập nhật 1 số code mới nhất thì dùng(không được dùng git clone vì nó sẽ tải toàn bộ code)

*git remote add origin <https: remote> : liên kết local với remote

*git remote -v: lấy thông tin của remote

*git push -u origin master: -u để ghi nhớ, lần sau chỉ cần *git push 

III)GIT BRANCH
Tạo nhánh để nó không can thiệp vào luồng code chính của website đang hoạt động.

*git branch <ten-branch> : tạo ra một branch mới
+
*get checkout <ten-branch> : di chuyển đến branch
=
*git checkout -b <ten-branch> : tạo mới và di chuyển đến branch đó

*git merge <ten-branch>: merge tên-branch và branch hiện tại(thường là master)
và nó tạo ra thêm 1 commit mới

*git rebase: ...................

*git log --pretty=oneline : xem mỗi commit ngắn gọn trên 1 dòng gồm id
và tên commit

--------xử lý công việc thực tế ------------------------
1) Lập trình viên A
    commit 1 chạy ổn định
    commit 2 code lỗi không để ý

BT1: lập trình viên A muốn quay lại commit 1 và coi như commit 2 chưa tồn tại

*git reset --hard <idCommit-back> : trở về 1 commit trước đó và coi như tất
cả commit sau không tồn tại

<idCommit-back>: lấy 6 số đầu hoặc là lấy tất cả

*git push -f : ép push lên bất kì lý do gì, bất chấp(hạn chế dùng, hiểu
thì dùng)

BT2: muốn giữ cả 2 commit nhưng muốn code quay về commit 1 

*git revert <idCommit> : lấy dữ liệu của 1 commit trước <idCommit>, và tạo ra
1 commit mới giống với cái commit ta cần lấy trước đó
===> cách làm này rất an toàn

2)

* origin master -- origin <ten-branch1> -- origin <ten-branch2> : các nhánh
ở trên remote

*master -- <ten-branch1> -- <ten-branch2> : các nhánh ở trên local

*git fetch: fecth các branch có trên remote mà ko copy code của nó

*git merge --abort: hủy merge

2) Lớp trưởng giao cho mỗi tổ trưởng để yêu cầu từng thành viên để giới thiệu bản thân
sau khi tổ trưởng tập hợp được các thành viên trong tổ mình, mỗi tổ trưởng sẽ báo cáo
cho lớp trưởng ==> hãy thực hiện điều đó:

Phương pháp: lớp trưởng tạo 1 repo trong máy, tạo ra 3 nhánh nhóm 1, nhóm 2, nhóm 3 và file giới thiệu
và push lên remote, các thành viên trong từng tổ clone về
+ nhóm 1 chuyển trang nhóm 1, tạo 1 nhánh là tên mình, làm việc trên đó, sau khi làm việc merge và nhóm
1 trên local rồi push lên remote, sau khi all các thành viên push xong nhóm 1, 1 thành viên nhóm
1 sẽ đại diện và tạo pull request để thông báo cho lớp trưởng merge và nhánh chính, nhóm trưởng có
thể xem trực tiếp để merge trên remote or nhóm turwuorng pull nhóm 1 về local để merge vào master
+ tương tự nhóm 2...
==>> bắt tay vào thực hành



