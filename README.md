# Python FastAPI Media Sharing App

<div>
  <img src="https://img.shields.io/badge/-Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/-FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white"/>
  <img src="https://img.shields.io/badge/-UV-DE5FE9?style=for-the-badge&logo=uv&logoColor=white"/>
  <img src="https://img.shields.io/badge/-MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white"/>
  <img src="https://img.shields.io/badge/-Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white"/>
</div>

A simple full‑stack [FastAPI](https://fastapi.tiangolo.com/) application that allows users to register, authenticate, and share images and videos. Uploaded media is processed and delivered via [ImageKit](https://imagekit.io/), stored with metadata in a MySQL database, and displayed to all users through a shared feed. The frontend is intentionally minimal and built using [Streamlit](https://streamlit.io/), focusing on functionality rather than UI complexity.

This project demonstrates authentication, media handling, third‑party service integration, and API‑driven architecture using modern Python tooling.

---

## 🚀 Features

- User registration and login with authentication
- Secure access control for protected actions
- Upload images and videos after logging in
- Public feed displaying all uploaded images and videos
- Users can delete only their own uploaded media
- Media processing and CDN delivery via **ImageKit**
- **MySQL** database for persistent storage
- Lightweight frontend built with **Streamlit**
- Dependency and environment management using **uv**

---

## 🧱 Tech Stack

### Backend

- Python
- FastAPI
- MySQL
- ImageKit (media storage and optimization)

### Frontend

- Streamlit (basic templated UI)

### Tooling

- uv (dependency & virtual environment management)

---

## 📁 Project Structure

```txt
.
├── app/
│   ├── app.py          # API definition and routes (auth, media, feed)
│   ├── db.py           # Database models
│   ├── images.py       # ImageKit configuration
│   ├── schemas.py      # Schemas for API payload
│   └── users.py        # User authentication functions
├── frontend.py         # StreamLit frontend
├── main.py             # FastAPI app entry point
├── .env                  # Environment variables
├── pyproject.toml        # Project dependencies (uv)
├── uv.lock               # Locked dependency versions
└── README.md
```

---

## 🔐 Authentication Flow

- Users can register with valid credentials
- Registered users can log in to receive authenticated access
- Only logged‑in users can:
  - Upload images and videos
  - Delete their own media
- All uploaded media is visible in the public feed

---

## 🖼 Media Handling

- Supports both image and video uploads
- Media files are processed and stored using ImageKit
- Optimized media URLs are returned and stored in the database
- Deleting media removes the record and the associated ImageKit asset

---

## 🗄 Database

- Uses **MySQL** for persistent storage
- Stores:
  - User accounts
  - Media metadata (type, URL, owner, timestamps)
- Relational structure ensures users can only manage their own uploads

---

⚙️ Environment Variables

Create a ```.env``` file in the root directory with the following variables:

```env
IMAGEKIT_PRIVATE_KEY=your-imagekit-private-key
IMAGEKIT_PUBLIC_KEY=your-imagekit-public-key
IMAGEKIT_URL=your-imagekit-url

JWT_SECRET = "any-random-string"
```

---

## ▶️ Running the Project Locally

### 1. Clone the repository

```bash
git clone https://github.com/muneefrehman/Python_FastAPI.git
cd Python_FastAPI
```

### 2. Install dependencies using uv

```bash
uv sync
```

### 3. Activate the virtual environment

```bash
source .venv/bin/activate   # macOS / Linux
.venv\Scripts\activate      # Windows
```

### 4. Start the FastAPI server

```bash
uv run main.py
```

### 5. Run the Streamlit frontend

```bash
uv run streamlit run frontend.py
```

---

## 📌 API Overview

| Method | Endpoint | Description |
|----------|----------|----------|
| POST  | /register  | Register a new user  |
| POST  | /login  | User login  |
| POST  | /upload  | Upload image or video  |
| GET  | /feed  | Get all uploaded media  |
| DELETE  | /posts/{post.id}  | Delete user’s own media  |

---

## 🎯 Purpose of the Project

This project was built to:
 - Practice API‑driven backend development with Flask
 - Implement authentication and authorization
 - Work with third‑party media services like ImageKit
 - Integrate a Python backend with a lightweight frontend
 - Use modern Python tooling (uv) for dependency management

---

## 🛠 Future Improvements

- Pagination and lazy loading for the feed
- Media likes and comments
- User profile pages
- Improved frontend UI
