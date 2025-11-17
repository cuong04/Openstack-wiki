
# 🌐 OpenStack Networking (Neutron) – Commands

## ▶ Xem danh sách network
```bash
openstack network list
```

## ▶ Xem danh sách subnet
```bash
openstack subnet list
```

## ▶ Liệt kê các ports trong OpenStack Network
```bash
openstack port list --fixed-ip ip-address=10.225.128.138 --long
```
## ▶ Xem danh sách router
```bash
openstack router list
```

## ▶ Lấy ip public cho VPC
```bash
openstack floating ip create --subnet sub-provider-net11 --floating-ip-address 192.223.15.x --project <project> provider-net11
```
