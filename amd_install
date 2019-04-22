#!/bin/bash
#Script for the easy installation of AMD Drivers on HiveOS/Ubuntu based OS
#Script By CryptoLuigi (Michael Ruperto)
#Date: 2019-04-21
#Updated: 2019-04-22

systemctl stop hivex
miner stop

echo
#mkdir /hive-driver/pack/
cd /hive-drivers-pack/
echo "Please note Drivers 18.4 and greater require an OS upgrade"
PS3='Please enter your choice Drivers: '
options=("16.40-348864" "16.60-379184" "17.10-429170" "17.10-450821" "17.30-458935" "17.40-492261" "17.50-511655" "18.10-572953" "18.20-606296-18.04" "18.40-697810-ubuntu-18.04" "18.50-725072-ubuntu-18.04" "Quit")
select opt in "${options[@]}"
do
case $opt in
    "16.40-348864")
        wget http://download.hiveos.farm/drivers/amdgpu-pro-16.40-348864.tar.xz
        version="16.40-348864";break
    ;;
    "16.60-379184")
		wget http://download.hiveos.farm/drivers/amdgpu-pro-16.60-379184.tar.xz
        version="16.60-379184";break
    ;;
	"17.10-429170")
        wget http://download.hiveos.farm/drivers/amdgpu-pro-17.10-429170.tar.xz
        version="17.10-429170";break
    ;;
    "17.10-450821")
        wget http://download.hiveos.farm/drivers/amdgpu-pro-17.10-450821.tar.xz
        version="17.10-450821";break
    ;;
    "17.30-458935")
		wget http://download.hiveos.farm/drivers/amdgpu-pro-17.30-458935.tar.xz
        version="17.30-458935";break
    ;;
    "17.40-492261")
		wget http://download.hiveos.farm/drivers/amdgpu-pro-17.40-492261.tar.xz
        version="17.40-492261";break
    ;;
    "17.50-511655")
		wget http://download.hiveos.farm/drivers/amdgpu-pro-17.50-511655.tar.xz
        version="17.50-511655";break
    ;;
    "18.10-572953")
		wget http://download.hiveos.farm/drivers/amdgpu-pro-18.10-572953.tar.xz
        version="18.10-572953";break
    ;;
    "18.20-606296-18.04")
		wget http://download.hiveos.farm/drivers/amdgpu-pro-18.20-606296-18.04.tar.xz
        version="18.20-606296-18.04";break
    ;;
    "18.40-697810-ubuntu-18.04")
		wget http://download.hiveos.farm/drivers/amdgpu-pro-18.40-697810-ubuntu-18.04.tar.xz
        version="18.40-697810-ubuntu-18.04";break
    ;;
    "18.50-725072-ubuntu-18.04")
		wget http://download.hiveos.farm/drivers/amdgpu-pro-18.50-725072-ubuntu-18.04.tar.xz
        version="18.50-725072-ubuntu-18.04";break
    ;;
    "Quit")
		exit
        break
    ;;
    *)
        echo "Invalid option $REPLY"
    ;;
    esac
done

echo
read -p "Do you want have RX4xx/RX5xx?(y/n)" -n 1 -r
if [[ $REPLY =~ ^[Yy]$ ]]; then
    tar -Jxvf amdgpu-pro-$version.tar.xz
    echo
    read -p "Do you want remove current AMD Drivers?(y/n)" -n 1 -r
    if [[ $REPLY =~ ^[Yy]$ ]]; then
		/usr/bin/amdgpu-pro-uninstall
		apt-get remove vulkan-amdgpu-pro*
	fi
	cd amdgpu-pro-$version
    apt-get -f install
    ./amdgpu-pro-install --opencl=legacy -y
    dpkg -l amdgpu-pro
    exit
fi

tar -Jxvf amdgpu-pro-$version.tar.xz
cd amdgpu-pro-$version
./amdgpu-pro-install -y
dpkg -l amdgpu-pro
