# ASRock Z390 Phantom Gaming- ITX/ac-OpenCore-Hackintosh


## 电脑配置
|规格 | 详细信息|
|:-: | :-:|
|主板型号| ASRock Z390 Phantom Gaming-ITX/ac |
|操作系统| macOS Big Sur 11.0.1（20B29） |
|处理器| 英特尔 酷睿i9 9900k |
|内存| 芝奇 16GBx2 3200Mhz C16 |
|硬盘| 西数 SN750 1T |
|显卡| XFX Radeon VII |
|显示器| 优派 VX2780-4K-ZERO |
|声卡| Realtek ALC1220 |
|网卡| 94360CS2 |

## 使用说明

### BIOS设置

- BIOS版本：~~V4.40C~~ V4.40

  - Advanced \ Chipset Configuration → Vt-d : Disabled

  - Advanced \ USB Configuration → XHCI Hand-off : Enabled

  - Advanced \ Chipset Configuration → Share Memory : 128MB（使用`Pro`机型请关闭）

  - Advanced \ Chipset Configuration → IGPU Multi-Monitor : Enabled（使用`Pro`机型请关闭）
  
  - ~~Advanced \ Advancedl Intel (R) Thunderbo1t → Thunderbolt (TM)
  Support : Enabled~~
  
  - ~~Advanced \ Advancedl Intel (R) Thunderbo1t → Thunderbolt Usb Support
 : Enabled~~
  
  - 没有的选项跳过即可
    
- ~~驱动 `TB3`接口支持热拔插教程~~
    
  - ~~详细驱动教程请参考 [华擎ASRock Z390 Phantom Gaming ITX/ac 雷电3 完美驱动 热插拔](https://fangf.cc/2020/05/19/TB3/)~~
  - ~~存在的问题：睡眠唤醒失败电脑自动重启提示`thunderbolt power on failed` （AMD 5000系列与VII睡眠唤醒失败自动重启，驱动雷电3需要放弃睡眠）~~

- `SSDT-XHC-USB.aml`定制USB `SSDT-XHC-TbtTypeC.aml`则是TypeC端口（需开机前插入）
  - 使用`SSDT-XHC-TbtTypeC.aml`时需要`ACPI`-`Delete`-`ltem1`-`Enabled`=`YES`
  
- `RadeonBoost.kext`支持`AMD 5000系列`、`VEGA56/64`、`Radeon VII`等显卡“优化”，请按需打开
  - `AMD 5000系列`请自行在`boot-args`处添加`agdpmod=pikera`
  
### `fangf`大佬的EFI
 
  - [fangf2018](https://github.com/fangf2018/ASRock-Z390-Phantom-ITX-OpenCore-Hackintosh)
  


