VAGRANTFILE_API_VERSION = 2

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "bento/ubuntu-16.04"
    config.vm.network "private_network", ip: "192.168.33.10"
    config.vm.hostname = "rnitame-dev"

    # Add any alias
    config.hostupdater.aliases = [
        "slides.dev-rnita.me",
        "owl.dev-rnita.me",
        "leafgo.dev-rnita.me"
    ]

    config.vm.synced_folder ".", "/vagrant"
    
    #Fix for Ansible bug resulting in an encoding error
    ENV['PYTHONIOENCODING'] = "utf-8"

    # Run ansible from the Vagrant VM
    config.vm.provision "ansible_local" do |ansible|
        ansible.playbook = "provisioning/playbook.yml"
        ansible.inventory = "provisioning/hosts"
        ansible.limit = 'all'
    end

    config.vm.post_up_message = "Provisioning is done! :)\n\nYou can visit #{config.hostupdater.aliases}"

end
