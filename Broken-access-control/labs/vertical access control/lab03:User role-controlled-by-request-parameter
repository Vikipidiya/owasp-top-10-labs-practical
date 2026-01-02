

#LAB: User Role Controlled by Request Parameter

**Platform:** PortSwigger Web Security Academy
**Level:** Apprentice
**Category:** Broken Access Control

---

## Lab Goal

Exploit a forgeable cookie to gain admin access and delete the user **carlos**.

we have Credentials for login :
wiener : peter





## Exploitation Steps

### 1️⃣ Login & Intercept Request

Logged in as `wiener` and intercepted the request to on click on My Account using Burp Suite.

📸

```md
![Login](screenshots/login.png)
```

---

### 2️⃣ Identify Forgeable Admin Cookie

Observed the following cookie in the request:

```
Admin=false
```

This indicates that admin authorization is controlled client-side.

📸

```md
![Admin cookie](screenshots/admin-false.png)
```

---

### 3️⃣ Privilege Escalation (Repeater)

Modified the cookie in Burp Repeater:

```
Admin=false → Admin=true
```

This granted access to the admin panel at `/admin`.

📸

```md
![Repeater admin true](screenshots/repeater-admin-true.png)
```

---

### 4️⃣ Automate with Match & Replace

Configured Burp to automatically modify requests:

**Proxy → Options → Match and Replace**

* **Match:** `Admin=false`
* **Replace:** `Admin=true`

📸

```md
![Match and Replace](screenshots/match-replace.png)
```

---

### 5️⃣ Delete User

Accessed `/admin` and deleted the user **carlos**.

📸

```md
![Admin panel](screenshots/admin-panel.png)
```

---

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



