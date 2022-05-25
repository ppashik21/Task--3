# Task 3 - LVM

1. Создать 4 файла размером 1Гб каждый, создать loopback устройства из файлов при помощи losetup.    

   sudo truncate -s 1G File    
   sudo losetup /dev/loop2X File

2. Создать физические разделы на этих устройствах при помощи pvcreate. Создать volume group из первых двух девайсов. На ней создать logical volume при помощи lvcreate.     
   sudo pvcreate /dev/loop21 /dev/loop22 /dev/loop23 /dev/loop24    
   sudo vgcreate vg-01 /dev/loop21 /dev/loop22    
   sudo lvcreate -L 1,99G -n lv-01 vg-01    

4. Создать файловую систему при помощи mkfs.ext3, подмонтировать её, посмотреть какой размер.    

5. Добавить оставшиеся два  устройства в группу. Изменить размер логического тома, затем размер файловой системы. Проверить размер при помощи df. В качестве результата сделать два скриншота команд.    

