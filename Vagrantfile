Vagrant.configure("2") do |config|  
  config.vm.box = "ubuntu/trusty64"
  config.vm.define "web" do |web|
    web.vm.network "forwarded_port", guest:80, host: 8080
    web.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "ansible/web.yaml"
      ansible.become = true
      ansible.become_user = "root"
      end
  end
  config.vm.define "db" do |db|
    db.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "ansible/db.yaml"
      ansible.become = true
      ansible.become_user = "root"
      end
    end
end
