# 💾 OpenStack Block Storage (Cinder) – Commands

Cinder cung cấp dịch vụ lưu trữ dạng block cho VM: tạo volume, gắn volume vào VM, snapshot, backup, và quản lý backend storage.

---
# ## Volume Commands

### ▶ Danh sách volume
```bash
openstack volume list
```

### ▶ Tạo volume mới
```bash
openstack volume create --size 10 vol-test
```

### ▶ Tạo volume từ image
```bash
openstack volume create \
  --size 20 \
  --image ubuntu-22.04 \
  vol-ubuntu
```

### ▶ Tạo volume từ snapshot
```bash
openstack volume create \
  --snapshot vol-snap1 \
  vol-from-snap
```

### ▶ Xem chi tiết volume
```bash
openstack volume show <volume-id>
```

### ▶ Xóa volume
```bash
openstack volume delete <volume-id>
```

---

# ## Volume Attachment

### ▶ Gắn volume vào VM
```bash
openstack server add volume <server> <volume>
```

### ▶ Tháo volume khỏi VM
```bash
openstack server remove volume <server> <volume>
```

### ▶ Kiểm tra volume đã attach chưa
```bash
openstack volume show <volume> | grep attachment
```

---

# ## Snapshot Commands

### ▶ Danh sách snapshot
```bash
openstack volume snapshot list
```

### ▶ Tạo snapshot
```bash
openstack volume snapshot create \
  --volume <volume-id> \
  snap-test
```

### ▶ Xem thông tin snapshot
```bash
openstack volume snapshot show <snapshot-id>
```

### ▶ Xóa snapshot
```bash
openstack volume snapshot delete <snapshot-id>
```
---
