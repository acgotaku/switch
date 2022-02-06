# switch

本手册基于自己的安装实践，仅供参考。

## 1. 准备工作

1. 可以软破的 Switch 机器

   Switch 破解分为软件破解和硬件破解。硬件破解技术难度高，不在讨论范围内。软件破解需要 2018 年 6 月之前出厂的机器，具体能破解的序列号请参考下图：
   <img alt="可软破的switch机型序列号" src="./images/code.png" width="320"></img>

2. [RCM 注入器 v5](https://www.xkitcn.com/rcmloader/)，某宝上有售，自行搜索

3. SD 卡，三星 EVO Plus 任天堂官方推荐

   关于 SD 卡的文件格式，推荐 FAT32，exFAT 虽然可以支持 4GB 以上大文件，但是并不稳定。详细可以参考[SD Preparation](https://nh-server.github.io/switch-guide/user_guide/sysnand/sd_preparation/)

## 2. 准备 SD 卡内容

软件清单：

1. [Atmosphère](https://github.com/Atmosphere-NX/Atmosphere/releases/latest) Switch 自定义操作系统

   下载 `atmosphere-xxx-master-173d5c2d3+hbl-xxx+hbmenu-xxx.zip` 并解压到 SD 卡根目录。下载 `fusee.bin` 复制到 `/bootloader/payloads`。

2. [hekate](https://github.com/CTCaer/hekate/releases/latest) Switch 引导文件

   下载 `hekate_ctcaer_xxx_Nyx_xxx.zip` 并解压到 SD 卡根目录。 这里有一个 `hekate_ctcaer_xxx.bin` 文件，注入器要使用。  
   把 RCM 注入器插入电脑，会识别为 U 盘，打开\ATMOSPHERE_HEKATE 文件夹，把刚才的 `hekate_ctcaer_xxx.bin` 复制为 payload.bin，然后拔掉。

3. [Signature Patches](https://github.com/ITotalJustice/patches/releases/latest) 这个补丁可以支持安装非官方签名的游戏文件

   下载 `SigPatches.zip` 并解压到 SD 卡根目录。
   Atmosphère 系统有两个引导方案，默认的是 fss0 引导，如果想使用这个补丁必须使用 fusee 引导。

4. [Lockpick_RCM](https://github.com/shchmue/Lockpick_RCM/releases/latest) 这个软件可以获取本机密钥，在处理 Switch 文件或者变砖修复的时候会用到，如果担心出问题最好提前备份。

   下载 `Lockpick_RCM.bin` 放到 `/bootloader/payloads` 文件夹下。 详细使用方法请看[Getting your Console's Unique Keys](https://nh-server.github.io/switch-guide/user_guide/emummc/making_emummc/#getting-your-consoles-unique-keys)

5. [JKSV](https://github.com/J-D-K/JKSV/releases/latest) 游戏存档管理软件

   下载 `JKSV.nro` 到 `/switch` 文件夹下。

6. [FTPD](https://github.com/mtheall/ftpd/releases/latest) FTP Server，方便文件传输

   下载 `ftpd.nro` 到 `/switch` 文件夹下。

7. [NxThemeInstaller](https://github.com/exelix11/SwitchThemeInjector/releases/latest) 顾名思义，主题安装器

   下载 `NXThemesInstaller.nro` 到 `/switch` 文件夹下。

8. [NX-Shell](https://github.com/joel16/NX-Shell/releases/latest) 文件管理器

   下载 `NX-Shell.nro` 到 `/switch` 文件夹下。

9. [hbappstore](https://github.com/fortheusers/hb-appstore/releases/latest) 顾名思义，软件商店

   下载 `appstore.nro`， 在 `/switch` 下创建 文件夹 `appstore`，然后把 `appstore.nro` 放入 `/switch/appstore`。
