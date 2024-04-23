Trịnh Đức Thành - 21020792

# Docker, Docker-compose dùng để làm gì?
## Docker
Docker là một công cụ đóng gói phần mềm và triển khai ứng dụng trong các container. Các ứng dụng chạy trong các container được gọi là các container Docker. Docker giúp các lập trình viên chỉ cần chạy các container lên mà không cần phải lo về việc cài các thư viện hoặc môi trường, điều này giúp các lập trình viên phát triển ứng dụng 1 cách nhanh chóng, đảm bảo tính nhất quán giữa môi trường phát triển và môi trường triển khai.

Ví dụ: Có 2 lập trình viên đang làm việc trên một dự án sử dụng framework NestJS và yêu cầu sử dụng NodeJS. Bình thường thì cả 2 lập trình viên cần phải cài cắm các thư viện cần thiết như Nodejs, npm... . Nhưng nếu bạn sử dụng MacOS và cài phiên bản Node 14.x, còn người kia dùng Windows và cài phiên bản Node 12.x, thì trường hợp này sẽ khá dễ phát sinh xung đột vì môi trường phát triển không đồng nhất. Trong trường hợp này, để tránh xung đột giữa các lập trình viên thì Docker cung cấp 1 môi trường đồng nhất giữa cả 2 bằng cách sử dụng image node:14.x, image này đã cung cấp đủ các công cụ và thư viện cần thiết để phát triển xây dựng và triển khai ứng dụng Node.js ( nó giống như bạn cài Node trên máy tính cá nhân của bạn ). Chính vì thế mà khi 1 người khác muốn vào phát triển ứng dụng cùng, thì họ chỉ cần chạy container lên mà không cần phải nghĩ về việc cài môi trường và các thư viện đi kèm.

Các thành phần đi kèm:
- Docker daemon: Là một tiến trình nền chạy trên một máy tính Docker host ( máy cài Docker ), và quản lý các hoạt động Docker như tạo và quản lý các container, images, networks và volumes.
- Docker client: Là một ứng dụng dòng lệnh hoặc giao diện người dùng đồ họa (GUI) để tương tác với Docker daemon và thực hiện các hoạt động Docker. Docker client sử dụng Docker API để giao tiếp với Docker daemon.
- Docker images: Là một gói đóng gói của một ứng dụng và các tài nguyên cần thiết để chạy ứng dụng đó trong một container. Một image có thể được tạo từ một Dockerfile hoặc tải từ một kho chứa image trên internet như Docker Hub.
- Docker container: Là một môi trường đóng gói độc lập, chứa tất cả các thành phần cần thiết để chạy một ứng dụng trong một môi trường cô lập, container được tạo ra từ image sau khi đã đóng gói
- Docker network: cho phép các container tương tác với nhau và với các dịch vụ khác. Một Docker network được tạo ra để tạo một mạng ảo cho các container chạy trên cùng một máy Docker host
- Docker volume: Cho phép các container lưu trữ và truy cập dữ liệu được sử dụng bởi các ứng dụng. Volume giúp dữ liệu được bảo vệ và giữ cho đồng bộ giữa các container.

## Docker-compose
- Docker Compose là một công cụ giúp quản lý nhiều container cùng lúc trong Docker.
- Docker Compose cho phép bạn định nghĩa các container cần thiết để triển khai ứng dụng của bạn trong cùng 1 tệp cấu hình ( .yaml ).
- Các tệp cấu hình này chứa các thông tin về image, environment, network, volume ...
  
 # Linux vs Unix vs BSD hay *nix? macOS thuộc loại nào?

 ## Unix
 Unix là một hệ điều hành được phát triển lần đầu tiên vào thập kỷ 60 và đã được phát triển không ngừng kể từ đó. Đây là một hệ thống ổn định, đa người dùng, đa tác vụ cho máy chủ, máy tính để bàn và máy tính xách tay.

 Unix có nhiều phiên bản khác nhau, mặc dù các phiên bản đều có những điểm tương đồng chung. Các phiên bản Unix phổ biến nhất hiện nay là Sun Solaris, GNU/Linux và MacOS X.

 Cấu trúc hệ điều hành Unix:
   - Kernel là trung tâm của hệ điều hành, nó có nhiệm vụ phân bổ thời gian và bộ nhớ cho các chương trình và xử lý các thư mục, thông tin liên lạc để đáp ứng các lệnh gọi của hệ thống.
   - Shell hoạt động như một giao diện giữa người dùng và Kernel, là một giao diện dòng lệnh (Command Line Interpreter – CLI), dùng để diễn giải các lệnh mà người dùng nhập vào và sắp xếp để chúng được thực hiện.
   - Program.
