# Lab vagrant + virtualbox trên local 
## 1. cài đặt vagrant vs virtualbox 
1. vagrant 

 https://developer.hashicorp.com/vagrant/install 

2. Virtualbox 

 https://www.virtualbox.org/wiki/Downloads

## 2. cấu hình vagrant vs virtualbox
- tạo thư mục 
- `mkdir vagrant-vb`
- vào thư mục mới tạo 
- `cd vagrant-vb`
- khởi tạo file 
- `vagrant init ubuntu/trusty64`
 ```
 Vagrant.configure("2") do |config|
  config.vm.define "hailh13" do |hailh13|
    hailh13.vm.box = "ubuntu/trusty64"
    hailh13.vm.hostname = "hailh13"
    hailh13.vm.network "private_network", ip: "192.168.100.12"
    hailh13.vm.provider "virtualbox" do |vb|
      vb.name = "hailh13"
      vb.memory = "1024"
      vb.cpus = 2
      disk_path = File.expand_path("hailh13_extra_disk.vdi", File.dirname(__FILE__))
      unless File.exist?(disk_path)
        vb.customize ['createhd', '--filename', disk_path, '--size', 10240] 
      end
      vb.customize [
        'storageattach', :id,
        '--storagectl', 'SATAController',
        '--port', 1,
        '--device', 0,
        '--type', 'hdd',
        '--medium', disk_path
      ]
    end
  end
end
```
- khỏi tạo cấu hình vagrant
- `Vagrant.configure("2") do |config|`
- định nghĩa máy ảo 
```
config.vm.define "hailh13" do |hailh13|
    hailh13.vm.box = "ubuntu/trusty64"
    hailh13.vm.hostname = "hailh13"
    hailh13.vm.network "private_network", ip: "192.168.100.12"
```
- `config.vm.define "hailh13" do |hailh13|` tạo 1 VM tên `hailh13`
- `hailh13.vm.box = "ubuntu/trusty64"` chọn box là ubuntu/trusty64
- `hailh13.vm.hostname = "hailh13"` đặt hostname cho vm 
- `hailh13.vm.network "private_network", ip: "192.168.100.12"` tạo mạng riêng để host và VM giao tiếp với ip cố định 
- cấu hình virtualbox
```
hailh13.vm.provider "virtualbox" do |vb|
      vb.name = "hailh13"
      vb.memory = "1024"
      vb.cpus = 2
```
- `vm.provider "virtualbox" ` chỉ định virtualbox là hypervisor
- `vb.name = "hailh13"` đặt tên VM trong virtualbox
- `vb.memory = "1024"` cấp 1G ram 
- `Vb.cpus = 2` cấp 2 CPU
- khởi chạy 
- `vagrant up` 

## 2. thêm ổ để tạo physical volume , volume Group , logical Volume
- xác định ổ đĩa phụ 

` disk_path = File.expand_path("hailh13_extra_disk.vdi", File.dirname(__FILE__))`
- xác định đường dẫn tuyệt đối đến file ổ đĩa ảo mới 
- `File.dirname(__FILE__)` thư mục chứa `Vagrantfile` 
- ` File.expand_path` tạo đường dẫn đầy đủ , tránh lỗi khi chạy vagrant từ các thư mục khác 

- tạo ổ mới nếu chưa tồn tại 
```
unless File.exist?(disk_path)
        vb.customize ['createhd', '--filename', disk_path, '--size', 10240] 
      end
```

- kiểm tra nếu file `.vdi` chưa tồn tại `File.exist?` tạo mới 
- `--size 10240` dung lượng 10G (kích thước của ổ ảo)
- `vb.customize ['createhd']` gọi VBoxmanage để tạo ổ cứng

- gắn ổ đĩa vào VM
```
vb.customize [
        'storageattach', :id,
        '--storagectl', 'SATAController',
        '--port', 1,
        '--device', 0,
        '--type', 'hdd',
        '--medium', disk_path
      ]
```
- `storageattach` gắn ổ đĩa vào controller Virtualbox
- `:id` Vagrant tự động chèn id ccuar VM 
- `'--storagectl', 'SATAController'` chỉ định controller SATA hiện có trên VM
- `--port 1, --device 0` gắn vào cổng 1 , thiết bị 0 trên contoller
- `--type hdd` loại ổ cứng là HDD ảo 
