---
title: "Sự kiện 4"
date: 2026-07-25
weight: 3
chapter: false
pre: " <b> 4.4. </b> "
---

# FCAJ - Agentic AI Build Week

### Mục tiêu sự kiện

- Tìm hiểu cách các đội biến một ý tưởng nghiệp vụ thành prototype Agentic AI trong Build Week.
- Quan sát kiến trúc AWS, lựa chọn dịch vụ và các đánh đổi kỹ thuật của từng giải pháp.
- Học cách lập kế hoạch, chia việc và xử lý vấn đề khi thời gian phát triển bị giới hạn.

### Diễn giả

- Đại diện các đội **One Team**, **Plan V**, **3KA**, **Dream AI Team** và **Six Pillar Team**
- Một diễn giả khách mời quốc tế trong phần khai mạc

### Nội dung nổi bật

#### Phần mở đầu

Diễn giả mở đầu nói về tốc độ thay đổi nhanh của AI và chia sẻ hành trình làm công nghệ của mình. Điều mình nhớ nhất là sự tò mò và thói quen học hỏi vẫn cần thiết dù công cụ có thay đổi liên tục.

#### Chia sẻ kinh nghiệm từ Build Week

Các đội không chỉ giới thiệu sản phẩm cuối mà còn nói về bài toán ban đầu, quá trình chỉnh ý tưởng, dịch vụ AWS đã chọn, lỗi kỹ thuật và điều muốn cải thiện. Một số ví dụ gồm kiosk gọi món tự phục vụ có AI và giải pháp hỗ trợ tương tác khách hàng trong lĩnh vực tài chính.

#### Trình bày kiến trúc hệ thống

Qua các sơ đồ, mình thấy Amazon Bedrock và AgentCore được dùng cho phần suy luận của agent, API Gateway và Lambda cho API, SQS cho xử lý bất đồng bộ, còn S3 hoặc DynamoDB dùng để lưu trữ. Một số đội kết hợp thêm OpenSearch, ECS, Fargate, ECR, CloudFront và ALB. IAM, KMS, WAF, CloudWatch, CloudTrail, GuardDuty và Secrets Manager hỗ trợ phần vận hành, bảo mật.

### Những điều học được

- Một sản phẩm Agentic AI không chỉ cần model mà còn cần API, dữ liệu, queue, triển khai và giám sát.
- Kiến trúc đơn giản, dễ vận hành đôi khi phù hợp hơn một thiết kế quá phức tạp.
- Khi thời gian ngắn, việc ưu tiên task, trao đổi và nhận phản hồi nhanh rất quan trọng.

### Áp dụng vào công việc

Nội dung này khá gần với hệ thống quản lý chi tiêu của mình vì dự án cũng dùng S3, SQS, API AI, container và mạng AWS. Mình có thể học cách các đội ưu tiên luồng chính trước, để chức năng phụ sau, đồng thời kiểm tra toàn bộ quá trình từ upload đến kết quả cuối.

### Cảm nhận về sự kiện

Buổi này thực tế hơn một buổi giới thiệu công nghệ thông thường vì các đội chia sẻ cả khó khăn gặp phải. Việc nhìn thấy cả quyết định đúng và giới hạn của từng dự án giúp mình hình dung rõ hơn quá trình phát triển thật.

### Bài học rút ra

Mình học được cách nhìn dự án ở mức tổng thể thay vì chỉ tập trung vào một API hoặc một prompt AI. Dự án muốn tiến triển cần phạm vi rõ, kiến trúc vừa sức, người phụ trách cụ thể và kiểm thử nhiều lần.

### Một số hình ảnh tại sự kiện

<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 24px; margin-top: 20px;">
  <div style="width: 360px; text-align: center;"><img src="/images/4-EventParticipated/4.4-Event4/event4.3.jpg" alt="Kiến trúc AWS" style="width:100%; height:230px; object-fit:cover; border-radius:10px;"><p>Kiến trúc Agentic AI</p></div>
  <div style="width: 360px; text-align: center;"><img src="/images/4-EventParticipated/4.4-Event4/event4.2.jpg" alt="Phần khai mạc" style="width:100%; height:230px; object-fit:cover; border-radius:10px;"><p>Phần khai mạc</p></div>
  <div style="width: 360px; text-align: center;"><img src="/images/4-EventParticipated/4.4-Event4/event4.1.jpg" alt="Người tham dự" style="width:100%; height:230px; object-fit:cover; border-radius:10px;"><p>Người tham dự sự kiện</p></div>
  <div style="width: 360px; text-align: center;"><img src="/images/4-EventParticipated/4.4-Event4/event4.jpg" alt="Ảnh tập thể" style="width:100%; height:230px; object-fit:cover; border-radius:10px;"><p>Ảnh lưu niệm</p></div>
</div>
