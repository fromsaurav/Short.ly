## 🧠 Micro-SaaS Link Analytics Dashboard

A full-stack URL shortener with an analytics dashboard — similar to Bitly — built using:

- **Frontend**: Vite + React + TailwindCSS  
- **Backend**: Node.js + Express + TypeScript  
- **Database**: MongoDB (Atlas)  
- **Deployment**: Vercel (Frontend), Render/Railway (Backend)  

---

### 🌐 Features

- User Signup, Signin & JWT-based Auth  
- Create short links (max 4 per user)  
- Analytics dashboard for tracking visits  
- URL search functionality  
- Clean TailwindCSS UI  
- Toast messages & Auth redirect  
- Email field-based user ID & auth logic  

---

## ⚙️ Tech Stack

| Layer     | Stack                        |
|-----------|------------------------------|
| Frontend  | React + Vite + TailwindCSS   |
| Backend   | Node.js + Express + TypeScript |
| Database  | MongoDB Atlas                |
| Auth      | JWT                          |
| Deployment| Vercel (frontend), Railway/Render (backend) |

---

## 🧪 Test Credentials

Use the following credentials to test the application:

- **Email**: `admin`
- **Password**: `password`

---

## 🚀 Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

---

## 🧪 Backend Setup

```bash
cd backend
npm install
npm run dev
```

### ⚙️ .env for Backend

```env
PORT=3000
MONGODB_URI=your_mongodb_uri
JWT_SECRET=your_secret_key
```

---

## 📦 API Endpoints & Payloads

---

### ✅ POST /api/auth/signup

**Request:**

```json
{
    "email":"user@gmail.com",
    "password":"password"
}
```

**Response:**

```json
{
    "token": "the token",
    "user": {
        "id": "67f6*********************b",
        "email": "user@gmail.com",
        "message": "user signed up sucessfully"
    }
}
```

---

### ✅ POST /api/auth/login

**Request:**

```json
{
  "email": "user@example.com",
  "password": "your_password"
}
```

**Response:**

```json
{
    "token": "the token",
    "user": {
        "id": "67f6*********************b",
        "email": "user@gmail.com",
        "message": "user logged in sucessfully"
    }
}
```

---

### 🔗 POST /api/shorten

**Headers:**  
`Authorization: Bearer <token>`

**Request:**

```json
{
  "originalUrl": "https://wikipedia.com/",
  "customAlias": "myLink1234", 
  "expirationDate": "2025-06-01T00:00:00Z"  
}
```

**Response:**

```json
{
    "shortUrl": "http://localhost:3000/myLink1234",
    "shortCode": "myLink1234"
}
```

---

### 📊 GET /api/auth/links

**Headers:**  
`Authorization: Bearer <token>`

**Response:**

```json
[
  {
    "_id": "67f62d210fd95393f231e332",
    "userId": "67f51e5217f7d7b1c412ee57",
    "originalUrl": "https://wikipedia.com/",
    "shortCode": "myLink1234",
    "customAlias": "myLink1234",
    "expirationDate": "2025-06-01T00:00:00.000Z",
    "totalClicks": 0,
    "createdAt": "2025-04-09T08:17:37.076Z",
    "__v": 0
  }
]
```

---

### 🔍 GET /api/search

**Headers:**  
`Authorization: Bearer <token>`

**Request:**

```json
{
  "originalUrl": "wikipedia.com"
}
```

**Response:**

```json
{
  "results": [
    {
      "_id": "67f62d210fd95393f231e332",
      "userId": "67f51e5217f7d7b1c412ee57",
      "originalUrl": "https://wikipedia.com/",
      "shortCode": "myLink1234",
      "customAlias": "myLink1234",
      "expirationDate": "2025-06-01T00:00:00.000Z",
      "totalClicks": 0,
      "createdAt": "2025-04-09T08:17:37.076Z",
      "__v": 0
    }
  ]
}
```




### 🎯 Frontend (Vercel)

```bash
cd frontend
npm install
npm run dev
```
To run the frontend locally do this


---
