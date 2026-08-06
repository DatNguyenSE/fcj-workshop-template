---
title: "Worklog Tuần 2"
date: 2026-05-18
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2

* Nắm vững các thành phần mạng cốt lõi trong Amazon VPC (IPv4 CIDR Block, Subnet, Route Table, Internet Gateway).
* Phân biệt chi tiết giữa Public Subnet và Private Subnet dựa trên bảng định tuyến và quyền kết nối Internet.
* Tìm hiểu nguyên lý hoạt động và triển khai NAT Gateway cho Private Subnet truy cập Internet chiều đi ra (outbound).
* So sánh cơ chế bảo mật giữa Security Group (Stateful, instance-level) và Network ACL (Stateless, subnet-level).
* Khởi tạo máy chủ Amazon EC2 trong VPC để kiểm tra khả năng kết nối mạng nội bộ và mạng bên ngoài.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Họp Weekly Sync. Đọc tài liệu Amazon VPC, nguyên lý quy hoạch IPv4 CIDR Block và cách chia Subnet.<br>- **Chiều:** Vẽ sơ đồ kiến trúc mạng VPC bằng Draw.io. Tính toán phân bổ dải IP cho VPC `10.0.0.0/16` và chia nhỏ cho 2 Public Subnets, 2 Private Subnets. | 18/05/2026 | 18/05/2026 | [Amazon VPC User Guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |
| 3 | - **Sáng:** Thực hành tạo custom VPC trên AWS Console. Khởi tạo và gắn Internet Gateway (IGW) vào VPC.<br>- **Chiều:** Bị lỗi Overlapping CIDR khi tạo Subnet thứ 3 do tính toán trùng lấp, đọc lại tài liệu chia mạng và fix thành công. Cấu hình Route Table cho Public Subnet (trỏ `0.0.0.0/0` ra IGW). | 19/05/2026 | 19/05/2026 | [VPCs and Subnets](https://docs.aws.amazon.com/vpc/latest/userguide/configure-subnets.html) |
| 4 | - **Sáng:** Khởi tạo NAT Gateway (đặt tại Public Subnet) và cấp Elastic IP tĩnh. Cấu hình Route Table cho Private Subnet trỏ luồng ra NAT Gateway.<br>- **Chiều:** Phân tích sự khác nhau giữa Security Group (Stateful) và Network ACL (Stateless). Cấu hình Inbound rules cho phép truy cập HTTP/SSH từ các nguồn tin cậy. | 20/05/2026 | 20/05/2026 | [NAT Gateways Guide](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html) |
| 5 | - **Sáng:** Tạo 2 máy chủ Amazon EC2 (1 đặt tại Public Subnet, 1 tại Private Subnet) để kiểm tra mạng.<br>- **Chiều:** SSH vào Public EC2 và thực hiện lệnh ping sang Private EC2. Gặp lỗi ping Request Timeout, debug phát hiện do Security Group chưa mở port ICMP IPv4, đã vào Console fix lại. Test outbound internet từ Private EC2 qua NAT thành công. | 21/05/2026 | 21/05/2026 | [Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html) |
| 6 | - **Sáng:** Đọc lý thuyết Workshop 5 về VPC Endpoint và giải pháp PrivateLink (Truy cập AWS Services không qua Internet).<br>- **Chiều:** Dọn dẹp tài nguyên (Xóa NAT Gateway, Terminate EC2 instances) tránh phát sinh chi phí billing. Viết tài liệu tổng kết mạng tuần 2 và lưu sơ đồ lên Notion nhóm. | 22/05/2026 | 22/05/2026 | [AWS Site-to-Site VPN](https://docs.aws.amazon.com/vpn/latest/s2svpn/VPC_VPN.html) |

### Kết quả đạt được tuần 2

* Nắm vững kỹ năng tính toán dải IP CIDR và chia Subnet không bị overlapping.
* Khởi tạo thành công VPC custom, định tuyến Internet Gateway cho Public Subnet hoạt động ổn định.
* Khắc phục thành công các lỗi mạng thực tế: fix lỗi overlapping CIDR, mở port ICMP trên Security Group để ping thông mạng nội bộ.
* Triển khai thành công NAT Gateway kèm Elastic IP, hỗ trợ EC2 Private truy cập Internet an toàn.
* Xây dựng thói quen tối ưu chi phí: luôn dọn dẹp (cleanup) các tài nguyên không dùng (đặc biệt là NAT Gateway và Elastic IP).
