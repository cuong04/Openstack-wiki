
# 🌐 OpenStack Networking (Neutron) – Commands

## ▶ Xem danh sách network
```bash
openstack network list
```

## ▶ Tạo network mới
```bash
openstack network create private
```

## ▶ Xem danh sách subnet
```bash
openstack subnet list
```

## ▶ Tạo subnet
```bash
openstack subnet create \
  --network private \
  --subnet-range 192.168.1.0/24 \
  private-subnet
```

## ▶ Xem danh sách router
```bash
openstack router list
```

## ▶ Tạo router
```bash
openstack router create router1
```

## ▶ Thêm router vào external network
```bash
openstack router set router1 --external-gateway public
```

## ▶ Gắn router với subnet
```bash
openstack router add subnet router1 private-subnet
```

## ▶ Xóa router
```bash
openstack router delete router1
```
