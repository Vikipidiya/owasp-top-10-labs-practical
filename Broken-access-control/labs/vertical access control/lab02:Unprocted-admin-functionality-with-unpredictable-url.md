---

## **Lab Title**

Unprotected Admin Functionality with Unpredictable URL

---

## **Objective**

To identify an unprotected admin panel exposed through client-side code and delete the user **carlos** by exploiting improper access control.

---

## **Lab Description**

This lab contains an **unprotected admin panel** that is hosted at an unpredictable URL.  
Although the admin functionality is hidden from normal users, the location of the admin panel is disclosed somewhere within the application.

---

## **Methodology / Approach**

In web application security testing, it is important to inspect **client-side code** such as HTML and JavaScript.  
Developers may unintentionally expose sensitive information like hidden endpoints or admin URLs in the front-end code, which can lead to access control vulnerabilities. we can you different tools according we needs but sometime we don't need 

---

## **Steps Performed**

### **Step 1: Start the Lab**

- The lab description indicated that an **unprotected admin panel** exists.
- The goal was to locate this admin panel and perform an administrative action.

<img width="1920" height="1080" alt="lab2" src="https://github.com/user-attachments/assets/bfcb2b86-fdd8-4df7-a13e-e9810e6390fe" />


---

### **Step 2: Initial Reconnaissance**

- As part of basic reconnaissance, I attempted to access to robots.txt `https://0a260065031bf29c85972d1900a300e7.web-security-academy.net/robots.txt/robots.txt` to check for any disclosed sensitive paths.
- The server returned a **Not Found** response, indicating no useful information was available there.

<img width="1920" height="1080" alt="Screenshot at 2025-12-30 05-44-30" src="https://github.com/user-attachments/assets/48dc0019-3874-4113-a1da-63d662e97875" />


---

### **Step 3: Inspect Client-Side Code**

Since sensitive information is often exposed in client-side code, I inspected the webpage source:

- Right-clicked on the page → **Inspect**
- Reviewed the JavaScript files loaded by the application
- Discovered the following JavaScript snippet:

<img width="1920" height="1080" alt="lab2comment" src="https://github.com/user-attachments/assets/e76f7e7b-95dc-481e-8038-3c90de79fc62" />


```javascript
var isAdmin = false;
if (isAdmin) {
   var topLinksTag = document.getElementsByClassName("top-links")[0];
   var adminPanelTag = document.createElement('a');
   adminPanelTag.setAttribute('href', '/admin-u0pdyy');
   adminPanelTag.innerText = 'Admin panel';
   topLinksTag.append(adminPanelTag);
}
Step 4: Access the Admin Panel

Using the discovered endpoint, I manually navigated to:

/admin-u0pdyy
https://0a260065031bf29c85972d1900a300e7.web-security-academy.net/admin-u0pdyy


The admin panel loaded successfully without any authentication or authorization checks, confirming that it was unprotected.

Step 5: Delete User carlos

Inside the admin panel, I accessed the user management section.

Located the user carlos.

Clicked on the Delete option for the user.

The deletion was successful.

![Lab Start Screenshot](https://github.com/user-attachments/assets/ce940dda-c9ab-468f-b2e5-36379d31a305)


