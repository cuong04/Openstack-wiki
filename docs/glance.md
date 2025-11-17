
# 🖼️ OpenStack Image Service (Glance) – Commands

Glance quản lý Image dùng để tạo VM: upload, list, delete, chia sẻ image, và kiểm tra format.

# ## Image Listing

### ▶ Danh sách image
```bash
openstack image list
```

### ▶ Xem chi tiết image
```bash
openstack image show <image-name-or-id>
```

---

# ## Image Upload

### ▶ Upload image dạng QCOW2
```bash
openstack image create \
  --disk-format qcow2 \
  --container-format bare \
  --file ubuntu.qcow2 \
  ubuntu-22.04
```

### ▶ Upload image dạng RAW
```bash
openstack image create \
  --disk-format raw \
  --container-format bare \
  --file centos.raw \
  centos-7
```

### ▶ Upload image Windows (QCOW2)
```bash
openstack image create \
  --disk-format qcow2 \
  --container-format bare \
  --property hw_disk_bus=scsi \
  --property hw_scsi_model=virtio-scsi \
  --file windows-2022.qcow2 \
  win-2022
```

---

# ## Image Properties

### ▶ Xem tất cả properties của image
```bash
openstack image show <image> 
```

### ▶ Thêm custom property
```bash
openstack image set --property os_type=linux <image>
```

### ▶ Thêm property cho Windows
```bash
openstack image set \
  --property hw_disk_bus=scsi \
  --property hw_scsi_model=virtio-scsi \
  --property os_type=windows \
  win-2022
```

### ▶ Disable image (không cho user dùng)
```bash
openstack image set --disable <image>
```

### ▶ Enable image
```bash
openstack image set --enable <image>
```

---

# ## Image Sharing

### ▶ Share image cho project khác
```bash
openstack image add project <image-id> <project-id>

openstack image set --accept --project <ID_Project> <Image_ID>
```

### ▶ Cho phép project accept share
```bash
openstack image set --accept <image-id>
```

### ▶ Tắt share
```bash
openstack image remove project <image-id> <project-id>
```

---

# ## Image Delete

### ▶ Xóa image
```bash
openstack image delete <image>
```

---

# ## Image Troubleshooting

### ▶ Kiểm tra image
```bash
openstack image list 
```

