# Manual Installation
Manual Installation for Windows

### How to do it?

Certainly, here's a concise guide to install Windows using Command Prompt (CMD):

1. **Prepare a Bootable USB:**
   - Use a tool like Rufus to create a bootable USB drive with the Windows installation files.

2. **Boot from USB (If necessary):**

   *Not for VMs*
   - Insert the USB into your computer.
   - Restart your computer and enter the BIOS/UEFI settings.
   - Set the USB as the primary boot device.

4. **Access Command Prompt:**
   - During Windows installation, press `Shift` + `F10` to open Command Prompt.

5. **Diskpart:**
   - Type `diskpart` and press Enter.
   - Use the following commands:
     - `list disk`: Display available disks.
     - `select disk X` (replace X with the disk number of your target drive).
     - `clean`: Erase the data on the selected disk.
     - `create partition primary`: Create a primary partition.
     - `select partition 1`: Select the created partition.
     - `format fs=ntfs quick`: Format the partition as NTFS.
     - `active`: Set the partition as active.
     - `exit`: Exit Diskpart.

6. **Apply the Windows Image:**
   - Type `dism /apply-image /imagefile:X:\sources\install.wim /index:1 /applydir:Y:\` (replace X and Y with your actual drive letters).

7. **Boot Configuration Data (BCD):**
   - Type `bcdboot Y:\Windows /s X:` (replace X and Y with your actual drive letters).

8. **Complete Setup:**
   - Close the Command Prompt and proceed with the on-screen instructions to complete the Windows installation.

Ensure you replace X and Y with the appropriate drive letters based on your system configuration.
