# File system management
## `chmod` (change mode of file, directory)

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

## `chown` (change owner) file, directory
Lệnh `chown` dùng để set chủ của file, folder, simbolic link cho một chủ mới hoặc một nhóm người mới trên hệ thống.

Chỉ những người dùng root hoặc các users có đặc quền `sudo` (priviliges) mới được phép thay đổi chủ của file/folder/ simbolic link.

SYNTAX:

```bash
sudo chown user:group files
```

- Lệnh hổ trợ list user
```bash
cat /etc/passwd

getent passwd
```

- Lệnh add user

```linux
sudo adduser username
```

- Lệnh login đến user mới
```linux
su - username | id user
```

# User Management

Trong linux thì mọi file đều được phân quền gồm r,w,e và sẽ được phân quền cho người dùng nhất định gồm owner, group, other( users).

- owner(user) người dùng hệ thống hoặc chủ file/directory có thể thao tác thư mục đổi quền thư mục.
- Group: Một nhóm người dùng được gộp chung để giúp hổ trợ phân quền một cách nhanh chống và nhiều người cùng lúc.

## Các loại user.
- Root: user tối cao có quền thay đổi quền của các user, file và cả file hệ thống.
- System user: là những user phục vụ hệ thống không truy cập cũng không login được với những user đó
   - ví dụ: www-data, mysql
- Normal user: là những user được tạo ra từ hệ thống chính bạn tạo ra có thể sữ dụng để login hay quản lý thư mục riêng của mình.

## User And Group
Để quản lý user một cách hiệu quả thì ta cần những câu lệnh quan trọng sau:
- Thêm
- List (xem danh sách người dùng, cũng như group) người dùng thuộc group nào.
- Sửa thông tin người dùng.
- Xóa người dùng.

### Thêm user mới
`adduser [username]`

Ví dụ: thêm một người dùng là userc

```bash
sudo adduser userc
```
Điều đặt biệt là chỉ người dùng root, hoặc người dùng có privaliges sudo mới có thể thêm người dùng mới.

### List user

List all user

`gentent passwd`

### Xóa user
`userdel [username]`

*Ví dụ: Để xóa một người tên thi!*

      sudo userdel thi


### Sửa thông tin người dùng
Lệnh này có thể thay đổi group của người dùng và thay đổi quền sudo cho người dùng đó.

`usermod [username]`

### Group - Thêm group
`groupadd [groupname]`

Với lệnh `groupadd` cho phép chúng ta thêm group người dùng cho hệ thống.

### Group - Xóa group
`groupdel [groupname]`

Lệnh `groupdel` ta có thể xóa group đi.

### Group - Thêm user vào group
`gpasswd -a [username] [groupname]`

### Group - Xem user thuộc group nào
`groups [username]`

Lệnh này hổ trợ xem người dùng thuộc nhóm nào.

### List group có những người nào.

`getent group [groupname]`

`getent group` - List tất cả các group người dùng. 











 
