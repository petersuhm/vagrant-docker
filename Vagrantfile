Vagrant.configure("2") do |config|
  config.vm.box = "raring"
  config.vm.box_url = "http://cloud-images.ubuntu.com/raring/current/raring-server-cloudimg-vagrant-amd64-disk1.box"
  # we'll forward the port 8000 from the VM to the port 8000 on the host (OS X)
  config.vm.network :forwarded_port, host: 8000, guest: 8000
  config.vm.synced_folder(".", "/vagrant")

  # add a bit more memory, it never hurts. It's VM specific and we're using Virtualbox here.
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", 2048]
  end

  config.vm.provision "shell", path: "docker.sh"
end
