---
title: "Blog 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

# NHỮNG BÀI HỌC VỀ TƯ DUY CLOUD-NATIVE TỪ DỰ ÁN THỰC TẾ

Hành trình 13 tuần thực tập và làm việc với dự án Snaptics đã mang lại cho mình nhiều kinh nghiệm thực tiễn quý báu. Việc tích hợp các dịch vụ hạ tầng trên môi trường Cloud đòi hỏi sự thay đổi lớn trong tư duy phát triển phần mềm, vượt ra khỏi giới hạn của việc lập trình thông thường trên máy cá nhân.

Đặc biệt, quá trình tích hợp dịch vụ lưu trữ Amazon S3 vào Backend .NET cho luồng tính năng Quét Hóa Đơn đã giúp mình củng cố rõ rệt các nguyên tắc thiết kế Cloud-Native.

### Những điểm nhấn kỹ thuật quan trọng

- **Tách biệt Compute và Storage (Decoupling)**
  - Trong các mô hình cũ, file tải lên thường được lưu trữ cục bộ ngay trên máy chủ ứng dụng (ví dụ: thư mục `/wwwroot`). Khi hệ thống mở rộng, điều này gây khó khăn trong việc quản lý dung lượng và sao lưu.
  - Áp dụng tư duy Cloud-Native, mình đã sử dụng Amazon S3 để lưu trữ file hóa đơn, trong khi Backend Database chỉ lưu lại URL ánh xạ. Việc tách biệt logic xử lý và kho lưu trữ giúp ứng dụng nhẹ nhàng, dễ dàng mở rộng và tối ưu hóa tài nguyên.

- **Tương tác hạ tầng qua AWS SDK for .NET**
  - Quá trình này giúp mình làm quen với việc cấu hình và điều khiển các dịch vụ AWS hoàn toàn bằng mã nguồn thay vì thao tác thủ công trên Management Console, bước đầu làm quen với tự động hóa trong quản trị hệ thống.

- **Đảm bảo bảo mật với Pre-signed URL**
  - Một yêu cầu đặt ra là: Làm sao để S3 Bucket luôn ở trạng thái Private hoàn toàn để bảo mật, nhưng Frontend Angular vẫn có thể tải và hiển thị hình ảnh hóa đơn cho người dùng?
  - Giải pháp tối ưu chính là sử dụng **Pre-signed URL**. Ứng dụng Backend dùng cặp Access/Secret key để tạo ra một đường dẫn truy cập có thời hạn (ví dụ: 15 phút). Nhờ vậy, hình ảnh được phân phối an toàn, bảo mật dữ liệu tuyệt đối và không cần phải tải dữ liệu về Server rồi mới truyền sang Frontend.

- **Áp dụng nguyên tắc Least Privilege với IAM**
  - Trong giai đoạn đầu, mình có xu hướng cấp quyền rộng (ví dụ: `S3FullAccess`) cho IAM User để tiện lợi cho việc lập trình. Quá trình kiểm tra chéo đã cho thấy đây là một rủi ro bảo mật lớn.
  - Mình đã thực hành thắt chặt JSON Policy, chỉ cấp quyền `PutObject` và `GetObject` cho đúng một S3 Bucket cụ thể (`snaptics-invoices-xyz`). Thao tác này giúp hệ thống an toàn và hạn chế tối đa rủi ro lộ lọt dữ liệu.

- **Xử lý vấn đề bảo mật CORS**
  - Khi triển khai, luồng lấy ảnh bằng Pre-signed URL bị trình duyệt chặn do lỗi CORS. Mình nhận ra rằng bảo mật trên Cloud cần cấu hình đồng bộ ở mọi lớp. Việc thiết lập đúng CORS Policy trên S3 Bucket đã giải quyết vấn đề, cho phép giao tiếp an toàn giữa các domain độc lập.

- **Quản lý vòng đời dữ liệu (Lifecycle) và Tối ưu chi phí**
  - Dữ liệu rác (ảnh mờ, lỗi upload) sinh ra liên tục. Nếu không quản lý, S3 sẽ gây lãng phí chi phí lưu trữ. Mình đã cấu hình S3 Lifecycle Policies để tự động xóa các file hình ảnh tạm thời sau 7 ngày, một thao tác nhỏ nhưng mang lại giá trị vận hành lâu dài.

### Tổng kết hành trình

Kỳ thực tập không chỉ giúp mình nâng cao kỹ năng sử dụng công cụ AWS, mà quan trọng hơn là định hình lại tư duy thiết kế hệ thống.

Cloud-Native là một phương pháp tiếp cận toàn diện: đề cao tính bảo mật từ thiết kế (IAM), tối ưu hóa chi phí (Lifecycle), thiết kế module tách biệt (S3 + EC2 + SQS), và chia sẻ tài nguyên an toàn (Pre-signed URL). Những kiến thức và trải nghiệm thực tiễn này sẽ là nền tảng vững chắc để mình tiếp tục phát triển trên con đường trở thành một Kỹ sư Cloud / Fullstack chuyên nghiệp.

### Hình minh họa

<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 24px; margin-top: 20px;">

  <div style="width: 420px; text-align: center;">
    <img src="/fcj-workshop-template/images/3-BlogsPosted/3.3-Blog3/blog3.jpg"
         alt="Amazon S3 Architecture"
         style="width:100%; height:260px; object-fit:contain; background:#fafafa; border-radius:10px; box-shadow:0 2px 8px rgba(0,0,0,0.15);">
    <p>Kiến trúc Cloud-Native tích hợp Amazon S3 vào ứng dụng Backend.</p>
  </div>

  <div style="width: 420px; text-align: center;">
    <img src="/fcj-workshop-template/images/3-BlogsPosted/3.3-Blog3/blog3.1.jpg"
         alt="Amazon S3 Pre-signed URL"
         style="width:100%; height:260px; object-fit:contain; background:#fafafa; border-radius:10px; box-shadow:0 2px 8px rgba(0,0,0,0.15);">
    <p>Triển khai tạo Amazon S3 Pre-signed URL bằng AWS SDK for .NET.</p>
  </div>

</div>