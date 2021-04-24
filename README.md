# emmm
The hack is no longer needed. No such problem on 27.20.100.9466|6.1.21-143957

# VBox-IntelGraphic-CrashWorkaround
Annoying

If your Virtualbox crashes when booting a Windows guest that installed guest additions and  turned on Hardware Graphic Acceleration, then this doc may help you.

How to check if this is the problem.\
&nbsp;First switch to the log panel by clicking the menu button on the right side of your windows guest entry.\
&nbsp;Swith to this log "VboxHardening.log".\
&nbsp;Scroll to the last to view the newest log.\
&nbsp;Find out if there's anything like or related to "igdumdim64.dll" or others that indicate some certification validation is failed if you understand.

If is, then you can try the workaround.\
&nbsp;First find out which driver folder your system is loading intel graphic drivers from. (You can do by viewing the detailed file information of your graphic driver in Device Manager.)\
&nbsp;Find the following driver components/dll.\
&nbsp;&nbsp;igc64.dll\
&nbsp;&nbsp;igd9dxva64.dll\
&nbsp;&nbsp;igdgmm64.dll\
&nbsp;&nbsp;igdumdim64.dll\
&nbsp;Copy these to a folder.\
&nbsp;Download the provided tool.\
&nbsp;Use the tool on them (Usage in its website)\
&nbsp;Reboot to Windows Recovery Env or Any PE System you like and replace the "doomed" files with your modified files.(Make backups!!!)\
&nbsp;Reboot to normal system and start the windows guest to see if this fix the problem.

It looks like Intel's new certificate is somehow confusing VirtualBox (Although VB's some code are specially reworked to fix this a century ago).\
And this only happens near the new general driver like 9077..

I already posted a thread on intel community but they say they can't replicate....Quitly interesting....\
https://community.intel.com/t5/Graphics/Some-driver-components-rejected-by-Virtualbox-with-HA-graphic/m-p/1237090#M92395

Haven't post this on Virtualbox's forum yet....

You don't need to worry that windows finds the modified files broken,actually they are still properly verified by security catalog (so VB can treat them as normal).\

Tool > https://www.fluxbytes.com/software-releases/fileunsigner-v1-0/


#At the end, if you have better solution, pls tell me. If you got this problem too, pls consider star this so I can know that this is happening to others too.
