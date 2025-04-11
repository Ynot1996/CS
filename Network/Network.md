# 🌐 Internet Networks 講義

適用對象：入門學習者、想快速掌握網路基礎知識的學生或自學者。

---

## 📖 目錄

1. 網際網路是什麼？
2. TCP/IP 四層模型
3. IP 位址與 DNS 原理
4. 常見通訊協定（HTTP、HTTPS、FTP…）
5. 網路設備介紹
6. 網路安全基礎概念
7. 實作與工具推薦
8. 延伸閱讀資源

---

## 1️⃣ 網際網路是什麼？

網際網路（Internet）是一個由全球數十億設備連接而成的網路集合體。其主要功能為**資料傳輸與資源共享**。

- 基於一套共同的**通訊協定（protocols）**
- 資料以**封包（packet）**形式傳輸
- 本質上是**由眾多小型網路組成的網路**

---

## 2️⃣ TCP/IP 模型（四層架構）

| 層級         | 功能                        | 舉例 |
|--------------|-----------------------------|------|
| 應用層       | 提供網路服務給應用程式      | HTTP, FTP, DNS |
| 傳輸層       | 控制資料傳輸的可靠性        | TCP, UDP |
| 網際層       | 資料的路由與位址處理        | IP |
| 網路介面層   | 實體傳輸、網卡、驅動等      | Ethernet, Wi-Fi |

---

## 3️⃣ IP 位址與 DNS

- **IP 位址**：每個網路設備的唯一識別碼（如：192.168.1.1）
- 分為：
  - IPv4（32位元）
  - IPv6（128位元）
- **DNS（Domain Name System）**
  - 功能：將「人類可讀的網址」轉換為「機器可讀的 IP 位址」
  - 例如：`www.google.com` → `142.250.196.4`

---

## 4️⃣ 常見通訊協定

| 協定 | 功能                           | 備註                  |
|------|--------------------------------|-----------------------|
| HTTP | 網頁傳輸協定                   | 無加密                |
| HTTPS| 安全的 HTTP（加密）            | 使用 SSL/TLS 加密     |
| FTP  | 檔案傳輸協定                   | 常用於伺服器檔案存取 |
| DNS  | 網域名稱解析協定               |                       |
| TCP  | 保證傳輸正確、有序             |                       |
| UDP  | 傳輸快速但不保證可靠性         | 適用於即時通訊        |

---

## 5️⃣ 常見網路設備介紹

| 設備       | 功能簡述 |
|------------|----------|
| Router（路由器）     | 負責不同網路間的資料轉送 |
| Switch（交換器）     | 在區域網路中分送資料封包 |
| Modem（數據機）      | 將數位/類比訊號轉換      |
| Access Point（無線基地台）| 提供無線裝置的連線 |

---

## 6️⃣ 網路安全基礎概念

- **Firewall**：封包過濾，阻擋惡意連線
- **加密技術（SSL/TLS）**：保護資料不被攔截
- **VPN（虛擬私人網路）**：建立加密通道，提升隱私
- **DDoS 攻擊**：大量封包癱瘓伺服器的攻擊方式

---

## 7️⃣ 實作與工具推薦

| 工具         | 功能                     |
|--------------|--------------------------|
| `ping`       | 測試主機是否可達         |
| `tracert` / `traceroute` | 顯示資料傳送的路由 |
| `nslookup`   | 查詢 DNS 紀錄            |
| Wireshark    | 封包擷取與分析工具       |
| Packet Tracer| 模擬網路設備與架構       |

---

## 8️⃣ 延伸閱讀資源

- [How the Internet Works - MDN](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/How_does_the_Internet_work)
- 《Computer Networking: A Top-Down Approach》（經典教材）
- [Wireshark 教學 - Practical Networking](https://www.practicalnetworking.net/series/wireshark/)

---

> 📌 本講義由 Wen-Teng Kang 製作，內容可自由引用，請註明出處或 GitHub 連結 🙌
