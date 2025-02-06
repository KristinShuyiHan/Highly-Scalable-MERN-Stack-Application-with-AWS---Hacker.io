# Highly Scalable MERN Stack Application with AWS

## Overview

This project is a **highly scalable MERN (MongoDB, Express.js, React.js, Node.js) stack-based** platform designed for a new startup that can scale infinitely. It follows a solid architecture to handle millions of users, ensuring high availability, security, and cost-effectiveness by leveraging AWS services.

## Tech Stack

### **Frontend**

- **React.js** for building the user interface.
- **Next.js** (React Framework) for better SEO, performance, and scalability.
- **Axios** for making API calls.
- **React Hooks** for state management.
- **React Quill** for a rich text editor.
- **Infinite Scrolling with React Infinite Scroll Component**.

### **Backend**

- **Node.js & Express.js** for server-side API development.
- **MongoDB Atlas** as a cloud-managed NoSQL database.
- **Mongoose** for schema modeling and database interactions.
- **Express Validator** for request validation.
- **JWT Authentication** for securing APIs.
- **Nodemailer with AWS SES** for sending transactional emails.

### **AWS Services Used**

- **AWS S3** for scalable file storage.
- **AWS SES** for email notifications.
- **AWS EC2** for hosting the application.
- **AWS IAM** for identity and access management.
- **AWS Route 53** for domain management.
- **AWS CloudWatch** for monitoring logs and metrics.

## Features

- **User Authentication:** Registration, login, password reset with email verification.
- **Content Management:** Users can create, update, delete, and share links.
- **Infinite Scaling:** Hosted on AWS to handle high traffic.
- **SEO Optimized:** Using Next.js for Server-Side Rendering (SSR).
- **Performance Optimizations:** Webpack bundling, lazy loading, and tree shaking.
- **Admin Dashboard:** Manage users, monitor content, and enforce policies.
- **Real-Time Notifications:** WebSocket for instant updates.

---

## **Setup Instructions**

### **1. Clone the Repository**

```sh
 git clone https://github.com/KristinShuyiHan/Highly-Scalable-MERN-Stack-Application-with-AWS---Hacker.io.git
 cd Highly-Scalable-MERN-Stack-Application-with-AWS---Hacker.io
```

### **2. Install Dependencies**

```sh
# Backend dependencies
cd server
npm install

# Frontend dependencies
cd ../client
npm install
```

### **3. Configure Environment Variables**

Create a `.env` file inside the `server` folder and configure your credentials:

```env
MONGO_URI=<Your MongoDB Atlas Connection String>
JWT_SECRET=<Your Secret Key>
AWS_ACCESS_KEY_ID=<Your AWS Access Key>
AWS_SECRET_ACCESS_KEY=<Your AWS Secret Key>
AWS_REGION=<AWS Region>
S3_BUCKET=<Your S3 Bucket Name>
SES_EMAIL=<Your Verified SES Email>
```

### **4. Run the Application**

```sh
# Start the backend server
cd server
npm run dev

# Start the frontend client
cd ../client
npm run dev
```

By default, the backend runs on **http://localhost:8000** and the frontend on **http://localhost:3000**.

---

## **Deployment**

### **1. Deploy the Backend on AWS EC2**

1. **Launch an EC2 Instance** (Ubuntu, free-tier eligible).
2. **Install Node.js and PM2**
   ```sh
   sudo apt update
   sudo apt install nodejs npm
   sudo npm install -g pm2
   ```
3. **Clone and Start the Backend Server**
   ```sh
   git clone <repo-url>
   cd server
   npm install
   pm2 start server.js --name backend
   ```

### **2. Deploy the Frontend on AWS S3 + CloudFront**

1. **Build the frontend**
   ```sh
   cd client
   npm run build
   ```
2. **Upload to S3**
   ```sh
   aws s3 sync out/ s3://your-s3-bucket-name --acl public-read
   ```
3. **Set up CloudFront for CDN delivery**

### **3. Domain and SSL Setup using AWS Route 53 & Cloudflare**

- Buy a domain on **Namecheap** and configure AWS Route 53 for DNS management.
- Set up **Cloudflare SSL** for HTTPS security.

---

## **API Endpoints**

### **Authentication**

- `POST /api/register` - Register a new user
- `POST /api/login` - Authenticate user and return JWT
- `POST /api/forgot-password` - Send reset password email
- `POST /api/reset-password` - Reset password

### **User Operations**

- `GET /api/profile` - Get user profile
- `PUT /api/profile` - Update user profile
- `POST /api/upload` - Upload profile picture (AWS S3)

### **Content Management**

- `POST /api/create-post` - Create a new post
- `GET /api/posts` - Fetch all posts
- `GET /api/post/:id` - Get post details
- `PUT /api/post/:id` - Update post
- `DELETE /api/post/:id` - Delete post

### **Admin Routes**

- `GET /api/admin/users` - Fetch all users
- `DELETE /api/admin/user/:id` - Delete a user

---

## **Performance & Security Enhancements**

- **Use WebSocket for Real-time Notifications**
- **Optimize Image Uploads with AWS S3 and Pre-signed URLs**
- **Set up JWT-based authentication for Secure API Access**
- **Use PM2 for Process Management on EC2**
- **Load Balancing with AWS Elastic Load Balancer (ELB)**
- **CloudWatch for Monitoring and Logging**

---

## **Future Improvements**

- Implement **GraphQL** for optimized queries.
- Add **AI-powered content recommendation**.
- Use **Microservices architecture** for further scalability.
- Migrate authentication to **AWS Cognito**.

---

## **Contributing**

1. Fork the repo.
2. Create a feature branch: `git checkout -b feature-branch`.
3. Commit changes: `git commit -m "Added new feature"`.
4. Push to branch: `git push origin feature-branch`.
5. Open a **Pull Request**.

---

## **License**

This project is licensed under the **MIT License**.
