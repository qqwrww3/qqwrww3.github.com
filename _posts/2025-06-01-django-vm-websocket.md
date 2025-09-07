---
layout: post
title:  "이미지 업로드"
date:   2024-06-01 12:05:00 +0700
categories: [python, Django]
---

여러 이미지를 올리는 곳

### 고양이 이미지들

<img width="530" height="338" alt="image" src="https://github.com/user-attachments/assets/e3d2710b-6a62-4d11-aaf3-b6d8bfb1db3f" /><br>
<img width="194" height="260" alt="image" src="https://github.com/user-attachments/assets/39dfe6fc-71dd-43c3-ac69-ceeadfbc0b86" />

### 강아지 이미지들

<img width="173" height="148" alt="image" src="https://github.com/user-attachments/assets/989b9b12-6d87-49c0-b9b9-339e2a4fe4de" /><br>
<img width="270" height="148" alt="image" src="https://github.com/user-attachments/assets/64f4619f-ec3c-4e58-9f86-02048993ceb0" /><br>

### 게임 이미지

<img width="300" height="168" alt="image" src="https://github.com/user-attachments/assets/2dd077b5-f538-4510-83d4-a6b15dea65ab" />

#### 내가 왜 이런 것들을 올리는가

### 1. 의미가 없어서

이 이미지들에 의미는 없다<br>
그냥 올리는 것임

### 2. 올리고 싶어서

실제 내 블로그는 처음 만드는 것이라서<br>
아무거나 올리고 싶었다

### 언재인지 모르갰는데 그 떄 교통사고 현장 목격함

앞에 검은 차가 가고 있었는데 비 때문에 길이 미끄러워서<br>
잠깐 세웠는데 뒤에 가던 차가 급발진하더니 표지판에 박음
진짜 ㄹㅈㄷ였음

To connect to your EC2 instance:
- Set environment variables:
  ```bash
  export AWS_HOSTNAME=your-ec2-public-dns
  export AWS_USERNAME=ec2-user
  ```
- Place your SSH private key as `terminal/aws.pem` (chmod 600, not tracked by git)

The backend will use these to establish an SSH session for the WebSocket terminal.

### Observability: Tracing Everything

- **OpenTelemetry**: Traces HTTP, WebSocket, Celery, and Redis operations
- **Jaeger**: Visualize traces and debug performance bottlenecks
- **Grafana**: Build dashboards for service monitoring

#### Class-Level Tracing
Decorators like `@traced_class` and `@traced_async_class` automatically trace all methods in a class, reducing boilerplate and ensuring consistent observability.

#### Redis Tracing
All Redis and Django cache operations are automatically traced and enriched with context—no manual instrumentation needed.

### Health Checks and Periodic Tasks
- `/health-check/` endpoint for monitoring
- Celery task runs every minute, calling the health check and logging results (fully traced)

### Customization
- **Frontend**: Edit `terminal/templates/terminal/terminal.html`
- **Backend**: Extend `TerminalConsumer` for authentication, EC2 connection, and streaming logic

### Running the Slidev Presentation
Want to demo or learn more? Run the included Slidev presentation:
```bash
npm install --save-dev @slidev/cli
npx slidev
```
This opens an interactive presentation in your browser using `slides.md`.

### Final Thoughts

This project is a great starting point for building secure, observable, and scalable web-based terminals for cloud infrastructure. With full tracing and monitoring out of the box, you can focus on features—not plumbing.

**Check out the [GitHub repo](https://github.com/agusmakmun/django-aws-terminal-websocket) for the full code and documentation!** 
