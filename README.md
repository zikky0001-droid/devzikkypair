# DEV ZIKKY PAIR

**Simple WhatsApp pairing. A cleaner way to get your bot started.**

[![Live](https://img.shields.io/badge/live-online-55e6a5?style=flat-square)](https://dev-zikky-pair.onrender.com/)
[![API](https://img.shields.io/badge/API-available-55e6ff?style=flat-square)](https://dev-zikky-pair.onrender.com/api)
[![Docs](https://img.shields.io/badge/docs-available-8b7cff?style=flat-square)](https://dev-zikky-pair.onrender.com/docs)
[![Node.js](https://img.shields.io/badge/Node.js-powered-43853d?style=flat-square&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![License](https://img.shields.io/badge/license-see_LICENSE-ffc55a?style=flat-square)](LICENSE)
[![Built by](https://img.shields.io/badge/built%20by-DEV%20ZIKKY-8b7cff?style=flat-square)](https://github.com/zikky0001-droid)

DEV ZIKKY PAIR is a WhatsApp pairing service with a web interface and an HTTP API for supported pairing and status operations.

Built by **[DEV ZIKKY TECH](https://github.com/zikky0001-droid)**.

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&height=210&color=gradient&text=DEV%20ZIKKY%20PAIR&animation=fadeIn&fontAlign=50&fontAlignY=42&desc=WHATSAPP%20PAIRING%20SERVICE&descAlign=50&descAlignY=62&fontColor=8b7cff" width="95%" alt="DEV ZIKKY PAIR">

<br><br>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=19&duration=3000&pause=900&color=8b7cff&center=true&vCenter=true&width=820&lines=Simple+pairing.;A+cleaner+bot+setup+experience.;Built+with+intent+by+DEV+ZIKKY." alt="Typing animation">

<br><br>

<a href="https://dev-zikky-pair.onrender.com/"><img src="https://img.shields.io/badge/OPEN%20WEBSITE-07090d?style=for-the-badge&logo=googlechrome&logoColor=8b7cff" alt="Open website"></a>
<a href="https://dev-zikky-pair.onrender.com/docs"><img src="https://img.shields.io/badge/API%20DOCUMENTATION-07090d?style=for-the-badge&logo=readthedocs&logoColor=55e6ff" alt="API documentation"></a>
<a href="https://github.com/zikky0001-droid"><img src="https://img.shields.io/badge/DEVELOPER-07090d?style=for-the-badge&logo=github&logoColor=8b7cff" alt="Developer GitHub"></a>

</div>

---

## 📌 Contents

- [Overview](#-overview)
- [Features](#-features)
- [Live Pages](#-live-pages)
- [API Reference](#-api-reference)
- [Request Examples](#-request-examples)
- [Responses and Errors](#-responses-and-errors)
- [Important Notes](#-important-notes)
- [Technology](#-technology)
- [License](#-license)
- [Contact](#-contact)

---

## ✨ Overview

DEV ZIKKY PAIR provides a web interface for WhatsApp pairing and an HTTP API for requesting a pairing code or checking API status. The aim is to provide a straightforward starting point for users working with compatible WhatsApp bot projects.

## 🚀 Features

- 🌐 Web-based pairing interface
- 🔌 HTTP API access
- 📡 API status endpoint
- 📚 Online documentation
- 📱 WhatsApp device-linking workflow
- 🆓 Advertised free pairing option

## 🌐 Live Pages

| Resource | Description |
|---|---|
| [Homepage](https://dev-zikky-pair.onrender.com/) | Main project website |
| [Free Pairing](https://dev-zikky-pair.onrender.com/free) | Pairing interface |
| [API Base](https://dev-zikky-pair.onrender.com/api) | API entry point |
| [API Documentation](https://dev-zikky-pair.onrender.com/docs) | API usage guide |
| [HTML Documentation](https://dev-zikky-pair.onrender.com/docs.html) | Documentation page |
| [Connect](https://dev-zikky-pair.onrender.com/connect) | Connection route |
| [Ping](https://dev-zikky-pair.onrender.com/ping) | Ping route |
| [API Status](https://dev-zikky-pair.onrender.com/api/status) | API status endpoint |
| [Owner Page](https://dev-zikky-pair.onrender.com/owner) | Public owner page |

Individual routes may have different requirements and response types. See the live documentation for current details.

---

## 🔌 API Reference

**Base URL**

```text
https://dev-zikky-pair.onrender.com/api
```

### 1. Generate a pairing code

```http
GET /api?number={phone}
```

Requests a pairing code for a phone number.

**Example request**

```text
https://dev-zikky-pair.onrender.com/api?number=234810XXXXXXX
```

**Example response**

```json
{
  "status": true,
  "creator": "DEV ZIKKY TECH",
  "code": "1234-5678",
  "phone": "+234810XXXXXXX",
  "time": "2026-05-24 12:00:00",
  "website": "https://dev-zikky-pair.onrender.com",
  "message": "Enter this code in WhatsApp > Linked Devices"
}
```

The values above are illustrative placeholders, not a real pairing code or live response.

### 2. Check API status

```http
GET /api/status
```

**Example request**

```text
https://dev-zikky-pair.onrender.com/api/status
```

**Example response**

```json
{
  "status": true,
  "creator": "DEV ZIKKY TECH",
  "online": true,
  "time": "2026-05-24 12:00:00"
}
```

This is an example of the documented response shape. A successful status response does not guarantee every operation is available.

### 3. Documentation route

The supplied API documentation lists `/api/docs` as an HTML documentation route.

- [Main documentation](https://dev-zikky-pair.onrender.com/docs)
- [HTML documentation page](https://dev-zikky-pair.onrender.com/docs.html)

---

## 💻 Request Examples

### JavaScript — Fetch

```javascript
const phone = "234810XXXXXXX";
const url = new URL("https://dev-zikky-pair.onrender.com/api");
url.searchParams.set("number", phone);

const response = await fetch(url);
const data = await response.json();
console.log(data);
```

### JavaScript — Check status

```javascript
const response = await fetch(
  "https://dev-zikky-pair.onrender.com/api/status"
);
const data = await response.json();
console.log(data);
```

### Python — Requests

```python
import requests

url = "https://dev-zikky-pair.onrender.com/api"
response = requests.get(
    url,
    params={"number": "234810XXXXXXX"},
    timeout=20
)
response.raise_for_status()
print(response.json())
```

Replace the example number with a number you own or are authorized to use. These snippets demonstrate HTTP requests; they do not guarantee successful pairing.

---

## ⚠️ Responses and Errors

The supplied API documentation describes these error responses.

### Missing phone number

```json
{
  "status": false,
  "creator": "DEV ZIKKY TECH",
  "message": "Provide phone number",
  "example": "/api?number=234810XXXXXXX"
}
```

### Invalid phone number

```json
{
  "status": false,
  "creator": "DEV ZIKKY TECH",
  "message": "Invalid phone number"
}
```

Check the `status` field and handle HTTP errors, timeouts, and unexpected response formats in your application.

## 🔐 Important Notes

- Use only WhatsApp accounts you own or are authorized to link.
- Treat pairing codes and session credentials as sensitive.
- Never publish session files, authentication tokens, cookies, or private credentials.
- Do not commit environment variables, deployment configuration, or private source files to a public repository.
- Avoid repeatedly requesting pairing codes.
- Refer to the live documentation for current service behaviour and availability.

**Security reminder:** Anyone who obtains valid WhatsApp session credentials may be able to access the associated linked session. Keep them private.

## 🛠️ Technology

The supplied service documentation identifies **Node.js** and **Baileys**. This high-level overview intentionally omits internal architecture, deployment configuration, database details, and private implementation logic.

## 📜 License

See [`LICENSE`](LICENSE) for the terms that apply to this repository.

This public documentation repository does not grant access to private application source code, infrastructure, credentials, or other materials that are not distributed here.

## 👨‍💻 Developer

Built by **DEV ZIKKY TECH**.

- 💻 GitHub: [@zikky0001-droid](https://github.com/zikky0001-droid)
- 🌐 Website: [DEV ZIKKY PAIR](https://dev-zikky-pair.onrender.com/)
- 📚 API Docs: [Documentation](https://dev-zikky-pair.onrender.com/docs)
- 💬 Telegram: [@Zikkystar1](https://t.me/Zikkystar1)
- 🎵 TikTok: [@devzikky](https://tiktok.com/@devzikky)

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=120&section=footer&fontColor=8b7cff" width="100%" alt="Footer">

**DEV ZIKKY PAIR** — Simple pairing. Cleaner workflows.

Built with ⚡ by **DEV ZIKKY TECH** 🇳🇬

</div>

