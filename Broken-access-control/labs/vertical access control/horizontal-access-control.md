## ↔️ Horizontal Access Control

### 📌 What is Horizontal Access Control?

Horizontal access control is an authorization mechanism that **restricts users from accessing other users’ data or resources at the same privilege level**.

It ensures that a user can **only access their own information**, not the data of other users with the same role.

---

### 🚨 Horizontal Privilege Escalation

Horizontal privilege escalation occurs when a user is able to **access or modify another user’s data** without proper authorization.

This usually happens due to **Insecure Direct Object References (IDOR)** or missing ownership checks.

---

### 🧠 Common Examples

* Changing user IDs in URLs:

  ```
  /account?id=1001 → /account?id=1002
  ```
* Modifying user identifiers in API requests
* Accessing another user’s order history, profile, or files
* Guessable or sequential object IDs

---

### 🛠 How to Test for Horizontal Access Control Issues

* Log in as a normal user
* Capture requests using Burp Suite
* Change object identifiers (user ID, account ID, order ID)
* Replay the request and observe the response
* Check if the server verifies resource ownership

---

### 💥 Impact

If horizontal access control is broken:

* Sensitive user data may be exposed
* Data can be modified or deleted
* Privacy violations occur
* Compliance issues may arise

---

### 🛡️ Prevention & Mitigation

* Validate **resource ownership** on the server side
* Use indirect object references where possible
* Enforce access control checks for every request
* Apply the principle of least privilege
* Avoid predictable identifiers

---


---


