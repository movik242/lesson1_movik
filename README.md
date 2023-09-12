# lesson1_movik
В рамках выполнения домашнего задания, буду обновлять ядро ubuntu desktop 20.04 LTS
```
uname -a
```
Вывод команды
```
Linux movik 5.15.0-67-generic #74~20.04.1-Ubuntu SMP Wed Feb 22 14:52:34 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
```
# **Настройка АРМ**
Скачиваем 4 файла
```
wget https://kernel.ubuntu.com/~kernel-ppa/mainline/daily/current/amd64/linux-headers-6.6.0-060600rc1daily20230911-generic_6.6.0-060600rc1daily20230911.202309110200_amd64.deb
```
```
wget https://kernel.ubuntu.com/~kernel-ppa/mainline/daily/current/amd64/linux-headers-6.6.0-060600rc1daily20230911_6.6.0-060600rc1daily20230911.202309110200_all.deb
```
```
wget https://kernel.ubuntu.com/~kernel-ppa/mainline/daily/current/amd64/linux-image-unsigned-6.6.0-060600rc1daily20230911-generic_6.6.0-060600rc1daily20230911.202309110200_amd64.deb
```
```
wget https://kernel.ubuntu.com/~kernel-ppa/mainline/daily/current/amd64/linux-modules-6.6.0-060600rc1daily20230911-generic_6.6.0-060600rc1daily20230911.202309110200_amd64.deb
```
# **Kernel update**
Запускаем установку
```
sudo dpkg -i linux-headers* linux-image* linux-modules*
```
После выполнения команды, требуется установить gdebi
```
sudo apt install gdebi
```
С помощью gdebi установите ядро
```
sudo gdebi linux-headers*.deb linux-image-*.deb linux-modules-*.deb
```
Далее обновляем загрузчик
```
sudo update-grub
```
Перезагружаем виртуальную машину:
```
sudo reboot
```

После перезагрузки виртуальной машины проверяем обновилось ли ядро

```
uname -a
```
Вывод команды
Linux movik 6.5.0-060500daily20230904-generic #202309032200 SMP PREEMPT_DYNAMIC Mon Sep  4 02:08:41 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
