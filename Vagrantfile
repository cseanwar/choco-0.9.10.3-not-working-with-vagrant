Vagrant.configure(2) do |config|
  # you first need to build the base image with:
  # git clone https://github.com/joefitzgerald/packer-windows
  # cd packer-windows
  # packer build windows_10.json
  # # this will take ages so leave it running over night...
  # vagrant box add --name windows_10 windows_10_virtualbox.box
  # cd ..
  # then finally you vagrant up this vagrant environment. 
  config.vm.box = "windows_10"
  config.vm.provider "virtualbox" do |vb|
    vb.linked_clone = true
    vb.memory = 1024
    vb.customize ["modifyvm", :id, "--vram", 64]
    vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
    vb.customize ["modifyvm", :id, "--draganddrop", "bidirectional"]
  end
  #config.vm.provision "shell", path: "chocolatey-0.9.9.12.ps1", name: "Install Chocolatey"
  config.vm.provision "shell", path: "chocolatey-0.9.10.3.ps1", name: "Install Chocolatey"
  config.vm.provision "shell", inline: "choco install -y notepad2", name: "Install Notepad2"
end