---
title: "Sự kiện 4"
date: 2026-07-25
weight: 3
chapter: false
pre: " <b> 4.4. </b> "
---

# FCAJ – Agentic AI Build Week

### Mục tiêu sự kiện

- Chia sẻ kinh nghiệm thực tế từ các đội đã tham gia **FCAJ – Agentic AI Build Week**.
- Tìm hiểu cách các ứng dụng Agentic AI được thiết kế, phát triển và triển khai trên nền tảng AWS trong khuôn khổ Build Week.
- Khám phá các kiến trúc Cloud thực tế và những quyết định kỹ thuật được áp dụng trong các dự án tham gia cuộc thi.
- Học hỏi kinh nghiệm về làm việc nhóm, giải quyết vấn đề và phát triển phần mềm trong môi trường có giới hạn về thời gian.

### Diễn giả

- Đại diện các đội tham gia **FCAJ – Agentic AI Build Week**:
  - **One Team**
  - **Plan V**
  - **3KA**
  - **Dream AI Team**
  - **Six Pillar Team**

- Diễn giả khách mời quốc tế (phần phát biểu mở đầu chương trình).

### Nội dung chính

#### Phần mở đầu

Buổi chia sẻ được mở đầu bởi một diễn giả khách mời quốc tế. Ông chia sẻ về hành trình phát triển của bản thân trong lĩnh vực công nghệ và nhấn mạnh rằng trí tuệ nhân tạo đang phát triển với tốc độ rất nhanh. Bên cạnh những chia sẻ về kinh nghiệm cá nhân, ông khuyến khích mọi người luôn giữ tinh thần học hỏi, sẵn sàng thích nghi với các công nghệ mới và không ngừng hoàn thiện bản thân để theo kịp sự thay đổi của ngành AI và Cloud Computing.

#### Chia sẻ kinh nghiệm từ Build Week

Phần lớn thời gian của chương trình được dành cho đại diện các đội đã tham gia **FCAJ – Agentic AI Build Week** chia sẻ về hành trình phát triển những dự án mà họ mang đi tham gia Hackathon.

Thay vì chỉ giới thiệu sản phẩm cuối cùng, các đội tập trung chia sẻ toàn bộ quá trình phát triển dự án, bao gồm:

- Bài toán thực tế mà nhóm muốn giải quyết.
- Ý tưởng hình thành dự án.
- Kiến trúc hệ thống và các dịch vụ AWS được lựa chọn.
- Những khó khăn gặp phải trong quá trình phát triển.
- Kinh nghiệm và bài học rút ra sau khi hoàn thành Build Week.

Một trong những dự án gây ấn tượng là giải pháp đặt món ăn tự phục vụ bằng AI, cho phép khách hàng tương tác với kiosk thông minh để đặt món mà không cần thao tác trực tiếp với nhân viên. Ngoài ra, một dự án khác hướng đến lĩnh vực tài chính – ngân hàng, ứng dụng Agentic AI nhằm hỗ trợ tương tác với khách hàng và tối ưu hóa các quy trình xử lý giao dịch.

Mặc dù mỗi nhóm theo đuổi một bài toán khác nhau, tất cả đều hướng đến việc xây dựng các hệ thống AI có khả năng mở rộng, tận dụng tối đa các dịch vụ được quản lý trên AWS để giải quyết những nhu cầu thực tế.

#### Trình bày kiến trúc hệ thống

Một trong những nội dung mình ấn tượng nhất là phần phân tích kiến trúc hệ thống của từng dự án.

Qua các sơ đồ được trình bày, mình nhận thấy hầu hết các đội đều áp dụng mô hình Cloud-native và kết hợp nhiều dịch vụ AWS như:

- Amazon Bedrock và AgentCore để xây dựng AI Agents.
- Amazon API Gateway và AWS Lambda cho các dịch vụ backend.
- Amazon SQS để xử lý tác vụ bất đồng bộ.
- Amazon DynamoDB và Amazon S3 để lưu trữ dữ liệu.
- Amazon OpenSearch Service phục vụ tìm kiếm và Vector Store.
- Amazon ECS, AWS Fargate và Amazon ECR để triển khai ứng dụng container.
- Amazon CloudFront, Amazon Cognito và Application Load Balancer để phân phối ứng dụng và quản lý người dùng.
- Amazon CloudWatch, AWS CloudTrail, AWS WAF, GuardDuty, IAM, AWS KMS và Secrets Manager để giám sát, bảo mật và quản lý hệ thống.

