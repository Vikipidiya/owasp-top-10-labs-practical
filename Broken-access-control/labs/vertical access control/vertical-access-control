

## 🔼 Vertical Access Control

### 📌 What is Vertical Access Control?

Vertical access control is a type of authorization mechanism that **restricts access based on user roles or privilege levels**.

It ensures that **lower-privileged users cannot access higher-privileged functionality**.

**Example roles:**

* Admin
* Moderator
* User

👉 A normal user should **not** be able to perform admin-level actions.

---

### 🚨 Vertical Privilege Escalation

Vertical privilege escalation occurs when a user with **lower privileges** is able to **gain access to higher-privileged functionality**, such as admin features.

This happens when the application:

* Does not properly check user roles on the server side
* Relies only on client-side controls (UI hiding buttons)

---

### 🧠 Common Examples

* Accessing `/admin` pages as a normal user
* Modifying role parameters in requests (e.g. `role=user` → `role=admin`)
* Calling admin APIs directly without proper authorization checks
* Changing cookies, JWT claims, or headers to elevate privileges

---

### 🛠 How to Test for Vertical Access Control Issues

* Log in as a **low-privileged user**
* Try accessing **admin-only URLs or endpoints**
* Replay admin requests using Burp Suite
* Modify role or privilege values in requests
* Check if the server properly validates permissions

---

### 💥 Impact

If vertical access control is broken:

* Attackers can gain **admin access**
* Sensitive data can be exposed or modified
* Full application compromise is possible

---

---

