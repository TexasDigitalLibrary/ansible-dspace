Vagrant.configure("2") do |config|
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "dspace7.yml"
  end

  # Application server
  config.vm.define :dspace do |dspace|
    # dspace.vm.hostname = "dspace7"

    dspace.vm.provider :virtualbox do |vb, override|
      # Launch with AWS AMI
      override.vm.box = "gbailey/amzn2"
      vb.memory = 8192
      # vb.cpus = 2

      # Forward ports
      override.vm.network "forwarded_port", guest: 80, host: 80 # Apache (for DSpace frontend)
      override.vm.network "forwarded_port", guest: 4000, host: 4000 # dspace-angular
      override.vm.network "forwarded_port", guest: 8080, host: 8080 # Tomcat (for DSpace API)
      config.vm.network :forwarded_port, guest: 8983, host: 8985 # Solr

    end
  end
end
