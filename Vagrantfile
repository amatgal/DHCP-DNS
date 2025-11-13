Vagrant.configure("2") do |config|

  # --- DNS Server ---
  config.vm.define "server-dns" do |dns|
    dns.vm.box = "debian/bookworm64"
    dns.vm.hostname = "server-dns"
    dns.vm.network "private_network", ip: "192.168.58.10"
  end

  # --- DHCP Server ---
  config.vm.define "server-dhcp" do |dhcp|
    dhcp.vm.box = "debian/bookworm64"
    dhcp.vm.hostname = "server-dhcp"
    dhcp.vm.network "private_network", ip: "192.168.58.11", virtualbox__intnet: "red58"
  end

  # --- Client machine ---
  config.vm.define "client" do |client|
    client.vm.box = "debian/bookworm64"
    client.vm.hostname = "client"
    client.vm.network "private_network", virtualbox__intnet: "red58"
  end

end
