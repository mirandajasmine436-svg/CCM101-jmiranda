# 🗄️ MinIO Deployment — Technical Documentation

## 📖 Mission Overview
Deployed a **MinIO S3-compatible object storage server** using Docker inside a KillerCoda Ubuntu Playground to provide a proof-of-concept storage environment for the client's photo-sharing application.

---

## 1️⃣ Exact Docker Command Used

```bash
docker run -d -p 9000:9000 -p 9001:9001 --name minio-server \
  -e "MINIO_ROOT_USER=cloudadmin" \
  -e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
  cgr.dev/chainguard/minio:latest server /data --console-address ":9001"
```

> ⚠️ **Note:** The original lab command referenced `minio/minio`, but that image is no longer available on Docker Hub. The `cgr.dev/chainguard/minio:latest` image was used as a compatible drop-in replacement — it provides the same S3-compatible object storage server and web console.

---

## 2️⃣ Web Console

| 🏷️ Property | 📋 Value |
|---|---|
| **Port** | `9001` |
| **Access Method** | KillerCoda **Traffic / Ports** panel → forward port `9001` → click **Access** |
| **URL Format** | `https://<session-id>-9001.killercoda.com` |
| **Login Username** | `cloudadmin` |
| **Login Password** | `CloudNova2026!` |

- 🔌 Port **9000** → MinIO S3 API endpoint (programmatic access)
- 🖥️ Port **9001** → MinIO Web Console (browser GUI)

---

## 3️⃣ Bucket Created

| 🏷️ Property | 📋 Value |
|---|---|
| **Bucket Name** | `client-photos` |
| **Created Via** | MinIO Web Console → Buckets → Create Bucket |
| **Test Object Uploaded** | A sample file uploaded to verify object storage works |
| **Visible In** | The `client-photos` bucket inside the MinIO console |

---

## 4️⃣ Purpose of the `-e` (Environment Variable) Flags

The `-e` flag sets **environment variables** inside the running Docker container. MinIO reads these variables at startup to configure the root administrator account.

| 🏷️ Flag | 📋 Value | 🎯 Purpose |
|---|---|---|
| `-e "MINIO_ROOT_USER=cloudadmin"` | `cloudadmin` | Sets the **admin username** for the MinIO console and API. |
| `-e "MINIO_ROOT_PASSWORD=CloudNova2026!"` | `CloudNova2026!` | Sets the **admin password** for the same account. |

> 🔒 Without these flags, MinIO would fall back to its insecure defaults (`minioadmin:minioadmin`), which would be unsafe in any real deployment. Using `-e` ensures the container starts with secure, custom credentials.

---

## 5️⃣ Deployment Steps Summary

1. 🚀 Launched a KillerCoda Ubuntu Playground.
2. 🐳 Verified Docker was installed: `docker --version`.
3. ▶️ Ran the `docker run` command above to pull and start the MinIO container.
4. ✅ Confirmed the container was running: `docker ps`.
5. 📜 Checked startup logs: `docker logs minio-server` — confirmed API on port 9000 and WebUI on port 9001.
6. 🌐 Forwarded port **9001** via KillerCoda's Traffic / Ports panel.
7. 🔑 Logged into the MinIO console with `cloudadmin` / `CloudNova2026!`.
8. 🪣 Created the bucket `client-photos`.
9. 📤 Uploaded a sample object into the bucket.
10. 📸 Captured screenshots (`minio-deployed.png`, `minio-bucket-upload.png`) and committed them to GitHub.

---

## 6️⃣ Outcome

✅ MinIO was successfully deployed and is fully operational as a proof-of-concept object storage environment. The `client-photos` bucket was created and verified through the web console, confirming the system is ready for the next stage of the client's photo-sharing application development.
