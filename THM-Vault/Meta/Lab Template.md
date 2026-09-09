# Room: Wireshark Basics
**Module:** [[Network Security]] | **Path:** [[SOC Level 1]]

---

## 📚 Theory & Concepts
* **What is Wireshark?** A packet analyzer used to capture and inspect network traffic in real time.
* **Key Concept (PCAP):** Packet Capture files stored on disk containing recorded network traffic.
* **Key Display Filters:**
  * `ip.addr == 192.168.1.1` — Filters traffic to/from a specific IP.
  * `http.request.method == "POST"` — Isolates submitted form data or login credentials.

---

## 🧪 Hands-On Lab Walkthrough

### Task 3: Analyzing HTTP Traffic
* **Goal:** Identify the credentials leaked in plaintext over HTTP.
* **Commands / Filter Applied:**
  `http.request.method == "POST"`
* **Findings:**
  - Target URL: `http://fakebank.thm/login`
  - Leaked Username: `admin`
  - Flag Captured: `THM{p4ck3t_sn1ff1ng_b4s1cs}`

---

## 🧠 Brain Dump & Takeaways
* **Mistake made:** I forgot that `ip.addr` matches both source and destination; use `ip.src` for strictly incoming packets.