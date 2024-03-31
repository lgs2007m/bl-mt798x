# ATF and u-boot for mt798x

## About bl-mt798x
- https://cmi.hanwckf.top/p/mt798x-uboot-usage

![](/u-boot.gif)

## Prepare

```
sudo apt install gcc-aarch64-linux-gnu build-essential flex bison libssl-dev
```

## Build UBOOT
Attention: Only used for **jdcloud_re-cp-03** and **cmcc_rax3000m-emmc**, DO NOT compile other targets.
```
SOC=mt7981 BOARD=cmcc_rax3000m-emmc ./build.sh
SOC=mt7981 BOARD=cmcc_xr30 ./build.sh
SOC=mt7986 BOARD=jdcloud_re-cp-03 ./build.sh
```
The cmcc_rax3000m-emmc and cmcc_xr30 only need to flash FIP, the FIP only support single boot, IP is 192.168.1.1  
The jdcloud_re-cp-03 need to flash **both BL2 and FIP**, the FIP only support single boot, IP is 192.168.1.1  

