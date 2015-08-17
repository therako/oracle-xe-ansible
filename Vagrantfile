Vagrant.configure(2) do |config|
  config.vm.box = "centos-6.6-x86_64"
  config.vm.box_url = "https://github.com/tommy-muehle/puppet-vagrant-boxes/releases/download/1.0.0/centos-6.6-x86_64.box"

  config.vm.provider :virtualbox do |vb|
    vb.cpus = 2
    vb.memory = 4096
  end

  config.vm.define "oracle" do |box|
    box.vm.hostname="oracle-host"
    box.vm.provision "ansible" do |ansible|
      ansible.playbook = "oracle.yml"
      # ansible.verbose = "vvv"
    end
    box.vm.network "forwarded_port", guest: 1521, host: 1521, auto_correct: true
  end
end
