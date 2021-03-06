# REPORT 1

![image15](https://user-images.githubusercontent.com/74639473/99750858-b7071600-2b13-11eb-8f33-be06b6fd50f7.png)
![image16](https://user-images.githubusercontent.com/74639473/99750863-b9697000-2b13-11eb-8cba-7c63d7058c37.png)
![image17](https://user-images.githubusercontent.com/74639473/99750878-bec6ba80-2b13-11eb-991b-688724b06f98.png)
![image18](https://user-images.githubusercontent.com/74639473/99750887-c0907e00-2b13-11eb-8750-b45036a30cc0.png)
![image19](https://user-images.githubusercontent.com/74639473/99750892-c38b6e80-2b13-11eb-99a7-210bea4fd599.png)
![image20](https://user-images.githubusercontent.com/74639473/99750899-c5553200-2b13-11eb-88d0-113164afadbc.png)
![image21](https://user-images.githubusercontent.com/74639473/99750908-ca19e600-2b13-11eb-9bf9-7384587396f6.png)
![image22](https://user-images.githubusercontent.com/74639473/99750912-cbe3a980-2b13-11eb-89bc-dba5ffe3959b.png)
![image23](https://user-images.githubusercontent.com/74639473/99750917-cf773080-2b13-11eb-9225-649a07c11f9e.png)
![image24](https://user-images.githubusercontent.com/74639473/99750921-d1d98a80-2b13-11eb-8f83-5be3d15799ec.png)
![image25](https://user-images.githubusercontent.com/74639473/99750924-d30ab780-2b13-11eb-98cc-e721ac1f5372.png)
![image26](https://user-images.githubusercontent.com/74639473/99750928-d4d47b00-2b13-11eb-8429-6f699507ec8b.png)

# 1.1. FILE SYSTEM CONFIGURATION

File system được dùng để quản lý các dữ liệu được đọc và lưu trên thiết bị.File system cho phép người dùng truy cập nhanh chóng và an toàn khi cần thiết.Các loại file system

	Filesystem cơ bản: EXT2, EXT3, EXT4, XFS, Btrfs, JFS, NTFS,…

	Filesystem dành cho dạng lưu trữ Flash: thẻ nhớ,…

	Filesystem dành cho hệ cơ sở dữ liệu

	Filesystem mục đích đặc biệt: procfs, sysfs, tmpfs, squashfs, debugfs,…


 Thư mục |  Chức năng |
 ------- | ---------- |
/bin | Các chương trình cơ bản|
/boot|Chứa nhân Linux để khởi động và các file system maps cũng như các file khởi động giai đoạn hai.|
/dev | Chứa các tập tin thiết bị (CD Rom, HDD, FDD….).|
/etc |  Chứa các tập tin cấu hình hệ thống.|
/home |Thư mục dành cho người dùng khác root.|
/lib | Chứa các thư viện dùng chung cho các lệnh nằm trong /bin và /sbin. Và thư mục này cũng chứa các module của kernel.|
/mnt hoặc /media |Mount point mặc định cho những hệ thống file kết nối bên ngoài.|
/opt |Thư mục chứa các phần mềm cài thêm.
/sbin |Các chương trình hệ thống

	/srv
	Dữ liệu được sử dụng bởi các máy chủ lưu trữ trên hệ thống.

	/tmp
	Thư mục chứa các file tạm thời.

	/usr
	Thư mục chứa những file cố định hoặc quan trọng để phục vụ tất cả người dùng.

	/var
	Dữ liệu biến được xử lý bởi daemon. Điều này bao gồm các tệp nhật ký, hàng đợi, bộ đệm, bộ nhớ cache,…

	/root
	Các tệp cá nhân của người quản trị (root)

	/proc
	Sử dụng cho nhân Linux. Chúng được sử dụng bởi nhân để xuất dữ liệu sang không gian người dùng.

# thông tin về hệ thống

	cat /proc/cpuinfo hiển thị thông tin CPU

	cat /proc/meminfo hiển thị thông tin về RAM đang sử dụng

	cat /proc/version hiển thị phiên bản của kernel

	cat /etc/redhat-release hiển thị phiên bản Centos

	uname -a hiển thị các thông tin về kernel

	free -m hiển thị lượng RAM còn trống

	df -h hiển thị thông tin những file hệ thống nơi mỗi file thường trú hoặc tất cả những file mặc định và lệnh này có thể xem được dung lượng ổ cứng đã sử dụng và còn trống bao nhiêu.

	du -sh xem dung lượng của thư mục hiện tại

	du -ah xem chi tiết dung lượng của các thư mục con, và cả các file

	du -h --max-depth=1 xem dung lượng các thư mục con ở cấp 1 (ngay trong thư mục hiện tại)

	df kiểm tra dung lượng đĩa cứng, các phân vùng đĩa

	top hiển thị sự hoạt động của các tiến trình, đặc biệt là thông tin về tài nguyên hệ thống và việc sử dụng các tài nguyên đó của từng tiến trình.

	vmstat 3 : kiểm soát hành vi của hệ thống

	vmstat -m : kiểm tra thông tin bộ nhớ

	shutdown, halt: Tắt hệ thống tại thời điểm yêu cầu

	pwd: hiển thị thư mục hiện tại

#  add disk và cấu hình LVM
-cấu trúc LVM

![image1](https://user-images.githubusercontent.com/74639473/99750706-760f0180-2b13-11eb-8e90-d512a2136c35.png)

cài đặt LVM:

add đĩa vào máy  ảo Centos

![image2](https://user-images.githubusercontent.com/74639473/99750733-7effd300-2b13-11eb-9c51-14dff14c4c7c.png)

xem máy ảo đã nhận disk chưa : lsblk

![image3](https://user-images.githubusercontent.com/74639473/99750737-81622d00-2b13-11eb-9801-9a5a10ed2b66.png)

Tạo các partition cho các ổ mới , bắt đầu từ sdb với lệnh :fdisk /dev/sdb

![image4](https://user-images.githubusercontent.com/74639473/99750746-832bf080-2b13-11eb-97f5-6d2fceb40db8.png)

	Tạo Physical Volume :pvcreate /dev/sdb1
	tạo Volume Group :vgcreate vg-demo1 /dev/sdb1 /dev/sdc1
	tạo logical Volume: lvcreate -L 1G -n lv-demo1 vg-demo1
	
	![image5](https://user-images.githubusercontent.com/74639473/99750791-96d75700-2b13-11eb-89f1-ea47dfaeaf5c.png)


# 1.2. USER ACCOUNT MANAGEMENT
Files used in creating a user
	tập tin /etc/passwd:  là csdl các tài khoản người dùng trên Linux dưới dạng văn bản: xem thông tin file /etc/passwd : cat /etc/passwd
	tập tin /etc/shadow: là nơi lưu trữ mật khẩu đã được mã hóa.xem thông tin file /etc/shadow là cat /etc/shadow
	tập tin /etc/group là nơi lưu thông tin các nhóm
	
	-tạo người dùng và mật khẩu: 
	
![image6](https://user-images.githubusercontent.com/74639473/99750798-98a11a80-2b13-11eb-8892-f634d285dc33.png)

	tạo Group: groupadd  group
	
![image7](https://user-images.githubusercontent.com/74639473/99750800-9a6ade00-2b13-11eb-922c-7c05bf714f49.png)

	add user vào group : usermod - g group user
	
![image8](https://user-images.githubusercontent.com/74639473/99750805-9c34a180-2b13-11eb-8adc-e4ac56e1c284.png)
	chown ,chmod 

![image9](https://user-images.githubusercontent.com/74639473/99750811-9dfe6500-2b13-11eb-8560-eff988829143.png)

Lenh sudo 
	cho phép một số user được định nghĩa trong file cấu hình /etc/sudoers có thể chạy một số câu lệnh xác định với quyền hạn root hoặc với quyền hạn của một user khác. khi sử dụng sudo thì yêu cầu nhập password trước khi thực hiện. các lệnh sudo sẽ ghi log lại trong file var/log/messages

# 1.3. PACKAGE MANAGEMENT
# Xem cu phap lenh rpm: man rpm
cài đặt gói: rpm -ivh <tap tin.rpm>
	
![image10](https://user-images.githubusercontent.com/74639473/99750815-9fc82880-2b13-11eb-9986-a7687aef9989.png)
	
thông tin  tập tin của 1 gói: rpm -qpl <tập tin rpm>

xóa một gói :rpm -e <tên gói>

thông tin về gói : rpm -qpi <tên gói>

liệt kê ds các gói đã cài đặt : rpm -qa

kiểm tra gói : rpm -q

liên kết ds tập tin của 1 gói: rpm -ql <tên gói>

cho biết tập tin thuộc gói nào : rpm -qf <tập tin>

Sử dụng yum để cài đặt gói
	cài đặt gói mc

![image11](https://user-images.githubusercontent.com/74639473/99750841-ace51780-2b13-11eb-84e4-a7f2959bf371.png)
![image12](https://user-images.githubusercontent.com/74639473/99750851-b0789e80-2b13-11eb-934c-b63466f6d2bf.png)

	xem thông tin gói mc
	
![image13](https://user-images.githubusercontent.com/74639473/99750854-b40c2580-2b13-11eb-9959-57448361442d.png)
![image14](https://user-images.githubusercontent.com/74639473/99750857-b53d5280-2b13-11eb-9025-1007d6469267.png)

	xem một số thông tin 


	update : yum update
	liệt kê ds đã cài: yum list install







		

# REPORT 2

# 2.1. SYSTEM STARTUP AND SHUTDOWN
# Quá trình khởi tạo hệ thống
Linux boot process là quá trình khởi tạo hệ thống Linux. Nó bao bước từ khi ta bật máy đến khi giao diện người dùng sẵn sàng.

Khi bật máy tính, quá trình khởi động sẽ được thực hiện theo các bước dưới đây:BIOS thực hiện kiểm tra tính toàn vẹn trên bộ nhớ và tìm kiếm các chỉ dẫn trên MBR.MBR nạp trình quản lý khởi động LILO hoặc GRUB.LILO/GRUB sẽ nhận diện kernel hệ điều hành và nạp nhân hệ điều hành từ /boot.Nhân hệ điều hành chuyển quyền điều khiển cho chương trình /sbin/init.Dựa trên mức hoạt động tương ứng, /sbin/init thực hiện nạp các dịch vụ và gắn kết (mount) tất cả các phần chia của hệ thống (trong /etc/fstab)

Tiến trình init: Các bước khởi động của init
	Đầu tiên, init gọi thi hành /etc/rc.d/rc.sysinit để thiết lập đường dẫn, kiểm tra các hệ thống tập tin v.v…
	Kế tiếp, init sẽ thực thi /etc/inittab (mô tả các mức thi hành).
	Init gọi thi hành script /etc/rc.d/init.d/functions cho biết các khởi động hay ngừng một chương trình và cách xác định PID của một chương trình.
	Tiếp tục, init khởi động các tiến trình ngầm nằm trong các thư mục /etc/rc.d/rc0.d/, /etc/rc.d/rc1.d/…
	Gọi thi hành /etc/rc.d/rc.local: bổ sung thêm các lệnh cần thiết.
	Sau khi init đã xử lý tất cả các mức thi hành, script /etc/inittab phát sinh một tiến trình getty cho mỗi virtual console cho mỗi mức thi hành.
# khung tập lệnh
	startx khởi động chế độ xwindows từ cửa sổ terminal
 # quản lý các service
	service --status-all Kiểm tra tất cả các service và tình trạng của nó.
	service mysql stop shutdown dịch vụ mysql.
	service httpd start khởi động dịch vụ httpd.
	whereis mysql hiển thị nơi các file dịch vụ được cài đặt.
	 service --status-all | grep abc, xem tình trạng của tiến trình abc
	service start | stop | restart
	/etc/init.d/ start | stop
	 netstat - plnt kiểm tra xem các dịch vụ đang sử dụng cổng mạng nào có thể kết hợp với grep như sau
	 netstat -plnt | grep :25 (Kiểm tra xem dịch vụ nào đang sử dụng cổng 25)
# 2.2. PROCESS MONITORING AND SCHEDULING
# theo dõi các tiến trình 
	xem tiến trình cha con: ps -ef |more
	xem tiến trình theo cấu trúc : pstree -np | more
	xem tiến trình user khởi tạo: ps -u user
	hủy tiến trình: pkill pid
	hủy tiến trình theo tên : pkill name


# Shared Library
Library là file chứa các đoạn mã lệnh và dữ liệu được tổ chức thành các hàm (subroutine), các lớp (class) nhằm cung cấp dịch vụ, chức năng nào đó cho các chương trình chạy trên máy tính.

xác định các library cần thiết cho 1 chương trình.
	ldd program1, program2

tạo index cho các  shared library

Các library được đặt trong các thư mục như /lib, /usr/lib, /usr/local/lib. Để hướng dẫn cho ld.so tìm kiếm library trong các thư mục này cũng như là các thư mục khác thì có 2 cách:

1.thêm danh sách các thư mục đó vào biên môi trường shell là LD_LIBRARY_PATH

2. tạo index gồm tên các library và thư mục lưu trữ chúng. File /etc/ld.so.cache chứa thông tin index này

thêm các index vào library

	ldconfig [options] /lib_dirs
	trong đó options gồm -p hoặc -v 
	ldconfig -v /lib_dirs

	Để xem nội dung của ld.so.cache: # ldconfig -p

	Tìm kiếm một library trong cache: # ldconfig -p | grep ncurses

Scheduling processes with cron

Cron là một tiện ích giúp lập lịch chạy những dòng lệnh bên phía server để thực thi một hoặc nhiều công việc nào đó theo thời gian được lập sẵn. Một số người gọi những công việc đó là Cron job hoặc Cron task

# 2.3 Cấu hình SSH
kiểm tra đã cấu hình SSH chưa: service sshd restart

cài đặt ssh: yum install openssh-server -y

cài đặt mobaXterm

# thực hiện ssh trên mobaXterm

	/etc/ssh/sshd_config : Cấu hình OpenSSH Server
	/etc/ssh/ssh_config : Cấu hình OpenSSH Client
	~/.ssh/ : Thực mục SSH user
	~/.ssh/authorized_keys hoặc ~/.ssh/authorized_keys : Thư mục chứa public key (RSA hoặc DSA) dùng để cấu hình SSH auth
	/etc/nologin : Nếu file này tồn tại , SSH sẽ từ chối mọi user trừ root
	/etc/host.allow và /etc/hosts.deny : Thư mục Access List của SSH
#cấu hình ssh nâng cao

	- đổi  cổng port 22 thành 2222: vi /etc/ssh/sshd_config 

	sau đó mở port trên iptable chuyển 22 thành 2222
	#service sshd restart
	#service iptable restart
	giới hạn số lần đăng nhập sai và phiên làm việc

	sử dụng ssh Protocol 2

	logout ssh nếu phiên đang nhàn rỗi


