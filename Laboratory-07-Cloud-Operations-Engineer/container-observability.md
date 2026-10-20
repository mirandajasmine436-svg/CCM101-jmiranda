# 🔍 Container Observability

## 📜 Application Logs

**The 404 Error Log Line:**
```text
172.17.0.1 - - [20/Oct/2026:12:13:27 +0000] "GET /hidden-admin-page HTTP/1.1" 404 153 "-" "curl/8.5.0" "-"
```

**Why application logs are vital for troubleshooting:**
Application logs are vital for troubleshooting because they provide a historical record of exactly what happened inside the container. While metrics might tell you *that* an error occurred (like a spike in failed requests), the logs tell you *why* it happened by showing the exact URL, timestamp, and IP address that triggered the issue. As a Cloud Operations Engineer, logs are the first place I look when a user reports a broken page.
