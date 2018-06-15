from ubuntu:18.04

maintainer William Law <wlaw@stanford.edu>

env DEBIAN_FRONTEND noninteractive

# Enable "extra" users, this makes
# overlaying our passwd/shadow/group content easier
#seems to already be there
#run echo "deb http://archive.ubuntu.com/ubuntu bionic main universe" >> /etc/apt/sources.list
run apt-get update
run apt-get install -y apt-utils 
run apt-get install -y libnss-extrausers 
run sed -i '/^\(passwd\|group\|shadow\):/{ s/$/ extrausers/; }' /etc/nsswitch.conf

# Install samba!
run apt-get install -y samba zfsutils-linux 

# Make directories for shared path
run mkdir -p /mnt/data

# Add user management tool
add docker-smb-user /usr/local/bin/
