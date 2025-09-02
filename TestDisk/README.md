# Experiment 02: Recover Deleted or Damaged Files Using TestDisk

## Objective
To recover deleted or corrupted partitions/files from storage devices using TestDisk.

## Tools Used
- TestDisk (CLI tool)
- Storage device with missing/corrupted partition

## Procedure
1. **Launch TestDisk** → Select target drive.
2. **Partition Table Detection** → Auto-detects type.
3. **Analyze Current Structure** → Check for errors/missing partitions.
4. **Quick Search** → Finds lost partitions.
5. **Deeper Search** → Scans cylinders for FAT/NTFS/ext backups.
6. **Partition Selection**:
   - Mark valid partition as Primary/Logical.
   - Mark damaged partitions as Deleted (D).
7. **Partition Table Recovery** → Save with **Write**.
8. **NTFS Boot Sector Recovery**:
   - Use **Backup BS** if primary boot sector is damaged.
   - Confirm copy of backup → Boot sector repaired.

---

## Result
- Successfully detected and recovered missing partitions.
- Restored NTFS boot sector from backup.
- Recovered files and verified integrity.

## Conclusion
TestDisk efficiently recovers lost partitions and repairs corrupted file systems, ensuring access to critical data.
