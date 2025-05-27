
# API Key Management System

A production-ready Flask REST API for secure user registration, login, and API key management, with SQLite storage and per-user rate limiting.

---

## ✅ Key Features

- 🔑 User registration & login with token authentication (itsdangerous)
- 🗝 Generate, list, and revoke API keys per user
- 🛡 Rate-limited endpoints (5 keys per day)
- 🗄 SQLite backend (simple & portable)
- 🌍 CORS-ready (for integration with any frontend)
- 🧪 Postman-tested, production structure (not a monolith)
- 🚦 Input validation & detailed error handling

---

## 🚀 Endpoints

### Register

**POST** `/register`
```json
{
  "username": "testuser",
  "password": "pass123"
}
```

---

### Login

**POST** `/login`
```json
{
  "username": "testuser",
  "password": "pass123"
}
```
**Response:**
```json
{
  "token": "<your_token>"
}
```

---

### Generate API Key

**POST** `/generate-key`
**Header:**
`Authorization: Bearer <your_token>`

**Response:**
```json
{
  "key": "..."
}
```

---

### List API Keys

**GET** `/list-keys`
**Header:**
`Authorization: Bearer <your_token>`

**Response:**
```json
{
  "keys": ["...", "..."]
}
```

---

### Revoke API Key

**POST** `/revoke-key`
**Header:**
`Authorization: Bearer <your_token>`
```json
{
  "key": "<key_to_revoke>"
}
```

**Response:**
```json
{
  "message": "Key revoked"
}
```

---

## ⛔ Rate Limiting

- **API key generation** is limited to **5 keys per user per day**
- All requests are globally limited to **10 per minute per IP**
- Exceeding the limit returns:
```json
{
  "error": "Rate limit exceeded. Try again later."
}
```

---

## ⚙️ Requirements

```bash
pip install -r requirements.txt
```

- Flask
- Flask-CORS
- Flask-Limiter
- Flask-HTTPAuth
- ItsDangerous
- Python-Dotenv

---

## 🖥 How to Run

```bash
python app.py
```

Server will run at:
```
http://127.0.0.1:5000/
```

---

## 🧪 Example Screenshots

- 🟢 Registration & login (Postman)
- 🟢 API key generation/listing/revoke
- 🟠 Error handling & rate limit
- 🖥️ Console logs

> See `/screens/` for live usage examples.

---

## 📬 Contacts

- Email: talabov.ali72@gmail.com
- Telegram: [@talabovali](https://t.me/talabovali)

---

**Need this in another language/stack (Node.js, Go, etc)?**
Email or Telegram — custom dev available.

