# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = "drupal-ubuntu-12.04"
  config.vm.box_url = "https://opscode-vm.s3.amazonaws.com/vagrant/boxes/opscode-ubuntu-12.04.box"
  config.vm.forward_port 80, 8080

  # Use this configuration for chef-client and a Chef server
  config.vm.provision :chef_client do |chef|
    chef.chef_server_url = "https://api.opscode.com/organizations/learnchef"
    chef.validation_key_path = "./.chef/learnchef-validator.pem"
    chef.validation_client_name = "learnchef-validator"
    chef.add_recipe("apt")
    chef.add_recipe("drupal")
    chef.node_name = "vagrant_drupal"
  end

  # Use this configuration for chef-solo and Vagrant
  # config.vm.provision :chef_solo do |chef|
  #   chef.cookbooks_path = "cookbooks"
  #
  #   # node attributes are stored on the Chef server when using chef-client. 
  #   # Because chef-solo does not connect to a server or save the node 
  #   # object at all, to have the same passwords persist across chef-solo 
  #   # runs, you must specify them as json attributes
  #   #
  #   # see https://github.com/opscode-cookbooks/mysql#chef-solo-note
  #   chef.json = {
  #     :mysql => {
  #       "server_root_password" => "iloverandompasswordsbutthiswilldo",
  #       "server_repl_password" => "iloverandompasswordsbutthiswilldo",
  #       "server_debian_password" => "iloverandompasswordsbutthiswilldo"
  #     }
  #   }
  #   chef.add_recipe("apt")
  #   chef.add_recipe("drupal")
  #   chef.node_name = "drupal"
  # end
end
