# Project IDS/IPS
## 🔖 Tên đề tài:
**Suricata - Phát hiện và ngăn chặn xâm nhập (IDS/IPS)**

## 🎯 Kịch bản triển khai

### 📌 Kịch bản 1: Stress test kiểm tra hiệu suất Suricata
- **Mô tả**: Tạo lưu lượng mạng lớn và đa dạng để kiểm tra khả năng xử lý đa luồng của Suricata. Yêu cầu tối thiểu: 2 vCPU.
- **Công cụ**: `htop`, `iperf3`, `hping3`

---

### 📌 Kịch bản 2: NMAP máy client
- **Mô tả**: Attacker sử dụng `nmap` để quét cổng trên máy user. Suricata phát hiện hoạt động bất thường (hơn 5 gói SYN/SYN+ACK trong 30s) và chặn IP.
- **Công cụ**: `nmap`

---

### 📌 Kịch bản 3: SQL Injection vào Web Server
- **Mô tả**: Tấn công SQL Injection vào trang DVWA trên Apache Web Server. Suricata phát hiện dựa trên signature, log và cảnh báo tấn công.
- **Công cụ**:
  - Host web: `Apache`, `DVWA`
  - Tấn công: `Burp Suite`

---

### 📌 Kịch bản 4: Phát hiện mã độc và trích xuất file từ gói tin
- **Mô tả**: Máy client tải mã độc qua HTTP. Suricata quét sâu gói tin, phát hiện và lưu file độc hại vào thư mục phân tích, sau đó drop packet.
- **Công cụ**: Suricata với tính năng file extraction

---

### 📌 Kịch bản 5: Phishing email và thực thi shellcode ở máy client
- **Mô tả**: Attacker gửi email phishing để tiêm shellcode, chiếm quyền thực thi từ xa. Suricata phát hiện shellcode và ngắt kết nối.
- **Công cụ**:
  - Gửi mail: `Gmail`, `GoPhish`
  - Tạo shellcode: `msfvenom` (Metasploit)