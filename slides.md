---
# You can also start simply with 'default'
theme: default
defaults:
  background: ./images/background.png
  layout: cover
title: The journey of a request
author: José Varela
class: text-center
transition: slide-left
mdc: true
---

# The journey of a request

### José Varela

---

# Why This Matters

- Support engineers often troubleshoot HTTP request failures
- Understanding the journey helps pinpoint issues faster
- Empowers better ticket quality and escalation decisions

::notes::
Introduce the concept with a relatable analogy—like sending a letter through the postal system.

---

# The Journey Begins – Client Side

- User clicks a link or submits a form
- Browser constructs HTTP request (method, headers, cookies)
- DNS lookup resolves domain to IP
- TCP handshake establishes connection

::notes::
Use a flowchart to show browser → DNS → TCP → server. Emphasize how each step can fail.

---

# Anatomy of an HTTP Request

- **Method:** GET, POST, PUT, DELETE
- **Headers:** Content-Type, Authorization, User-Agent
- **Body:** Data payload (for POST/PUT)
- **Cookies:** Session info

```http
POST /login HTTP/1.1
Host: example.com
Content-Type: application/json
Authorization: Bearer token123
```

::notes::
Show a raw request and explain each part. Ask the audience what headers they commonly see.

---

# Server-Side Processing

- Web server receives request (e.g., Nginx, Apache)
- Routing determines which service handles it
- Application logic processes the request
- Database queries may be triggered
- Response is constructed and sent back

::notes::
Mention how logs and routing configs are key for debugging.

---

# The Response Journey

- Server sends back status code, headers, body
- Browser receives and renders content
- User sees result (or error)

::notes::
Use a timeline graphic: request → server → response → render.

---

# Common Issues & Where They Occur

| Issue       | Layer   | Symptom          | Fix              |
| ----------- | ------- | ---------------- | ---------------- |
| DNS failure | Client  | “Site not found” | Check DNS tools  |
| Timeout     | Network | Long loading     | Ping/traceroute  |
| 500 Error   | Server  | “Internal Error” | Check logs       |
| 404 Error   | App     | “Page not found” | Confirm endpoint |

::notes::
Walk through each issue with a real-world example. Ask if they've seen similar cases.

---

# Tools of the Trade

- **Browser Dev Tools:** Inspect headers, status codes
- **Postman / curl:** Manual request testing
- **Wireshark / Fiddler:** Network-level inspection
- **Server Logs:** Access logs, error logs

::notes::
Show a screenshot of Dev Tools inspecting a failed request.

---

# Real-World Case Study

- Ticket: “User can’t log in”
- Found: POST request missing CSRF token
- Fix: Frontend bug, not backend
- Lesson: Always inspect the request payload

::notes::
Make it interactive—ask the audience what they would check first.

---

# Quick Troubleshooting Checklist

✅ Check status code
✅ Inspect headers
✅ Confirm endpoint exists
✅ Review logs
✅ Test manually (curl/Postman)

::notes::
Encourage them to use this checklist before escalating.

---

# Summary & Takeaways

- Every HTTP request has a story—learn to read it
- Understand each layer to troubleshoot effectively
- Use the right tools to isolate problems

::notes::
Reinforce the value of understanding the full journey.

---

# Q&A

- Ask me anything!
- Want to walk through a live example?

::notes::
Have a few FAQs ready in case the audience is quiet.
