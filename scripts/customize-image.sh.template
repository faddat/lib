#!/bin/bash

# arguments: $RELEASE $FAMILY $BOARD $BUILD_DESKTOP
#
# This is the image customization script
#
# NOTE: It is copied to /tmp directory inside the image
# and executed there inside chroot environment
# so don't reference any files that are not already installed

RELEASE=$1
FAMILY=$2
BOARD=$3
BUILD_DESKTOP=$4

case $RELEASE in
	wheezy)
	# your code here
	;;
	jessie)
	curl -s https://packagecloud.io/install/repositories/Hypriot/Schatzkiste/script.deb.sh | bash
	apt update
	apt upgrade -y
	apt install -y docker-hypriot
	curl -L https://raw.githubusercontent.com/dilgerma/weave/rpi-latest-release/weave -o /usr/local/bin/weave
	chmod +x /usr/local/bin/weave
	curl -L https://raw.githubusercontent.com/dilgerma/scope/latest-rpi-release/scope -o /usr/local/bin/scope
	chmod +x /usr/local/bin/scope
	wget -O /etc/systemd/system/consul-onboot.service https://gist.githubusercontent.com/faddat/d143c53cbebba481f9159623b4472d1a/raw/79d7f89862f44d00f9a424b91489b72c77d1bf78/consul-onboot.service
	wget -O /etc/systemd/system/nomad-onboot.service https://gist.githubusercontent.com/faddat/d143c53cbebba481f9159623b4472d1a/raw/79d7f89862f44d00f9a424b91489b72c77d1bf78/nomad.service
	wget -O /usr/bin/consul-onboot https://gist.githubusercontent.com/faddat/d143c53cbebba481f9159623b4472d1a/raw/79d7f89862f44d00f9a424b91489b72c77d1bf78/consul-onboot
	wget -O /usr/bin/nomad-onboot https://gist.githubusercontent.com/faddat/d143c53cbebba481f9159623b4472d1a/raw/79d7f89862f44d00f9a424b91489b72c77d1bf78/nomad-onboot
	;;
	trusty)
	# your code here
	;;
	xenial)
	wget -O /usr/bin/docker https://master.dockerproject.org/linux/arm/docker
	curl -s https://packagecloud.io/install/repositories/Hypriot/Schatzkiste/script.deb.sh | bash
	apt update
	apt upgrade -y
	apt install -y docker
	chmod a+x /usr/bin/docker
	curl -L https://raw.githubusercontent.com/dilgerma/weave/rpi-latest-release/weave -o /usr/local/bin/weave
	chmod +x /usr/local/bin/weave
	curl -L https://raw.githubusercontent.com/dilgerma/scope/latest-rpi-release/scope -o /usr/local/bin/scope
	chmod +x /usr/local/bin/scope
	wget -O /etc/systemd/system/consul-onboot.service https://gist.githubusercontent.com/faddat/d143c53cbebba481f9159623b4472d1a/raw/79d7f89862f44d00f9a424b91489b72c77d1bf78/consul-onboot.service
	wget -O /etc/systemd/system/nomad-onboot.service https://gist.githubusercontent.com/faddat/d143c53cbebba481f9159623b4472d1a/raw/79d7f89862f44d00f9a424b91489b72c77d1bf78/nomad.service
	wget -O /usr/bin/consul-onboot https://gist.githubusercontent.com/faddat/d143c53cbebba481f9159623b4472d1a/raw/79d7f89862f44d00f9a424b91489b72c77d1bf78/consul-onboot
	wget -O /usr/bin/nomad-onboot https://gist.githubusercontent.com/faddat/d143c53cbebba481f9159623b4472d1a/raw/79d7f89862f44d00f9a424b91489b72c77d1bf78/nomad-onboot
	;;
esac
