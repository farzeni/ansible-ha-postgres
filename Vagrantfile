Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"

  config.vm.define "pgpool" do |pgpool|
    pgpool.vm.hostname = "pgpool"
    pgpool.vm.network "private_network", ip: "192.168.56.80"
  end

  config.vm.define "barman" do |barman|
    barman.vm.hostname = "barman"
    barman.vm.network "private_network", ip: "192.168.56.20"
  end

  config.vm.define "pgsql1" do |pgsql1|
    pgsql1.vm.hostname = "pgsql1"
    pgsql1.vm.network "private_network", ip: "192.168.56.101"
  end

  config.vm.define "pgsql2" do |pgsql2|
    pgsql2.vm.hostname = "pgsql2"
    pgsql2.vm.network "private_network", ip: "192.168.56.102"
  end
end
