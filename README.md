<p align="center">
  <a href="https://www.betterthanadventure.net/" target="_blank">
    <img alt="Minecraft Better Than Adventure and X Minecraft Launcher Logo" width="250" src="readme-mat/logos.png">
  </a>
</p>

<p align="center">
  <h1 align="center">Better Than Adventure <br> for X Minecraft Launcher</h1>
</p>

<p align="center">
  <img alt="Screenshot of Minecraft BTA mod working in XMCL" width="1000" src="readme-mat/main.png">
</p>

This repo contains files and instructions on getting [Better Than Adventure](https://www.betterthanadventure.net/) (both regular as well as Babric version for modding) to work on [X Minecraft Launcher (XMCL)](https://xmcl.app).

## Table of Contents

* [Instructions](#instructions)
* [Adding New Versions](#adding-new-versions)
* [Credits & Legal Notice](#credits--legal-notice)

## Instructions

### Import the client json
1. Download the zip file from [release](https://github.com/JiayuanWen/bta-xmcl-instance/releases) and save it somewhere temporary.
1. Launch XMCL, open the "Store Location" folder (where your instances, libraries, etc resides) from your XMCL Settings page:
    ![XMCL Store Location show button](readme-mat/instruction-storelocation.png)
1. Open the zip you downloaded with any archive utility and extract the `versions/` folder to the "Store Location" folder you opened. If prompted to "Write into" existing folder of same name, accecpt it.
> [!IMPORTANT] 
> Make sure the arcive utility you use extracts preserves the folder struture, which means the whole `versions/` folder with the `bta-*/` and `bta-*-babric/` sub-folders inside. If not, configure it to do so. Or you can just drag and drop the `versions/` folder. 

### Install Java 17 (Skip if you have it already)
Better Than Adventure uses Java 17 instead of Java 8. 

Go to the site below for installer and runtime archive download links, install instructions are also included. \
https://adoptium.net/temurin/releases?version=17&os=any&arch=any

### Create the instance
1. Create a new instance:
    * For `Minecraft` section, click on the bug icon, then search & pick `b1.7.3`\
      ![](readme-mat/instruction-pickversion1.png)\
      \
      ![](readme-mat/instruction-pickversion2.png)
    * For `Local Version` section at the very bottom, choose `bta-<version you imported>` (ex. `bta-7.3_04`) 
> [!WARNING] 
> Do NOT choose the `-babric` version just yet. XMCL need the `bta-<version>` selected to install necessary files first.
    * For `JavaLocation`, choose `17.0.x` (ex. `17.0.17`)

1. Once the instance is created, select it if not already, click on the gear icon at the top-right corner of launcher:
    ![](readme-mat/instruction-editinstance.png)
1. On the right side, find `JVM Options` field, and add in the following JVM options:
    ```
    -XX:+UseG1GC -Dsun.rmi.dgc.server.gcInterval=2147483646 -XX:+UnlockExperimentalVMOptions -XX:G1NewSizePercent=20 -XX:G1ReservePercent=20 -XX:MaxGCPauseMillis=50 -XX:G1HeapRegionSize=32M
    ```
1. Press the blue `INSTALL` button, let XMCL install everything.
1. You are done! Launch the instance and enjoy. If you want modding support, keep reading.

### Modding support with Babric
> [!IMPORTANT] 
> Make sure you followed the previous section to install the regular version first. Otherwise the steps below will not work.
1. Go back to the instance's settings page if not already.
1. On the left side at the bottom of the page, find `Local Version` and select `bta-<version-babric-<babric version>`(ex. `bta-7.3_04-babric-0.15.6`).
1. XMCL will prompt "Your modification is unsaved" at the bottom middle, click Save to save changes.
1. Click `INSTALL` to let XMCL install additional libraries files.

## Adding New Versions
(WIP)

## Credits & Legal Notice

<small>
<h3>Better Than Adventure by Mak and jonkadelic. Fabric intergration (Babric) from Turnip-Labs</h3>
This project makes use of, or provides a launcher integration for, the mod [Better Than Adventure](https://www.betterthanadventure.net/) by Mak and [jonkadelic](https://bta.miraheze.org/wiki/User:Jonkadelic) and [Fabric Integration (Babric)](https://github.com/Turnip-Labs/bta-fabric-instance-repo) from [Turnip-Labs](https://github.com/Turnip-Labs). 

This project does *not* itself distribute any files from stated parties. All downloads performed by the project are directly linked to perspective official sources and repository:  
* Better Than Adventure jarmods and libraries: https://github.com/Turnip-Labs/bta-fabric-instance-repo/releases
* Fabric integration (Babric): https://github.com/Turnip-Labs/bta-fabric-instance-repo/releases 

I am not responsible for the contents of the linked mod or any subsequent modifications by the original authors.

<br>
<h3>Minecraft® from Microsoft Corporation</h3>
[Minecraft®](https://www.minecraft.net/) is a trademark of [Microsoft Corporation](https://www.microsoft.com/).

This project is not affiliated with, endorsed by, or in any way officially connected with [Microsoft Corporation or Mojang Synergies AB](https://www.minecraft.net/). All product names, logos, and brands are property of their respective owners.

<br>
<h3>X Minecraft Launcher</h3>
This project integrates with [X Minecraft Launcher (XMCL)](https://github.com/Voxelum/x-minecraft-launcher), an open-source Minecraft launcher released under the [MIT License](https://github.com/Voxelum/x-minecraft-launcher/blob/master/LICENSE). 
</small>