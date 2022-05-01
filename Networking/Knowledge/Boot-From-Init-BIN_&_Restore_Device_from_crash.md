
# Fz3r0 Operations  [Networking]

![My Video](https://user-images.githubusercontent.com/94720207/165892585-b830998d-d7c5-43b4-a3ad-f71a07b9077e.gif)

### Boot from a Binary .bin or config.text & Recover from a System Crash like a Sir!

---

##### Twitter  : [@fz3r0_OPs](https://twitter.com/Fz3r0_OPs) 
##### Github  : [Fz3r0](https://github.com/fz3r0) 

---

#### Keywords: `Networking` `Routing & Switching` `CCNA` `CCNP` `Initial Settings` `Reset` `Flash`

---

### Index

- Part1: << **Boot** from a **.bin initial configuration** | `boot system` command >>
- Part2: << **Recovering from a System Crash** | Step by step recover >>

---

### The `boot system` Command 

- **Before anything!** 

    - **This technique DOES NOT reset the device to factory settings like new & shiny**
    - **This is used to tell the router/switch which IOS file to be used while booting, when there are multiple files in the flash... So, if you have only 1 file, it will be your same config!!! (not the factory or other startup config)**
    - **This can also be used when a device crash (_See the second section of this document_) 
    - **If you have a backup or another .bin with an init setup stored in you device, then you can boot from there tho ;) (but there are other better ways to init the device from factory, just click here!!!)
    - **Another good use for this crap, is to boot from another disk or service outside the device like FTP, ROM, TFTP...**

- **...OK moving on...** 

- The switch attempts to automatically boot by using information in the BOOT environment variable. 

    - If this variable is not set, the switch attempts to load and execute the first executable file it can find.

    - On Catalyst 2960 Series switches, **the image file is normally contained in a directory that has the same name as the image, but sometimes are directly in `/` **

- The IOS operating system then initializes the interfaces using the Cisco IOS commands found in the startup-config file. 
 
- **The `startup-config` file is called `config.text` and is located in `flash`.**

### Example:

- Notice that the IOS is located in root `/` (flash:/) folder, but sometimes another folder path is specified (flash:/folderabcs_122345/). 

- Use the command **`show boot`** to see what the current IOS boot file is set to:

```

Switch> enable
Switch#
Switch# show boot
BOOT path-list      : 
Config file         : flash:/config.text    <<<-------| HERE!!!!! ;) 
Private Config file : flash:/private-config.text
Enable Break        : no
Manual Boot         : no
HELPER path-list    : 
Auto upgrade        : yes
NVRAM/Config file
      buffer size:   65536
Switch#

```

- Use **`dir flash:`** to do a ls/dir on the flash 

```

Switch#dir flash:
Directory of flash:/      <<<---------| in this case is directly in /

    3  -rw-   505532849          <no date>  cat3k_caa-universalk9.16.03.02.SPA.bin  <<<-----| The IOS file name!!! :D

1539575808 bytes total (1034042959 bytes free)
Switch#

```

- Now that we know which IOS file we want to choose _(in this example there's just 1)_ we can select in and reboot from it!

- For example, if you load a new .bin and we want to reboot form that binary , just paste that file name and boot from there: 

    - **HINT: Check the path!** if there's a folder, Paste it twice :)!!! The first is the directory (without .bin) the second is the file name:
    
    - **`flash:/cat3k_caa-universalk9.16.03.02.SPA/cat3k_caa-universalk9.16.03.02.SPA.bin`**

- **HINT: But sometimes is directly in /**

    - **`flash:/cat3k_caa-universalk9.16.03.02.SPA.bin`**
        
- Shake your Boot it!:
    
    - **`boot system flash:/cat3k_caa-universalk9.16.03.02.SPA/cat3k_caa-universalk9.16.03.02.SPA.bin`** 

```

Switch(config)# boot system flash:/cat3k_caa-universalk9.16.03.02.SPA/cat3k_caa-universalk9.16.03.02.SPA.bin

```

| **Command**                      | **Definition**               |
|:--------------------------------:|:----------------------------:|
| boot system                      | The main command             |
| flash:                           | The storage device           |
| c2960-lanbasek9-mz.150-2.SE/     | The path to the file system  |
| c2960-lanbasek9-mz.150-2.SE.bin  | The IOS file name            |

--- 

### Recovering from a System Crash | Step by step recover

- The `boot loader` provides access into the switch if the operating system cannot be used because of missing or damaged system files.
 
- The `boot loader` has a command-line/shell that provides access to the files stored in flash memory.

- The trick to access that shell is easy, _(it's similar like booting another shell or BIOS on smartphone or any other device hehe)_

1. Connect a PC by console cable to the switch console port.

![image](https://user-images.githubusercontent.com/94720207/166128307-dc7dbbb9-dfd9-40a6-97c9-bcaccc6c7436.png)

3. Unplug the switch power cord. _(not allowed in all packet tracer devices, but, for example:)_

![image](https://user-images.githubusercontent.com/94720207/166128212-a954d668-bc73-4e50-8124-535cc33eb93a.png)

4. Continue pressing the Mode button until the System LED turns briefly amber and then solid green; then release the Mode button.

![image](https://user-images.githubusercontent.com/94720207/166128365-b4357dea-e673-4b02-a544-4d3575dd2edc.png)

![image](https://user-images.githubusercontent.com/94720207/166128407-256baee4-c342-4ab0-84af-68e224ccba47.png)



5. Reconnect the power cord to the switch and press and hold **within 15 seconds**, the `Mode` button while the System LED is still flashing green.
---

### References

- https://networklessons.com/cisco/ccna-routing-switching-icnd1-100-105/cisco-ios-boot-system-image-
- https://www.cisco.com/en/US/docs/switches/lan/catalyst4000/7.5/configuration/guide/boot_support_TSD_Island_of_Content_Chapter.html
---

> ![hecho en mex3 (1)mini](https://user-images.githubusercontent.com/94720207/163919294-2754caa3-c98c-4df3-b782-00703e4d3343.png)
>
> _- Hecho en México - by [Fz3r0 💀](https://github.com/Fz3r0/)_ 
>
> _"In the mist of the night you could see me come, where shadows move and Demons lie..."_ 
