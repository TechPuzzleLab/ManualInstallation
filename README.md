# Manual Installation
Manual Installation for Windows

### How to do it?

Certainly, here's a concise guide to installing Windows using Command Prompt (CMD):

1. **Prepare a Bootable USB:**
   - Use a tool like Rufus to create a bootable USB drive with the Windows installation files.

2. **Boot from USB (If necessary):**

   *Not for VMs*
   - Insert the USB into your computer.
   - Restart your computer and enter the BIOS/UEFI settings.
   - Set the USB as the primary boot device.

4. **Access Command Prompt:**
   - During Windows installation, press `Shift` + `F10` to open Command Prompt.

5. **Diskpart**
   - Use these commands
     
     
    ```
    Diskpart
    ```
    Once Diskpart is launched:
    ```
    Sel disk 0
    ```
    Then:
   ```
    Convert gpt
    ```
   Once/After Converted:
    ```
    Create part efi size=500
    ```
    After Partition Is Created:
   ```
    Format fs=fat32 quick
    ```
   Use this command to assign that partition to:
    ```
    Assign letter w
    ```
    After that, we can now make the C drive
   ```
    Create part primary
    ```
   Create a partition again
   ```
    Create part primary
    ```
   Again, format it, but in a different type
   ```
    Format fs=ntfs quick
    ```
   Assign it as
    ```
    Assign letter c
    ```
    After that:
    ```
    exit
    ```

6. **Install Windows (By Dism)**

 - Type `CD /d D:\sources`
 - Then Dism /apply-image /imagefile:install.wim /index:1 /applydir:C:\
 - If you want to get info of the WIM file, type `Dism /get-wiminfo /imagefile:install.wim`
 - It will take time to apply the image from the wim file/s to C

7. **Bcdboot**
   -Use this command
   ```
   Bcdboot C:\Windows /s W:
   ```
8. **Reboot**
   - Type `Wpeutil reboot` to reboot/restart your PC
  

That's all for today :) 
   Comment what you want to suggest.
