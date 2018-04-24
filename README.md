# Backup

## Introduction

Backup individual files/directories, multiple files/directories, and or backup
your whole filesystem.

If you reference the Arch Wiki on Rsync, at the end it has a section on a
(Snapshot Backup)[https://wiki.archlinux.org/index.php/rsync#Snapshot_backup] as
well as a section on (File System
Cloning)[https://wiki.archlinux.org/index.php/rsync#File_system_cloning]. This
script does a combination of both to retain as much information as possible per
snapshot.

## Examples

### Backup one or more files

This form of backing up will just copy the original file and append .bak to each
backup.
```
backup -f File1 File2 File3 ...
```

### Backup one or more directories

This form of backing up will copy the requested directories to the designated
destination.
```
backup -b Dir1 Dir2 Dir3 ... -d /path/to/destination
```

### Full System Backup

This will backup your entire system to the designated destination.
```
backup --system -d /path/to/destination
```

It's important to note that this will exclude various filesystems, specifically,
those of type *tmpfs* and *devtmpfs*, since those are populated at boot.

To see which directories that pertains to, run:
```
df -h -x tmpfs -x devtmpfs
```

Running the following command will display all filesystems.
```
df -h
```
