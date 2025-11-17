# 🔐 OpenStack Identity (Keystone) – Commands

Keystone quản lý xác thực (authentication), phân quyền (authorization), user, role, project và token trong OpenStack.

# ## User Commands

### ▶ Danh sách user
```bash
openstack user list
```

### ▶ Tạo user mới
```bash
openstack user create --password <password> <username>
```

### ▶ Set email cho user
```bash
openstack user set --email user@example.com <username>
```

### ▶ Khóa user
```bash
openstack user set --disable <username>
```

### ▶ Mở khóa user
```bash
openstack user set --enable <username>
```

### ▶ Xóa user
```bash
openstack user delete <username>
```

---

# ## Project Commands

### ▶ Danh sách project
```bash
openstack project list
```

### ▶ Tạo project mới
```bash
openstack project create <project-name>
```

### ▶ Disable ( enable) project 
```bash
openstack project set --disable ( enable ) <project-name>
```

### ▶ Xóa project
```bash
openstack project delete <project-name>
```

---

# ## Role Commands

### ▶ Danh sách role
```bash
openstack role list
```

### ▶ Tạo role mới
```bash
openstack role create <role-name>
```

### ▶ Gán role cho user trong project
```bash
openstack role add --project <project-name> --user <username> <role-name>
```

### ▶ Gỡ role
```bash
openstack role remove --project <project-name> --user <username> <role-name>
```

---

# ## Token Commands

### ▶ Lấy token hiện tại
```bash
openstack token issue
```

### ▶ Xem thông tin token
```bash
openstack token issue --debug
```





