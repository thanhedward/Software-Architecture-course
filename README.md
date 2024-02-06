# Software-Architecture-course
a repo to submit assignment

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
  
  Các thành cở bản của Docker Compose:
  - Compose file: Đây là một tệp YAML ( docker-compose.yml ) chứa thông tin cần thiết về container để triển khai ứng dụng.
  - Các dịch vụ (services): Là một nhóm container mà các bạn muốn tạo ra. Mỗi service đại diện cho một thành phần của ứng dụng, ví dụ như service backend, service frontend, service database...
  - Container: Là một đối tượng chứa ứng dụng của bạn và các thành phần của nó, bao gồm phần mềm và cấu hình của ứng dụng. Docker Compose sử dụng các container để triển khai các services được định nghĩa trong tệp docker-compose.yml.
  - Các mạng (networks): Định nghĩa các mạng ảo để các container trong cùng một service hoặc các service khác nhau liên lạc với nhau. Các mạng này cho phép các container truy cập lẫn nhau bằng tên hoặc địa chỉ IP.
  - Các khối lưu trữ (volumes): Là một phần quan trọng của quá trình triển khai Docker Compose, cho phép bạn lưu trữ dữ liệu của ứng dụng của mình độc lập với các container. Điều này giúp cho việc sao lưu, phục hồi và quản lý dữ liệu trở nên dễ dàng hơn.
  - Các biến môi trường (environment variables): Là các biến môi trường được sử dụng để cấu hình các container của dịch vụ. Điều này giúp bạn dễ dàng định nghĩa các cấu hình của ứng dụng của mình trong tệp docker-compose.yml một cách linh hoạt hơn.
  - Command line interface (CLI): Là giao diện dòng lệnh để chạy các lệnh liên quan đến Docker Compose, cho phép tạo, triển khai, quản lý và xóa các container và service.

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

