Absolutely! Here's the **revised lab write-up** with “we” instead of “I”:

---

## **Lab Title**

Unprotected Admin Panel – Access Control Vulnerability

---

## **Objective**

To identify an unprotected admin panel in a web application and delete the user **carlos** by exploiting improper access control.

---

## **Lab Description**

This lab contains an **unprotected admin panel** that can be accessed without authentication. The goal of the lab is to find the admin panel and use it to delete a specific user named **carlos**.

---

## **Methodology / Approach**

In web security testing, one of the first steps is to look for **hidden or sensitive paths** that developers may unintentionally expose. A common place to check is the `robots.txt` file, which may reveal restricted or sensitive endpoints.

---

## **Steps Performed**

### **Step 1: Start the Lab**

* We started the lab and the description indicated that the **admin panel is unprotected**.

<img width="1920" height="1080" alt="Screenshot at 2025-12-30 03-26-14" src="https://github.com/user-attachments/assets/044e6f17-1d78-40ab-89f0-da8766f2169b" />


---

### **Step 2: Check `robots.txt`**

* As a basic web hacking practice, we checked the `robots.txt` file by navigating to:

  ```
  /robots.txt
  ```
* The `robots.txt` file revealed a **hidden endpoint**:

  ```
  /administrator-panel
  ```

📸 *Screenshot 2: robots.txt showing administrator-panel*

---

### **Step 3: Access the Admin Panel**

* We accessed the discovered endpoint:

  ```
  /administrator-panel
  ```
* The admin panel loaded successfully **without any authentication**, confirming that it was unprotected.

📸 *Screenshot 3: Unprotected admin panel page*

---

### **Step 4: Delete User carlos**

* Inside the admin panel, we located the list of users.
* We found the user **carlos**.
* We clicked the **Delete** option for the user carlos.
* The deletion was successful.

📸 *Screenshot 4: User carlos deleted successfully*

---

## **Result**

The user **carlos** was successfully deleted, and the lab was solved. This confirms the presence of an **access control vulnerability** due to an unprotected admin panel.

---

## **Conclusion**

This lab demonstrates the importance of proper access control in web applications. Sensitive functionality such as admin panels should never be exposed without authentication. The `robots.txt` file should not be relied upon to protect sensitive endpoints, as attackers can easily access it to discover hidden paths.

---

## **Security Lesson Learned**

* Admin panels must be protected with strong authentication and authorization.
* Sensitive URLs should not be disclosed in `robots.txt`.
* Always verify access controls for privileged functionality.

---

If you want, I can **also make a visually appealing version with proper headings, numbering, and highlighted key points** so it looks **like a professional lab report**.

Do you want me to do that next?