Những kiến trúc này cho thấy việc xây dựng một ứng dụng Agentic AI hoàn chỉnh không chỉ phụ thuộc vào mô hình AI mà còn cần sự kết hợp giữa hạ tầng Cloud, bảo mật, lưu trữ dữ liệu, giám sát và điều phối dịch vụ.

### Những điều học được

#### Kiến thức chuyên môn

- Hiểu rõ hơn cách các ứng dụng Agentic AI được xây dựng bằng cách kết hợp nhiều dịch vụ được quản lý trên AWS.
- Có cái nhìn thực tế hơn về kiến trúc Cloud-native dành cho các hệ thống AI.
- Quan sát cách các nhóm triển khai Amazon Bedrock, AWS Lambda, Amazon ECS, Amazon S3, DynamoDB, API Gateway, OpenSearch cùng nhiều dịch vụ AWS khác trong các dự án thực tế.

#### Học hỏi từ thực tế

- Hiểu được cách các nhóm chuyển đổi ý tưởng thành sản phẩm trong khoảng thời gian giới hạn của Build Week.
- Nhận thấy tầm quan trọng của việc thiết kế kiến trúc hệ thống, khả năng mở rộng, bảo mật và giám sát trong quá trình phát triển ứng dụng AI.
- Học hỏi được nhiều kinh nghiệm thực tế về quá trình phát triển sản phẩm, làm việc nhóm và giải quyết các vấn đề kỹ thuật trong môi trường Hackathon.

#### Phát triển bản thân

- Buổi chia sẻ giúp mình nhận thấy tầm quan trọng của tinh thần học hỏi liên tục, khả năng làm việc nhóm và quá trình cải tiến sản phẩm.
- Những kinh nghiệm được chia sẻ từ các đội tham gia Build Week tạo thêm động lực để mình tiếp tục trau dồi kiến thức về AWS và phát triển backend.
- Chương trình cũng truyền cảm hứng để mình tham gia nhiều hơn vào các cuộc thi và dự án thực tế về Cloud Computing và AI trong tương lai.

### Áp dụng vào công việc

- Tiếp tục nghiên cứu các mô hình kiến trúc Cloud-native dành cho ứng dụng AI.
- Tìm hiểu sâu hơn về Amazon Bedrock AgentCore và cơ chế điều phối AI Agents.
- Thực hành nhiều hơn với các dịch vụ AWS như API Gateway, Lambda, ECS, DynamoDB, OpenSearch, CloudWatch và IAM.
- Áp dụng các nguyên tắc thiết kế hệ thống có khả năng mở rộng và các Best Practices của AWS vào những dự án backend sau này.

### Cảm nhận về sự kiện

Tham gia **FCAJ – Agentic AI Build Week Sharing Session** giúp mình hiểu rõ hơn về hành trình phát triển một sản phẩm AI hoàn chỉnh trong khuôn khổ của một cuộc thi Hackathon.

#### Học hỏi từ hành trình phát triển dự án

Điều mình ấn tượng nhất không phải là các sản phẩm cuối cùng, mà là cách các đội chia sẻ toàn bộ quá trình phát triển dự án trong Build Week. Từ việc xác định bài toán thực tế, xây dựng ý tưởng, thiết kế kiến trúc hệ thống, lựa chọn các dịch vụ AWS phù hợp cho đến quá trình phối hợp giữa các thành viên và liên tục cải tiến sản phẩm trong suốt cuộc thi.

Qua những chia sẻ đó, mình nhận ra rằng để xây dựng một ứng dụng AI hoàn chỉnh không chỉ cần kiến thức lập trình mà còn đòi hỏi tư duy thiết kế hệ thống, khả năng làm việc nhóm và quá trình cải tiến liên tục.

#### Tiếp cận các kiến trúc Cloud hiện đại

