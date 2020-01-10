# Hackintosh build with ASUS Prime Z390-A and i7-9700K

i would like to thank [@dhckdgjs](https://github.com/dhckdgjs) by hepling the community and share [ this build ](https://github.com/dhckdgjs/ASUS-PRIME-Z390-A-HACKINTOSH-Clover-iGPU-with-dGPU-UHD630-RX580) with us, which is my build based on.

## changeLog
- 10/1/2020
Sidecar is not tested yet on Catalina , i will updated as soon as i test it 

## Summary
this build is tested with:
- MacOS Catalina 10.15.2
- MacOS Mojave 10.14.6

everything is working fine including:
1. AirDrop
2. Handoff
3. FaceTime
4. imessage

## Components
- M/B: ASUS PRIME Z390-A
- CPU: Intel® Core™ i7-9700 Processor
- iGPU: Intel® UHD Graphics 630
- dGPU: SAPPHIRE PULSE Radeon RX 580 8GB GDDR5
- Lan: Intel® I219V, 1 x Gigabit LAN Controller
- WiFi/Bluetooth: BCM943602CS
- Audio: Realtek® ALC S1220A 8-Channel High Definition Audio
- Storage: Samsung SSD 970 EVO Plus 500GB




## Modification and fixes
below the list of modification i made to the orginal [build ](https://github.com/dhckdgjs/ASUS-PRIME-Z390-A-HACKINTOSH-Clover-iGPU-with-dGPU-UHD630-RX580) to make it work with my components and system:

1. fix dGPU only HDMI work no DP (Display Link)  
Change SMBIOS from iMac 19,1 to iMac18,1 to make the dGPU properly with ports work

2. fix boot stuck on **AppleNVMe: Assert failed**
add the following in config.plist
```
 <key>USB</key>
        <dict>
            <key>FixOwnership</key>
            <true/>
            <key>Inject</key>
            <true/>
        </dict>
```

3. fix boot stuck on **apfs_module_start:1683**
  download  [SSDT-EC.aml](https://www.tonymacx86.com/attachments/ssdt-ec-aml.325126/) and put it in /EFI/CLOVER/ACPI/patched

4. installation stuck on when choose **Samsunge 970 EVO PLUS**
updating the firmware drive system for the Samsunge 970 EVO PLUS from  [here](https://www.samsung.com/semiconductor/minisite/ssd/download/tools/) and Write it on the USB drive and boot from it 




## Screenshots
![system_info](https://github.com/m4ary/hackintosh-Asus-Prime-Z390A_i7-9700K_RX580/blob/master/screenshots/Screen%20Shot%202020-01-10%20at%202.52.25%20PM.png)
![disk_speed](https://github.com/m4ary/hackintosh-Asus-Prime-Z390A_i7-9700K_RX580/blob/master/screenshots/DiskSpeedTest.png)



* References

https://www.tonymacx86.com/threads/solved-stuck-with-log-showing-applenvme-assert-failed.223434/
https://www.tonymacx86.com/threads/guide-usb-power-property-injection-for-sierra-and-later.222266/post-1728645
https://www.reddit.com/r/hackintosh/comments/aprsbp/970_evo_plus_hackintosh/eo7odr3/?utm_source=share&utm_medium=ios_app&utm_name=iossmf
https://github.com/dhckdgjs/ASUS-PRIME-Z390-A-HACKINTOSH-Clover-iGPU-with-dGPU-UHD630-RX580
