[[Setup|Home]]
# Hardware

geizhals [part list](https://geizhals.de/wishlists/2659082)

 | Part       | Product                           | Cost (€) |
 | ---------- | --------------------------------- | -------- |
 | Mainboard  | ASRock x570M Pro4                 | 180,70   |
 | Processor  | AMD Ryzen 5 5600X                 | 189,00   |
 | CPU Cooler | be quiet! Shadow Rock LP          | 40,89    |
 | RAM        | 4x Kingston ECC 16GB DDR4-3200    | 244,03   |
 | GPU        | Zotac GeForce GT 710 2GB GDDR3    | 56,89    |
 | USV        | be quiet! Straight Power 11 650W  | 114,35   |
 | Storage OS | Samsung SSD 980 500GB, M.2        | 49,00    |
 | Storage    | 4x Toshiba Enterprise 16TB        | 1019,96  |
 | Case       | Inter-Tech IPC 3U-30248, 3HE      | 125,89   |
 | Case Fan   | be quiet! Pure Wings 2 PWM, 120mm | 8,20     |

Total: **2.028,91 €**


CPU governor for energy consumption
cat  /sys/devices/system/cpu/cpu0/cpufreq/scaling_available_governors
cat /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor
echo "ondemand" | tee /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor

crontab -e
@reboot echo "ondemand" | tee /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor

https://medium.com/@MARatsimbazafy/journey-to-deep-learning-nvidia-gpu-passthrough-to-lxc-container-97d0bc474957
https://theorangeone.net/posts/lxc-nvidia-gpu-passthrough/
https://passbe.com/2020/gpu-nvidia-passthrough-on-proxmox-lxc-container/
dmks
dynamic module kernel support

https://wiki.archlinux.org/title/CPU_frequency_scaling#Scaling_drivers

apt install cpufrequtils
cpufreq-info

https://forum.endeavouros.com/t/how-to-use-amd-p-state-in-linux/25247