Một điểm mình đặc biệt ấn tượng là các sơ đồ kiến trúc được trình bày trong buổi chia sẻ. Mặc dù mỗi đội giải quyết một bài toán khác nhau, hầu hết đều áp dụng các nguyên tắc thiết kế Cloud-native và kết hợp nhiều dịch vụ AWS như Amazon Bedrock, Lambda, API Gateway, Amazon ECS, Amazon S3, DynamoDB, CloudWatch và IAM để xây dựng các hệ thống có khả năng mở rộng, bảo mật và dễ vận hành.

Những ví dụ thực tế này giúp mình hiểu rõ hơn cách các dịch vụ AWS được kết hợp với nhau để tạo nên một hệ thống AI hoàn chỉnh thay vì chỉ sử dụng riêng một mô hình AI.

#### Cảm nhận cá nhân

Buổi chia sẻ giúp mình có cái nhìn thực tế hơn về quá trình phát triển phần mềm trong môi trường Hackathon. Lắng nghe những kinh nghiệm từ các đội đã hoàn thành Build Week giúp mình hiểu rằng bên cạnh kiến thức kỹ thuật, việc lập kế hoạch, phối hợp trong nhóm và khả năng thích nghi với những thay đổi trong quá trình phát triển cũng đóng vai trò rất quan trọng.

Sự kiện cũng tạo thêm động lực để mình tiếp tục học AWS, AI và phát triển các kỹ năng backend nhằm có thể tự tin tham gia những cuộc thi và dự án Cloud trong tương lai.

#### Một số hình ảnh tại sự kiện

<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 24px; margin-top: 20px;">

  <div style="width: 360px; text-align: center;">
    <img src="/images/4-EventParticipated/4.4-Event4/event4.3.jpg"
         alt="Kiến trúc hệ thống AWS"
         style="width:100%; height:230px; object-fit:cover; border-radius:10px; box-shadow:0 2px 8px rgba(0,0,0,0.15);">
    <p>Kiến trúc hệ thống Agentic AI được một trong các đội Build Week trình bày.</p>
  </div>

  <div style="width: 360px; text-align: center;">
    <img src="/images/4-EventParticipated/4.4-Event4/event4.2.jpg"
         alt="Phiên khai mạc"
         style="width:100%; height:230px; object-fit:cover; border-radius:10px; box-shadow:0 2px 8px rgba(0,0,0,0.15);">
    <p>Phần mở đầu của buổi chia sẻ FCAJ – Agentic AI Build Week Sharing Session.</p>
  </div>

  <div style="width: 360px; text-align: center;">
    <img src="/images/4-EventParticipated/4.4-Event4/event4.1.jpg"
         alt="Người tham gia sự kiện"
         style="width:100%; height:230px; object-fit:cover; border-radius:10px; box-shadow:0 2px 8px rgba(0,0,0,0.15);">
    <p>Chụp ảnh lưu niệm cùng các bạn tham gia sau buổi chia sẻ.</p>
  </div>

  <div style="width: 360px; text-align: center;">
    <img src="/images/4-EventParticipated/4.4-Event4/event4.jpg"
         alt="Ảnh tập thể"
         style="width:100%; height:230px; object-fit:cover; border-radius:10px; box-shadow:0 2px 8px rgba(0,0,0,0.15);">
    <p>Ảnh lưu niệm cùng các thành viên tham dự tại địa điểm tổ chức sự kiện.</p>
  </div>

</div>

> **Nhìn chung, FCAJ – Agentic AI Build Week Sharing Session đã mang đến cho mình nhiều góc nhìn thực tế về quá trình xây dựng một sản phẩm AI trên nền tảng AWS trong môi trường Hackathon. Bên cạnh việc hiểu rõ hơn cách các dịch vụ AWS được kết hợp để xây dựng những hệ thống AI có khả năng mở rộng và dễ vận hành, mình còn học hỏi được nhiều kinh nghiệm về tư duy thiết kế hệ thống, làm việc nhóm và quá trình phát triển sản phẩm từ những đội đã trực tiếp tham gia Build Week. Những chia sẻ này đã tạo thêm động lực để mình tiếp tục nâng cao kiến thức về Cloud Computing, AI và áp dụng những kinh nghiệm đó vào các dự án thực tế trong tương lai.**