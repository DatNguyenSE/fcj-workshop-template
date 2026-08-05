---
title: "Blog 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

# NHỮNG BÀI HỌC "TRẦY DA TRÓC VẨY" VỀ AWS VÀ TƯ DUY CLOUD-NATIVE TỪ DỰ ÁN THỰC TẾ

13 tuần thực tập và cày cuốc với dự án Snaptics đã thực sự làm thay đổi hoàn toàn tư duy lập trình của mình. "Works on my machine" (Chạy ngon trên máy tôi) trở nên hoàn toàn vô nghĩa khi bước lên môi trường Cloud! 

Đặc biệt, việc phải tự tay tích hợp Amazon S3 vào Backend .NET để làm luồng Quét Hóa Đơn đã mang đến cho mình những bài học "trầy da tróc vẩy" nhưng cực kỳ đáng giá về tư duy Cloud-Native.

### Những "Aha Moments" Đáng Nhớ Nhất

- **Tách biệt Compute và Storage (Decoupling)**
  - Hồi trước, cứ làm form upload ảnh là mình lưu thẳng file vào thư mục `/wwwroot` của server. Lên Cloud rồi mới thấy làm thế là tự sát! Server phình to, back-up khó khăn.
  - Mình học được cách đẩy toàn bộ file hình hóa đơn lên Amazon S3, và Backend Database chỉ lưu lại một đoạn URL mỏng nhẹ. Logic xử lý riêng, kho lưu trữ riêng, nhẹ gánh cực kỳ!

- **Vật lộn với AWS SDK for .NET**
  - Cảm giác lần đầu tiên viết code C# gọi API đẩy thành công một file thẳng lên bucket S3 thật sự rất tuyệt. Mình bắt đầu quen với việc tương tác hạ tầng bằng code thay vì bấm giao diện Management Console.

- **Sự lợi hại của Pre-signed URL**
  - Đây chính là "Aha Moment" lớn nhất của mình! Ban đầu mình rất đau đầu: *"Làm sao để cái Bucket S3 của mình khóa Private hoàn toàn (không ai chọc vào được), nhưng thằng Frontend Angular của người dùng vẫn load được ảnh hóa đơn để xem?"*
  - Câu trả lời là **Pre-signed URL**. Code Backend của mình dùng cặp Access/Secret key âm thầm tạo ra một cái link tạm thời sống đúng 15 phút rồi quăng cho Frontend. Vừa bảo mật 100%, vừa tiện lợi, khỏi phải tải ảnh về server rồi mới stream qua cho Frontend!

- **Thấm đòn với IAM và "Least Privilege"**
  - Ban đầu, tiện tay mình cấp luôn quyền `S3FullAccess` cho con IAM User dùng trong code. Kết quả bị review bắt đập đi làm lại.
  - Mình buộc phải ngồi cấu hình JSON Policy kẹp chặt lại: Chỉ được phép quyền `PutObject` và `GetObject` vào đúng duy nhất cái Bucket `snaptics-invoices-xyz`. Hơi cực lúc đầu, nhưng ngủ rất ngon vì biết hệ thống cực kỳ an toàn.

- **Vấp ngã với CORS (Cross-Origin Resource Sharing)**
  - Code xong xuôi, Frontend gọi URL ảnh bị trình duyệt vả ngay lỗi CORS đỏ chót. Mình học được bài học xương máu rằng bảo mật Cloud không chỉ nằm ở Backend, mà còn phải thiết lập CORS Policy ngay trên S3 Bucket để trình duyệt nó "nhận anh em" với tên miền của Frontend.

- **Bài toán Tối ưu chi phí**
  - Dữ liệu hóa đơn tạo ra rác rất nhiều (ảnh mờ, ảnh lỗi upload). Nếu để im, S3 sẽ tính tiền lưu trữ vĩnh viễn. Mình phải thiết lập ngay S3 Lifecycle Policies để tự động "đổ rác" xóa các ảnh tạm sau 7 ngày.

### Tổng kết hành trình

Kỳ thực tập này không chỉ dạy mình cách dùng vài dịch vụ AWS. Nó đập đi xây lại tư duy của mình. 

Mình nhận ra Cloud Computing không phải là thuê một cái máy ảo rồi bê y nguyên code cũ lên chạy. Cloud-Native là nghệ thuật thiết kế: bảo mật từ trong trứng (IAM), tối ưu chi phí ngay từ đầu (Lifecycle), tách rời các chức năng (S3 + EC2 + SQS), và chia sẻ an toàn (Pre-signed URL).

Những trải nghiệm thực chiến này là hành trang vô giá, tạo đà rất lớn để mình tiếp tục theo đuổi con đường trở thành một Fullstack / Cloud Engineer chuyên nghiệp!

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