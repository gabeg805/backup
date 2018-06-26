# backup

## Introduction

Backup individual files/directories, multiple files/directories, and or backup
your whole filesystem.

## Usage

### Backup one or more files

```
backup -f file1 -f file2 ...
```

### Backup one or more directories

```
backup -b dir1 -b dir2 ... -d /path/to/destination
```

### Full System Backup

```
backup --system -d /path/to/destination
```

**Note:** A full system backup will exclude filesystems of type *tmpfs* and
*devtmpfs*, since those are populated at boot. The list of filesystems that will
*be backed up can be displayed with the following command:
```
df -h -x tmpfs -x devtmpfs
```

## Reference

At the end of the Arch Wiki on Rsync, it has a section on a [Snapshot
Backup](https://wiki.archlinux.org/index.php/rsync#Snapshot_backup) as well as a
section on [File System
Cloning](https://wiki.archlinux.org/index.php/rsync#File_system_cloning). This
script does a combination of both to retain as much information as possible per
snapshot.
