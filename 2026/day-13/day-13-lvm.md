# Linux Volume Management (LVM)

## Task Done 

## Before You Start

Switch to root user:
```bash
sudo -i
```
<img width="213" height="119" alt="image" src="https://github.com/user-attachments/assets/6f63800b-f2bd-4c53-bcd5-9b8ae60b1519" />
or
```bash
sudo su
```

<img width="216" height="65" alt="image" src="https://github.com/user-attachments/assets/4a87ac9c-17e2-422b-952b-c50ab69578ca" />

No spare disk? Create a virtual one (watch the tutorial):
```bash
dd if=/dev/zero of=/tmp/disk1.img bs=1M count=1024
losetup -fP /tmp/disk1.img
losetup -a   # Note the device name (e.g., /dev/loop0)
```
<img width="611" height="188" alt="image" src="https://github.com/user-attachments/assets/55bef81e-a9ac-43ad-91c2-245f26b54ee6" />

---

## Challenge Tasks

### Check Current Storage
Run: `lsblk`, `pvs`, `vgs`, `lvs`, `df -h`

<img width="426" height="363" alt="image" src="https://github.com/user-attachments/assets/cf9d1738-a6f7-4118-ae4e-5e34fb4b2914" />

```
###  Format and Mount
```bash
mkfs.ext4 /dev/devops-vg/app-data
mkdir -p /mnt/app-data
mount /dev/devops-vg/app-data /mnt/app-data
df -h /mnt/app-data
```
<img width="633" height="171" alt="image" src="https://github.com/user-attachments/assets/643c2515-20dc-45ed-a8b0-7cf0570ef8a5" />

## Documentation

Create `day-13-lvm.md` with:
- Commands used
- Screenshots of outputs
- What you learned (3 points)

---

## Submission
1. Add your `day-13-lvm.md` to `2026/day-13/`
2. Commit and push

---

## Learn in Public

Share your LVM progress on LinkedIn.

```
#90DaysOfDevOps #DevOpsKaJosh #TrainWithShubham
```

Happy Learning!
**Mahendra Singh**

