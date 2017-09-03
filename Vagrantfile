# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrant setup for minecraft servers. For use with virtualbox

# If you plan on making your server accessible on your network, you may need
# to change this device name (works for macbooks)
$BRIDGE_DEVICE = 'en0: Wi-Fi (AirPort)'

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.provision :shell, :path => "minecraft_bootstrap"

  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
  end

  # This will make minecraft accessible on localhost port 25565
  config.vm.network "forwarded_port", guest: 25565, host: 25565

  # If you plan on having others join your minecraft server, comment out the
  # line above and uncomment this line, which will give your server a private
  # IP address on your local network. You may need to adjust your bridge
  # device, which is set at the top of this script.

  # See this link for more information:
  #   http://docs-v1.vagrantup.com/v1/docs/bridged_networking.html

  #config.vm.network "public_network", :bridge => "en0: Wi-Fi (AirPort)"

  config.vm.hostname = "minecraft.local"
end
