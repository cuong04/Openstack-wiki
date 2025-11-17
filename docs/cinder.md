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

# ## Backup Commands

### ▶ Danh sách backup
```bash
openstack volume backup list
```

### ▶ Tạo backup volume
```bash
openstack volume backup create \
  --name backup-vol1 <volume-id>
```

### ▶ Restore backup sang volume mới
```bash
openstack volume backup restore <backup-id> <volume-id>
```

### ▶ Xóa backup
```bash
openstack volume backup delete <backup-id>
```

---

# ## Type & QoS

### ▶ Danh sách volume type
```bash
openstack volume type list
```

### ▶ Tạo volume type
```bash
openstack volume type create ssd-highspeed
```

### ▶ Tạo QoS (giới hạn IOPS)
```bash
openstack volume qos create \
  --consumer front-end \
  --property read_iops_sec=500 \
  --property write_iops_sec=300 \
  qos-low
```

### ▶ Gán QoS vào volume type
```bash
openstack volume qos associate qos-low ssd-highspeed
```

---

# ## Troubleshooting

### ▶ Kiểm tra trạng thái dịch vụ Cinder
```bash
systemctl status openstack-cinder-volume
systemctl status openstack-cinder-scheduler
systemctl status openstack-cinder-api
```

### ▶ Xem log của Cinder
```bash
tail -f /var/log/cinder/cinder-volume.log
tail -f /var/log/cinder/cinder-api.log
```

### ▶ Kiểm tra backend
```bash
grep enabled_backends /etc/cinder/cinder.conf
```

### ▶ Kiểm tra volume stuck khi deleting
```bash
openstack volume set <vol-id> --state error_deleting
```

---

> Nếu bạn muốn mình làm thêm **Cinder nâng cao** như:
> - LVM backend  
> - Ceph RBD backend  
> - Multi-backend  
> - Volume migration  
> - QoS nâng cao  
>  
> Chỉ cần nói: **“Làm thêm phần nâng cao Cinder”**.

