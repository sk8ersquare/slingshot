# -*- mode: ruby -*-
# vi: set ft=ruby :

time = Time.new

Vagrant.configure("2") do |config|
	config.vagrant.plugins = "vagrant-reload"

    config.vm.define "slingshot" do |machine|
        `(tar -C labs/slingshot -czf slingshot.tar.gz .)`

        commit = `git log --format="%H" -n 1`
        version = "#{time.year}.#{time.month}.#{commit[0..6]}"

        machine.vm.box = "bento/ubuntu-22.04-arm64"
        machine.vm.hostname = "slingshot"

        config.vm.provider "parallels" do |prl|
            prl.check_guest_tools = false
	    prl.name = "slingshot"
	    prl.memory = 2048
            prl.cpus = 2
        end

        machine.vm.provision "shell",
            inline: "sed -i 's/^DISTRIB_DESCRIPTION=.*/DISTRIB_DESCRIPTION=\"'Slingshot')} #{version}\"/' /etc/lsb-release"

        machine.vm.provision :file, source: "slingshot.tar.gz", destination: "/tmp/labs.tar.gz"

        machine.vm.provision "setup", type: "ansible" do |ansible|
            ansible.compatibility_mode = "2.0"
	    ansible.playbook = "ansible/slingshot.yml"
        end

        machine.vm.provision :reload
    end
end
