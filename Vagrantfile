Vagrant.configure(2) do |config|
  config.vm.box = "bento/ubuntu-18.04"
  config.vm.define "cyf"
  config.vm.hostname = "cyf"
  config.ssh.forward_x11 = true
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
