# nubia_sm8650_eng

## Supported models

- `sm8650_v1`

| Device (public codename) (codename)                                | Tested |
| ------------------------------------------------------------------ | ------ |
| ZTE nubia Z60 Ultra (`nx721j` `pq83a01`) (`cerro`)                 | [v]    |
| ZTE nubia Z60 Ultra Leading Edition (`nx721j` `pq83a01`) (`cerro`) | [v]    |
| ZTE nubia Red Magic 9 Pro (`nx769j`) (`tiro`)                      | [v]    |
| ZTE nubia Red Magic 9S Pro (`nx769j`) (`tiro`)                     | [v]    |

- `sm8650_v2`

| Device (public codename) (codename)        | Tested |
| ------------------------------------------ | ------ |
| ZTE nubia Pad Pro (`nt01` `pq83p02`) (`?`) | [v]    |
| ZTE nubia RedMagic Nova (`np03j`) (`?`)    | [v]    |

```
[v] = Tested and working
[x] = Not working
[?] = Unknown status
```

## Usage

> [!WARNING]
> **This guide must be followed exactly for your specific device model. Using the wrong version (`sm8650_v1` vs `sm8650_v2`) or wrong loader file can permanently brick your device. Verify your exact device model before proceeding.**

- `sm8650_v1`

<details>
<summary>Click to reveal</summary>

```bash
# Enable "OEM unlocking" in "Developer options"
# Clone and install https://github.com/bkerler/edl
# Reboot into edl
$ adb reboot edl
# Backup the stock abl
$ python3 edl r abl_a stock/abl_a.img --loader prog_ufs_firehose_sm8650_v1_ddr.elf
$ python3 edl r abl_b stock/abl_b.img --loader prog_ufs_firehose_sm8650_v1_ddr.elf
# Flash the eng abl
$ python3 edl w abl_a eng_v1/abl.img --loader prog_ufs_firehose_sm8650_v1_ddr.elf
$ python3 edl w abl_b eng_v1/abl.img --loader prog_ufs_firehose_sm8650_v1_ddr.elf
# Reboot into fastboot & unlock the bootloader
$ python3 edl reset --loader prog_ufs_firehose_sm8650_v1_ddr.elf
$ adb reboot bootloader
$ fastboot flashing unlock
```

</details>

- `sm8650_v2`

<details>
<summary>Click to reveal</summary>

```bash
# Enable "OEM unlocking" in "Developer options"
# Clone and install https://github.com/bkerler/edl
# Reboot into edl
$ adb reboot edl
# Backup the stock abl
$ python3 edl r abl_a stock/abl_a.img --loader prog_ufs_firehose_sm8650_v2_ddr.elf
$ python3 edl r abl_b stock/abl_b.img --loader prog_ufs_firehose_sm8650_v2_ddr.elf
# Flash the eng abl
$ python3 edl w abl_a eng_v2/abl.img --loader prog_ufs_firehose_sm8650_v2_ddr.elf
$ python3 edl w abl_b eng_v2/abl.img --loader prog_ufs_firehose_sm8650_v2_ddr.elf
# Reboot into fastboot & unlock the bootloader
$ python3 edl reset --loader prog_ufs_firehose_sm8650_v2_ddr.elf
$ adb reboot bootloader
$ fastboot flashing unlock
```

</details>
