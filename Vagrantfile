VAGRANTFILE_API_VERSION = 2

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "bento/ubuntu-16.04"
    config.vm.network "private_network", ip: "192.168.33.10"
    # need install vagrant-hostsupdater
    config.vm.hostname = "dev-rnita.me"

    config.vm.synced_folder "./codes", "/home/vagrant/codes"
  
    #Fix for Ansible bug resulting in an encoding error
    ENV['PYTHONIOENCODING'] = "utf-8"
    
    # Run ansible from the Vagrant VM
    config.vm.provision "ansible_local" do |ansible|
        ansible.install = true
        ansible.playbook = "provisioning/playbook.yml"
        ansible.inventory_path = "provisioning/hosts"
        ansible.limit = 'all'
    end

    config.vm.provider 'virtualbox' do |vb|
        vb.customize ['modifyvm', :id, '--cableconnected1', 'on']
    end

    config.vm.network :forwarded_port, host: 3000, guest: 3000
    config.vm.network :forwarded_port, host: 4200, guest: 4200
    config.vm.network :forwarded_port, host: 3999, guest: 3999
    config.vm.post_up_message = "Provisioning is done! :)"
end
