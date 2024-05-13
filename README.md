## Terraform module for creating vm on ProxmoxVE

> [!NOTE]
> This Terraform module uses the **[BPG](https://github.com/bpg/terraform-provider-proxmox)** provider version **v0.54.0**.  
> Supported version of Proxmox **8.2.0**.

This terraform module uses pre-prepared virtual machine templates.
If you use a Proxmox cluster, then virtual machine template should be located in the central storage or on each node of the cluster.

#### Creating a virtual machine template using the console
```sh
qm create 999 --name Debina11-CloudInit
qm importdisk 999 /tmp/debian-12-generic-amd64.qcow2 local-zfs
qm set 999 --scsihw virtio-scsi-pci --virtio0 local-zfs:vm-999-disk-0
qm set 999 --net0 virtio,bridge=vmbr0
qm set 999 --ostype l26
qm set 999 --ide2 local-zfs:cloudinit
qm set 999 --boot c --bootdisk virtio0
qm set 999 --serial0 socket --vga serial0
qm set 999 --agent enabled=1
qm template 999
```

## Variables info
#### Global variables
| Name | Type | Default | Example |
| ---- | ---- | ------- | ------- |

#### Cloud-Init variables
| Name | Type | Default | Example |
| ---- | ---- | ------- | ------- |

## Example of using the module
#### main.tf
```sh
```

#### output.tf
```sh
```

#### hosts.tmpl
```sh
```