Mọi thứ trong Unix đều là file hoặc process.

Process là một chương trình đang thực thi được xác định bởi một PID (mã định danh quy trình) duy nhất.

File là một tập hợp dữ liệu. Chúng được tạo bởi người dùng bằng cách sử dụng trình soạn thảo văn bản, trình biên dịch đang chạy…

## BSD

BSD là viết tắt của "Berkeley Software Distribution," một hệ điều hành Unix-like phát triển từ nền tảng của Unix Research của Đại học California, Berkeley. BSD bắt nguồn từ dự án Unix tại đại học này vào những năm 1970 và 1980. BSD là một trong những hệ điều hành Unix đầu tiên được phát triển và phân phối miễn phí dưới dạng mã nguồn mở.

Các dự án BSD phổ biến bao gồm FreeBSD, OpenBSD và NetBSD. Mỗi dự án này có các mục tiêu và sự phát triển riêng, nhưng chúng đều dựa trên mã nguồn gốc từ Berkeley và cung cấp các tính năng như độ ổn định, bảo mật và hiệu suất cao. BSD cũng đã đóng góp rất nhiều vào ngành công nghiệp máy tính, với các yếu tố như TCP/IP stack và các công nghệ mạng khác được phát triển ban đầu trong dự án BSD.

BSD có nhiều phiên bản nổi bật, trong đó có:
1. FreeBSD: Là phiên bản BSD phổ biến nhất và cũng là phiên bản cơ sở cho nhiều phiên bản BSD khác. FreeBSD tập trung vào tính ổn định, hiệu năng và an ninh.
2. OpenBSD: Được phát triển với mục tiêu chính là bảo mật. OpenBSD được kiểm tra kỹ lưỡng và có một hệ thống bảo mật mạnh mẽ.
3. NetBSD: Là phiên bản BSD đa nền tảng, hỗ trợ nhiều kiến trúc phần cứng khác nhau. NetBSD có thể chạy trên nhiều loại máy tính từ máy tính cá nhân đến các máy chủ lớn.
4. DragonFly BSD: Là một nhánh được tách ra từ FreeBSD với mục tiêu là tăng hiệu năng và hỗ trợ xử lý đa nhân.
Phiên bản BSD khác cũng bao gồm PC-BSD (tập trung vào việc cung cấp một phiên bản BSD dễ sử dụng cho người dùng cuối) và Mac OS X (phiên bản BSD được Apple sử dụng làm nền tảng cho hệ điều hành của họ).
BSD được phân phối dưới các giấy phép mã nguồn mở, cho phép người dùng sử dụng, chỉnh sửa và phân phối mã nguồn của BSD. BSD license cũng có các điểm khác biệt so với các giấy phép nguồn mở khác, như cho phép phát triển dự án có chủ sở hữu và không yêu cầu việc công bố mã nguồn.

