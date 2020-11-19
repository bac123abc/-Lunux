2.1. SYSTEM STARTUP AND SHUTDOWN
Quá trình khởi tạo hệ thống
Linux boot process là quá trình khởi tạo hệ thống Linux. Nó bao bước từ khi ta bật máy đến khi giao diện người dùng sẵn sàng.
Khi bật máy tính, quá trình khởi động sẽ được thực hiện theo các bước dưới đây:BIOS thực hiện kiểm tra tính toàn vẹn trên bộ nhớ và tìm kiếm các chỉ dẫn trên MBR.MBR nạp trình quản lý khởi động LILO hoặc GRUB.LILO/GRUB sẽ nhận diện kernel hệ điều hành và nạp nhân hệ điều hành từ /boot.Nhân hệ điều hành chuyển quyền điều khiển cho chương trình /sbin/init.Dựa trên mức hoạt động tương ứng, /sbin/init thực hiện nạp các dịch vụ và gắn kết (mount) tất cả các phần chia của hệ thống (trong /etc/fstab)
Tiến trình init: Các bước khởi động của init
Đầu tiên, init gọi thi hành /etc/rc.d/rc.sysinit để thiết lập đường dẫn, kiểm tra các hệ thống tập tin v.v…
Kế tiếp, init sẽ thực thi /etc/inittab (mô tả các mức thi hành).
Init gọi thi hành script /etc/rc.d/init.d/functions cho biết các khởi động hay ngừng một chương trình và cách xác định PID của một chương trình.
Tiếp tục, init khởi động các tiến trình ngầm nằm trong các thư mục /etc/rc.d/rc0.d/, /etc/rc.d/rc1.d/…
Gọi thi hành /etc/rc.d/rc.local: bổ sung thêm các lệnh cần thiết.
Sau khi init đã xử lý tất cả các mức thi hành, script /etc/inittab phát sinh một tiến trình getty cho mỗi virtual c
