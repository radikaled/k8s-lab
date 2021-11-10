Vagrant.configure("2") do |config|
  config.vm.provision :hostmanager

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end

  config.vm.box = "generic/ubuntu2010"

  config.vm.provider :libvirt do |v|
    v.cpus = 2
    v.memory = 8192                                                                                                                                                    
  end

  config.vm.define "cp" do |cp|
    cp.vm.hostname = "cp"
    cp.vm.network "private_network", ip: '10.100.0.10'
  end

  config.vm.define "worker1" do |worker1|
    worker1.vm.hostname = "worker1"
    worker1.vm.network "private_network", ip: '10.100.0.11'
  end

  config.vm.define "worker2" do |worker2|
    worker2.vm.hostname = "worker2"
    worker2.vm.network "private_network", ip: '10.100.0.12'
  end
end
