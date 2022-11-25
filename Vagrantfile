Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  #config.vm.network "private_network", ip: "192.168.1.77"
  config.vm.network "public_network"
  config.vm.network "forwarded_port", guest: 6443, host: 6443
  config.vm.define 'k3s-vm' do |node|
    node.vm.hostname = 'k3s-vm.local'
    node.vm.provision "ansible" do |ansible|
      ansible.playbook = "main.yml"
    end
  end
end
