# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vagrant.plugins = ["vagrant-reload", "vagrant-scp"]

  config.vm.define "sample-box" do |sample_box|
    sample_box.vm.box = "centos/7"
    sample_box.vm.box_version = "2004.01"
    sample_box.vm.hostname = "sample-box"

    sample_box.vm.provider "libvirt" do |v, override|
      override.vagrant.plugins = config.vagrant.plugins + ["vagrant-libvirt"]
      override.vm.box_download_checksum_type = "sha256"
      override.vm.box_download_checksum = "48e14597e88a0663b1748ac2239de6fea5e9976687f5c57b1ba2480612a0b154"
      v.cpus = "2"
      v.cputopology sockets: "1", cores: "2", threads: "1"
      v.memory = "2048"
      v.disk_bus = "virtio"
      v.nic_model_type = "virtio-net-pci"
      v.nested = false
      v.cpu_mode = "host-model"
      v.cpu_fallback = "allow"
      v.graphics_type = "none"
      v.kvm_hidden = "false"
      v.machine_type = "pc-i440fx-2.11"
      v.machine_arch = "x86_64"
      v.autostart = false
    end

    sample_box.vm.provider "virtualbox" do |v, override|
      override.vagrant.plugins = config.vagrant.plugins + ["vagrant-vbguest"]
      override.vbguest.auto_update = false
      override.vm.box_download_checksum_type = "sha256"
      override.vm.box_download_checksum = "7e83943defcb5c4e9bebbe4184cce4585c82805a15e936b01b1e893b63dee2c5"
      override.vm.network "private_network", type: "dhcp"
      v.name = "sample-box"
      v.gui = false
      v.cpus = "2"
      v.memory = "2048"
      v.linked_clone = true
      v.customize ['modifyvm', :id, '--graphicscontroller', 'vmsvga']
      v.customize ['modifyvm', :id, '--audio', 'none']
    end

    sample_box.vm.provider "hyperv" do |v, override|
      override.vagrant.plugins = config.vagrant.plugins + ["vagrant-vbguest"]
      override.vbguest.auto_update = false
      override.vm.box_download_checksum_type = "sha256"
      override.vm.box_download_checksum = "51bb0495a2c01f25ed511ab02608d05c868285d17372be4efedd798f9ac1c81f"
      v.maxmemory = "2048"
      v.cpus = "2"
      v.memory = "2048"
    end

    sample_box.vm.synced_folder ".", "/vagrant", type: "rsync", rsync__exclude: ['.git/']
  end
end
