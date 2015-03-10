# vim:ft=ruby

VAGRANTFILE_API_VERSION = "2"

$SnortInstall = <<SCRIPT
apt-get update
apt-get upgrade -y
apt-get install -y build-essential \
                   gdb valgrind \
                   bison flex \
                   make \
                   autoconf \
                   automake \
                   libtool \
                   pkg-config \
                   libpcap-dev \
                   libpcre3-dev \
                   zlib1g-dev \
                   libdumbnet-dev \
                   libssl-dev \
                   liblzma-dev \
                   texlive \
                   ethtool

wget https://www.snort.org/downloads/snort/snort-2.9.7.0.tar.gz
tar xzf snort-2.9.7.0.tar.gz
pushd snort-2.9.7.0/
## /home/vagrant/snort-2.9.7

wget https://www.snort.org/downloads/snort/daq-2.0.4.tar.gz
tar xzf daq-2.0.4.tar.gz
pushd daq-2.0.4/
## /home/vagrant/snort-2.9.7/daq-2.0.4

# build daq
./configure
make -j 4 2>&1 | tee make.out
sudo make install &> make-install.out
sudo ldconfig # Just incase
popd
## /home/vagrant/snort-2.9.7/

# build Snort
./configure --enable-sourcefire --enable-file-inspect
make -j 4 2>&1 | tee make.out
sudo make install &> make-install.out

# Check snort works
snort -V
SCRIPT

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-juju-vagrant-disk1.box"
  config.vm.provision "shell", inline: $SnortInstall 
end
