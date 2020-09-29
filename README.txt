sudo apt-get install qemu-system qemu-utils python3 python3-pip

sudo usermod -aG kvm $(whoami) # && reboot

#    -drive id=SystemDisk,if=none,file=$HOME/Data/MacOsKvmSystemDisk/SystemDisk.qcow2 \
#    -device ide-hd,bus=sata.4,drive=SystemDisk \

# make sure it's really released the virt engine
systemctl stop virtualbox.service 


./jumpstart.sh --catalina

qemu-img create -f qcow2 ~/KvmMachines/MacOsKvmSystemDisk/SystemDisk.qcow2 128G

./basic.sh

# 1/ format the 128G disk in disk utility

# 2/ install MacOS

