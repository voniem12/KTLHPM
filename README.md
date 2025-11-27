# 🔐 Triển khai môi trường Moodle theo từng CVE (Docker)

Repo này chứa các phiên bản Moodle tương ứng với các CVE phổ biến, dùng để nghiên cứu – mô phỏng – kiểm thử bảo mật.  
Tất cả môi trường đều chạy bằng **Docker Compose**.

---

## 📥 Cài đặt & chạy nhanh

```bash
# Tải repo
git clone https://github.com/voniem12/KTLHPM.git
cd KTLHPM

# Chạy Moodle 3.10.1 (CVE-2021-36393)
cd moodle-3.10.1
docker compose up -d

# Chạy Moodle 3.11.4 (CVE-2022-0332)
cd ../moodle-3.11.4/moodle-docker
docker compose up -d

# Chạy Moodle 4.4.0 (CVE-2024-43425)
cd ../../moodle-4.4.0
docker compose up -d

# Xem hướng dẫn cấu hình chi tiết cho UI ở đây:
https://www.notion.so/POC-CVE-2022-0332-2a35d56d48ab80e0ab8cd0dcc74251c7?source=copy_link
https://www.notion.so/CVE-2021-36393-2a65d56d48ab803f8021c3a7300332c0?source=copy_link
