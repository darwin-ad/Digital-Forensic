# Experiment 01: Evidence Acquisition Using AccessData FTK Imager

## Objective
To acquire and analyze forensic evidence (volatile and non-volatile memory) using FTK Imager.

## Tools Used
- FTK Imager (Portable / Installed)
- USB Pen Drive / HDD (for portable version)
- Write Blocker

## Procedure

### Acquiring Volatile Memory
1. Open **FTK Imager** → Click **Capture Memory**.
2. Options:
   - **Include Pagefile (pagefile.sys):** Stores additional volatile data.
   - **AD1 file option:** Creates an FTK-specific image.
3. Click **Capture Memory** → A `.mem` file is generated.

---

### Acquiring Non-Volatile Memory (Disk Image)
1. Open **FTK Imager** → Select **Create Disk Image**.
2. Choose source (Physical drive, Logical drive, Image file, Folder/CD).
3. Use **Write Blocker** for integrity.
4. Select image format:
   - Raw (dd)
   - SMART
   - E01
   - AFF/AFF4
5. Enter **Case Details** and set **Destination**.
6. Enable **Verify Image** for hash validation.
7. Click **Start** → Acquisition begins.

---

## Result
- Captured volatile memory in `.mem` format.
- Acquired non-volatile disk image (Raw/E01/SMART/AFF).
- Verified hash values and generated log.

## Conclusion
FTK Imager allows secure acquisition of volatile and non-volatile memory with integrity maintained.
