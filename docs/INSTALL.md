

[How to create a bootable installer for macOS](https://support.apple.com/en-us/HT201372)

Insert your USB Flash Drive

List file systems available for formatting.

```bash
diskutil listFilesystems
```

List the partitions of a disk.

```bash
diskutil list
```

Double check the correct Disk Identifier.

```bash
diskutil info disk1|grep Identifier
diskutil info disk2|grep Identifier
diskutil info disk3|grep Identifier
diskutil info disk4|grep Identifier
```

Set the correct Disk Identifier.

```bash
FILE_SYSTEM=JHFS+
DISK_NAME=Mojave

DISK_IDENTIFIER=disk9999
```

WARNING. WARNING.  GET THIS RIGHT OR IT WILL BE BAD.

Erase an existing disk, removing all volumes.

```bash
diskutil eraseDisk $FILE_SYSTEM $DISK_NAME $DISK_IDENTIFIER
```

Create a bootable installer.

```bash
sudo '/Applications/Install macOS Mojave.app/Contents/Resources/createinstallmedia' --volume /Volumes/$DISK_NAME
```

Eject the UBS Flash Drive

```bash
diskutil eject $DISK_IDENTIFIER
```