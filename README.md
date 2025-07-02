# File permission
## chmod (change mode of file, directory)

- hôm nay tôi học về chmod và biết được cách chmod thay đổi quền của file như thế nào.

Gồm: r(4) w(2) x(1)
r: "folder" chỉ có thể thực hiện command l và không thể truy cập vào được như cd,mkdir,touch nói chung là chỉ xem được 
- không thể create folder hay file 
- không thể xóa.

r: "file" thì có thể đọc được nó. và không thể viết hoặc thực thi như lưu, sửa, hay xóa

w: folder - có thể thêm folder mới, rename, remove
- cd vào không được.
- không chạy được như node rồi execute nó sẽ không run được. nếu thêm quền x thì oke hơn.
- không tạo được folder/file mới
- remove không được

x: folder
- yes - cd  được
- not - create (touch, mkdir) file | folder
- not - list (ls)
- not - run (script, binary, etc...)

x: file
- not - run script (must have r+x) to run script
- not - write file.

## chown (change owner) file, directory



 
