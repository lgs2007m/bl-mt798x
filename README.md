# ATF and u-boot for mt798x

## About bl-mt798x
- https://cmi.hanwckf.top/p/mt798x-uboot-usage

![](/u-boot.gif)

## Prepare

```
sudo apt install gcc-aarch64-linux-gnu build-essential flex bison libssl-dev
```

## Build UBOOT
Attention: Only use for **jdcloud_re-cp-03**, **cmcc_rax3000m-emmc** and **cmcc_xr30-emmc**. DO NOT compile for other targets.
```
SOC=mt7981 BOARD=cmcc_rax3000m-emmc ./build.sh
SOC=mt7981 BOARD=cmcc_xr30-emmc ./build.sh
SOC=mt7986 BOARD=jdcloud_re-cp-03 ./build.sh
```
The FIP only support single boot, IP is 192.168.1.1  
The cmcc_rax3000m-emmc and cmcc_xr30-emmc only need to flash FIP.  
The jdcloud_re-cp-03 need to flash **both BL2 and FIP**, only flashing FIP would cause the device to brick!  

## Generate GPT with python2.7
```
cd bl-mt798x/atf-20231013-0ea67d76a/tools/dev/gpt_editor
./generate_gpt.sh
```
The GPT binaries will be located in this directory: bl-mt798x/atf-20231013-0ea67d76a/tools/dev/gpt_editor/gpt_output
