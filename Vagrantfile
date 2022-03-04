Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  #config.vm.synced_folder "app/", "/var/www/app",
    #create: true, group: "vagrant", owner: "vagrant",
    #id: "app"
  #config.vm.network "forwarded_port", guest: 8080, host: 8081,
  #auto_correct: true, id: "wanderer-app"
#end
  config.vm.define "app" do |app|
    app.vm.synced_folder "app/", "/var/www/app",
      create: true, group: "vagrant", owner: "vagrant",
      id:"app"
    app.vm.network "forwarded_port", guest:8080, host: 8081,
    auto_correct: true, id: "wanderer-app"
    app.vm.network "private_network", ip: "192.168.200.10"
    app.vm.provision "ansible_local" do |ansible|
      #ansible.playbook = "ansible/playbook.yaml"
      ansible.playbook = "ansible/node.yaml"
      ansible.become = true
      ansible.become_user = "root"
    end
  end
  config.vm.define "prom" do |prom|
    prom.vm.network "forwarded_port", guest:9090, host:9090,
    auto_correct: true, id: "promtheus"
    prom.vm.network "private_network", ip: "192.168.200.11"
  end
end