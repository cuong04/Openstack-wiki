## #OpenStack Compute (Nova) – Commands

## ▶ Xem danh sách instance
```bash
openstack server list
```

## ▶ Xem chi tiết một instance
```bash
openstack server show <instance>
```

---

## #Flavor Commands

## ▶ List flavor
```bash
openstack flavor list
```

## ▶ Tạo flavor
```bash
openstack flavor create --public 2C18G \
  --ram 18432 \
  --disk 0 \
  --vcpus 2 \
  --rxtx-factor 1 \
  --property aggregate_instance_extra_specs:pinned='false' \
  --property hw:cpu_policy='shared' \
  --property hw:vif_multiqueue_enabled=true \
  --property bss:active='true'
```

## ▶ set flavor
```bash
openstack flavor set --project <project_id_or_name> <flavor_id_or_name>
```
