# CCTV Backend Service

## Overview
This repository contains the backend service for a CCTV monitoring system.  
It is responsible for camera management, user authentication, live video streaming, and cloud-based recording of video feeds.

The backend is designed to ingest RTSP streams from CCTV cameras, convert them into browser-compatible formats, and securely deliver live and recorded video to client applications.

---

## Key Features
- User authentication and authorization
- Camera registration and management
- RTSP stream ingestion
- Live video streaming (RTSP → HLS)
- Cloud-based video storage
- Playback support for recorded footage
- WebSocket support for real-time updates

---

## Tech Stack
- **Runtime:** Node.js
- **Framework:** Express.js
- **Streaming:** FFmpeg
- **Database:** PostgreSQL (Amazon RDS)
- **Storage:** Amazon S3
- **CDN:** Amazon CloudFront
- **Authentication:** JWT
- **Real-time Communication:** Socket.IO
- **Deployment:** AWS EC2

---

## Project Structure
```
src/
 ├── controllers/     # Request handlers
 ├── routes/          # API routes
 ├── services/        # Business logic (streaming, storage)
 ├── middlewares/     # Auth, validation, error handling
 ├── utils/           # Helper utilities
 ├── app.js           # Express app entry point
```

---

## Environment Variables
Create a `.env` file in the root directory:

```env
PORT=3000
NODE_ENV=development

JWT_SECRET=your_jwt_secret

DB_HOST=localhost
DB_PORT=5432
DB_NAME=cctv
DB_USER=postgres
DB_PASSWORD=password

AWS_REGION=ap-southeast-1
S3_BUCKET_NAME=your_bucket_name
```

**Do not commit `.env` files to the repository.**

---

## Getting Started

### Prerequisites
- Node.js (v18 or later)
- FFmpeg installed
- PostgreSQL
- AWS account (for cloud features)

### Install Dependencies
```bash
npm install
```

### Run the Server
```bash
npm run dev
```

Server will start at:
```
http://localhost:3000
```

---

## API Status Check
```http
GET /health
```

Response:
```json
{
  "status": "ok"
}
```

---

## Security Notes
- RTSP URLs should be stored securely
- AWS credentials must be handled via IAM roles
- HTTPS is required in production
- JWT tokens should be short-lived

---

## License
This project is licensed under the **MIT License**.

---

## Notes
This backend is under active development.  
Feature scope and architecture may evolve as the system matures.