## Linux
Linux là một hệ điều hành máy tính mã nguồn mở và miễn phí được phát triển dựa trên nhân Linux, một nhân hệ điều hành Unix-like. Ban đầu, Linux được phát triển bởi Linus Torvalds vào những năm đầu của thập kỷ 1990, và ngày nay đã trở thành một trong những hệ điều hành phổ biến nhất trên thế giới, được sử dụng rộng rãi trên các máy tính cá nhân, máy chủ, thiết bị nhúng và nhiều nền tảng khác.
Hệ điều hành Linux bao gồm nhiều phần khác nhau:
 - Nhân (Kernel): Nhân Linux là phần quan trọng nhất của hệ điều hành Linux. Nó là phần mềm trung tâm quản lý tài nguyên của hệ thống, điều khiển truy cập vào phần cứng, quản lý bộ nhớ, quản lý tác vụ và cung cấp giao diện giữa phần cứng và phần mềm ứng dụng.
 - GNU Utilities: Linux thường được kết hợp với các công cụ và tiện ích từ dự án GNU (GNU's Not Unix). Các công cụ này bao gồm các lệnh dòng lệnh (command-line utilities) như ls, cp, mv, grep, và nhiều công cụ khác để quản lý tập tin, thư mục và thực thi các tác vụ.
 - Các giao diện người dùng: Linux có nhiều giao diện người dùng, bao gồm giao diện dòng lệnh (CLI - Command Line Interface) và giao diện đồ họa (GUI - Graphical User Interface). Một số giao diện đồ họa phổ biến bao gồm GNOME, KDE, Xfce và LXDE.
 - Hệ thống quản lý gói: Linux thường đi kèm với một hệ thống quản lý gói để quản lý cài đặt, cập nhật và xóa các phần mềm trên hệ thống. Một số hệ thống quản lý gói phổ biến bao gồm APT (Advanced Package Tool) trong các bản phân phối dựa trên Debian và YUM (Yellowdog Updater Modified) trong các bản phân phối dựa trên Red Hat.
 - Các dịch vụ hệ thống: Linux cung cấp một loạt các dịch vụ hệ thống như quản lý tài nguyên mạng (ví dụ: DHCP, DNS), quản lý người dùng và quyền truy cập (ví dụ: SSH, sudo), và các dịch vụ khác như máy chủ web (ví dụ: Apache, Nginx).

## *nix
Hệ điều hành Unix-like (đôi khi được gọi là UN * X hoặc * nix ) là hệ điều hành hoạt động tương tự như hệ thống Unix, nhưng không nhất thiết phải tuân thủ hoặc được chứng nhận với bất kỳ phiên bản nào của UNIX Base Specification. Unix-like là một ứng dụng hoạt động giống như lệnh hoặc Unix Shell tương ứng, không có tiêu chuẩn để xác định thuật ngữ và có thể có một số khác biệt về quan điểm, mức độ mà một hệ điều hành hoặc ứng dụng nhất định.
*nix bao gồm các hệ điều hành nguồn mở và miễn phí, được lấy cảm hứng từ Unix của Bell Labs hoặc được thiết kế để mô phỏng các tính năng, các công việc thương mại, độc quyền và các phiên bản dựa trên mã nguồn UNIX được cấp phép.

## macOS thuộc loại nào?
MacOS cũng như các hệ điều hành khác của Apple hiện nay là iOS, watchOS, và tvOS đều được dựa trên nền tảng của BSD. Và MacOS cũng là một trong số ít các hệ điều hành được coi là Unix-like, khi có được chứng nhận Single UNIX Specification.

# Alpine vs Ubuntu
## Ubuntu là gì?
Ubuntu là một hệ điều hành máy tính dựa trên Debian GNU/Linux, một bản phân phối Linux thông dụng. Hệ điều hành này yêu cầu cấu hình CPU tối thiểu là 1 GHz, RAM ít nhất 1GB và dung lượng ổ đĩa ít nhất 2.5 GB. Nó hỗ trợ thư viện GNU C và các công cụ quản lý gói dựa trên APT.

## Alpine Linux là gì?
Alpine Linux là một bản phân phối linux nhẹ chủ yếu được tạo ra để chạy các ứng dụng trên các bản phân phối linux. Nó đơn giản, an toàn và tiết kiệm tài nguyên. Nó được thiết kế để chạy trực tiếp từ RAM. Một container cần 8 MB và dung lượng ổ đĩa mà nó yêu cầu là khoảng 130 MB . Nó không chỉ cung cấp một môi trường Linux chính thức mà còn cung cấp một danh sách khổng lồ các gói từ kho lưu trữ. Nó được xây dựng dựa trên musl và BusyBox, do đó nó nhỏ gọn và hiệu quả hơn các hệ điều hành dựa trên GNU/LINUX truyền thống như Ubuntu.

## Khác nhau
1. Kích thước:
- Alpine Linux: Nổi tiếng với kích thước nhỏ gọn, chỉ mất khoảng vài MB. Điều này làm cho Alpine rất phù hợp cho việc sử dụng trong các container docker và các ứng dụng nhúng.
- Ubuntu: Ubuntu có kích thước lớn hơn so với Alpine do nó có nhiều tính năng và gói phần mềm mặc định hơn. Điều này làm cho Ubuntu phù hợp cho cả các ứng dụng máy tính cá nhân và server.

2. Bảo mật
- Alpine Linux: Alpine được biết đến với việc tập trung vào bảo mật và an toàn. Nó sử dụng musl libc thay vì glibc, và mặc định sử dụng BusyBox thay vì các tiện ích GNU thông thường, điều này có thể giảm thiểu các điểm tấn công tiềm ẩn.
- Ubuntu: Ubuntu cũng có các cơ chế bảo mật mạnh mẽ như AppArmor và một hệ thống cập nhật phần mềm tự động, nhưng không như Alpine, nó không tập trung vào việc tối ưu hóa kích thước để tăng cường bảo mật.

3. APK so với APT
Trong các trình quản lý gói truyền thống như APT, trước tiên máy chủ sẽ đọc gói từ kho lưu trữ, lưu nó vào bộ đệm, xác minh chữ ký và sau đó trích xuất nó. Đây là một quá trình sử dụng nhiều tài nguyên vì phải thực hiện ba thao tác đọc và hai thao tác ghi.

Ngược lại với APK được Alpine linux sử dụng, tính toán tổng kiểm tra trong khi chờ I/O, ghi trực tiếp vào hệ thống tệp (dưới dạng .apknew), đổi tên tệp sau khi chữ ký được xác minh hoặc xóa tệp nếu chữ ký không được xác minh. Quá trình này chỉ yêu cầu một lần đọc và một lần ghi. Điều này làm cho máy chủ Alpine hoạt động hiệu quả hơn rất nhiều so với máy chủ Ubuntu vì nó sử dụng ít tài nguyên hệ thống hơn như CPU và hệ thống tập tin.

# VNC
VNC được hiểu là một công nghệ kỹ thuật cho phép việc chia sẻ giao diện màn hình từ xa. VNC giúp người dùng hiển thị được màn hình của máy tính. Hay cả những hệ thống ở xa trực tiếp trên máy tính chính của người dùng. Sau đó có thể điều khiển các thao tác qua kết nối mạng. VNC rất thuận lợi cho những công việc cần quản lý từ xa.

VNC hoạt động theo cơ chế client/server và sử dụng giao thức VNC. Giao thức VNC hoạt động rất đơn giản. Chúng truy cập theo kênh giao diện đồ hoạ của máy tính người sử dụng thông qua mạng internet.
Giao thức VNC được thiết kế dựa trên ý tưởng của Remote Frame Buffer. Người xem sẽ bắt đầu chia sẻ các đầu ra như bàn phím, click chuột với VNC Server. VNC Server sẽ ghi lại các nội dung hiển thị framebuffer và chia sẻ chúng lại cho VNC Client.
Giao thức VNC có 1 số yêu cầu nhất định về màn hình. Cụ thể là tỉ lệ màn hình, độ phân giải màn hình, độ rộng màn hình. Tất cả sẽ đáp ứng được hoạt động của VNC.
