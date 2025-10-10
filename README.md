# nubia_sm8650_eng

> Extracted from `Red Magic 9 Pro+ (NX769J) Engineering ROM HiUnlockSupport.zip`

## Supported models

| Device (public codename) (codename) | Tested |
| ----------------------------------- | ------ |
| ZTE nubia Z60 Ultra (`nx721j` `pq83a01`) (`cerro`) | [v] |
| ZTE nubia Z60 Ultra Leading Edition (`nx721j` `pq83a01`) (`cerro`) | [v] |
| ZTE nubia Red Magic 9 Pro (`nx769j`) (`tiro`) | [v] |
| ZTE nubia Red Magic 9S Pro (`nx769j`) (`tiro`) | [v] |

```
[v] = Tested and working
[x] = Not working
[?] = Unknown status
```

## Usage

```bash
# Enable "OEM unlocking" in "Developer options"
# Clone and install https://github.com/bkerler/edl
# Reboot into edl
$ adb reboot edl
# Backup the stock abl
$ python3 edl r abl_a stock/abl_a.img --loader prog_ufs_firehose_sm8650_ddr.elf
$ python3 edl r abl_b stock/abl_b.img --loader prog_ufs_firehose_sm8650_ddr.elf
# Flash the eng abl
$ python3 edl w abl_a eng/abl.img --loader prog_ufs_firehose_sm8650_ddr.elf
$ python3 edl w abl_b eng/abl.img --loader prog_ufs_firehose_sm8650_ddr.elf
# Reboot into fastboot & unlock the bootloader
$ python3 edl reset --loader prog_ufs_firehose_sm8650_ddr.elf
$ adb reboot bootloader
$ fastboot flashing unlock
```
