# Medical Examination Assistant - Backend (Trợ lý Khám bệnh - Backend)

## Tổng quan
Đây là API Backend cho hệ thống Trợ lý Khám bệnh. Được xây dựng trên nền tảng NestJS, nó đóng vai trò là cổng API trung tâm và bộ phận xử lý cho các logic nghiệp vụ phức tạp, điều phối các tác nhân AI (AI Agents) và quản lý cơ sở dữ liệu.

## Công nghệ sử dụng
- **Framework:** [NestJS](https://nestjs.com/)
- **Ngôn ngữ:** TypeScript
- **Database ORM:** [Drizzle ORM](https://orm.drizzle.team/)
- **Cơ sở dữ liệu:** PostgreSQL
- **Tích hợp AI:**
  - [LangChain](https://js.langchain.com/)
  - Google Gemini (GenAI)
- **Validation:** class-validator & class-transformer

## Các tính năng chính
- **API Gateway:** Các endpoint RESTful phục vụ cho frontend.
- **AI Agents:** Các tác nhân AI chuyên biệt cho phân tích y tế, RAG (Retrieval-Augmented Generation - Tạo văn bản tăng cường truy xuất) và tóm tắt thông tin.
- **Quản lý cơ sở dữ liệu:** Truy cập dữ liệu tập trung sử dụng Drizzle ORM.
- **Hệ thống đặt lịch:** Logic cho việc xếp lịch hẹn và giải quyết xung đột lịch.

## Hướng dẫn cài đặt và chạy

### Yêu cầu tiên quyết
- Node.js (khuyên dùng bản v20 trở lên)
- PostgreSQL Database

### Các bước cài đặt

1.  Di chuyển vào thư mục backend:
    ```bash
    cd medical-examination-assistant-be
    ```

2.  Cài đặt các thư viện phụ thuộc:
    ```bash
    npm install
    ```

3.  Cấu hình biến môi trường:
    - Copy file `.env.example` thành `.env`:
      ```bash
      cp .env.example .env
      ```
    - Cập nhật `.env` với URL Cơ sở dữ liệu, API Keys, v.v.

4.  Chạy ứng dụng:
    ```bash
    # Chế độ Development (tự động reload khi sửa code)
    npm run start:dev

    # Chế độ Production
    npm run start:prod
    ```

5.  API sẽ hoạt động tại địa chỉ `http://localhost:4000` (mặc định).

## Cấu trúc dự án
- `/src/app*`: Logic cốt lõi của ứng dụng.
- `/src/database`: Kết nối cơ sở dữ liệu và quản lý schema.
- `/src/agents`: Triển khai các AI Agent.
- `/src/booking`: Module đặt lịch.
- `/src/patient`: Module quản lý bệnh nhân.