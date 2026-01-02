

#LAB: User Role Controlled by Request Parameter

**Platform:** PortSwigger Web Security Academy
**Level:** Apprentice
**Category:** Broken Access Control

---

## Lab Goal

Exploit a forgeable cookie to gain admin access and delete the user **carlos**.

we have Credentials for login :
wiener : peter
<img width="1920" height="1080" alt="Screenshot at 2026-01-02 03-37-52" src="https://github.com/user-attachments/assets/8f13890e-86bc-4d74-8725-2138fec0c3ce" />







## Exploitation Steps

### 1️⃣ Login & Intercept Request

Logged in as `wiener` and intercepted the request to on click on My Account using Burp Suite.

📸


<img width="1920" height="1080" alt="Screenshot at 2026-01-02 03-38-07" src="https://github.com/user-attachments/assets/97819ec9-6f43-4c6a-be0a-19dcd316a57d" />

<img width="1920" height="1080" alt="Screenshot at 2026-01-02 03-40-10" src="https://github.com/user-attachments/assets/372d713b-a6d4-4014-b775-89a3c47927a0" />



### 2️⃣ Identify Forgeable Admin Cookie

Observed the following  request and cookie in the request:
we can see a value in cookie Admin=False means, authorization is manage in client-side


This indicates that admin authorization is controlled client-side.


---

### 3️⃣ Privilege Escalation (Repeater)

Modified the cookie in Burp Repeater:

```
Admin=false → Admin=true
```

This granted access to the admin panel at `/admin`.

📸


<img width="1920" height="1080" alt="Screenshot at 2026-01-02 03-38-07" src="https://github.com/user-attachments/assets/be0c9da6-8ea7-4230-9f49-84e6660886b7" />

```

---

### 4️⃣ Automate with Match & Replace

Configured Burp to automatically modify requests so when each request go through burpsuite it's automaticly set the value Admin=True
go into proxy setting->
**Proxy → Options → Match and Replace**->click add and then

* **Match field:** `Admin=false`
* **Replace field:** `Admin=true`


<img width="1920" height="1080" alt="Screenshot at 2026-01-02 03-44-17" src="https://github.com/user-attachments/assets/f3c0adbe-af9f-494e-8a02-ac9dfcb3d393" />


### 5️⃣ Delete User

Accessed `/admin` and deleted the user **carlos**.

📸


<img width="1920" height="1080" alt="Screenshot at 2026-01-02 03-48-26" src="https://github.com/user-attachments/assets/1a255a2f-557f-42c0-9716-8966f551ef65" />




## Result

✔ Unauthorized admin access
✔ User **carlos** deleted
✔ Lab solved

---

## Vulnerability

The application trusts a **client-side cookie** for authorization, allowing privilege escalation.

* **OWASP:** A01 – Broken Access Control
* **CWE:** 285 – Improper Authorization

---



