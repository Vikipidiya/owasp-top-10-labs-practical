# Broken Access Control

This section contains practical labs and write-ups related to Broken Access Control
from OWASP Top 10 and PortSwigger Web Security Academy.


## 📌 What is Access Control?
Access control is a security mechanism that defines **what actions a user is allowed to perform** in an application.
It ensures that users can only access resources and functionalities that they are authorized for.

For example:
- A normal user should not be able to access admin pages
- Users should only be able to view or modify their own data

Access control is usually enforced using:
- Authentication (who you are)
- Authorization (what you are allowed to do)
- Roles and permissions (admin, user, moderator, etc.)

---

## 🚨 What is Broken Access Control?
Broken Access Control occurs when an application **fails to properly restrict user actions**, allowing attackers to:
- Access unauthorized pages or functionality
- View or modify other users’ data
- Perform administrative actions without proper privileges

According to **OWASP Top 10**, Broken Access Control is one of the most critical web application vulnerabilities.

---

## 🧨 Common Examples of Broken Access Control
- Accessing admin pages by directly visiting URLs (e.g. `/admin`)
- Changing user IDs in requests (IDOR vulnerabilities)
- Privilege escalation (horizontal and vertical)
- Missing server-side authorization checks
- Insecure direct object references

---

## 🔍 Impact
If exploited, Broken Access Control can lead to:
- Data leakage
- Account takeover
- Unauthorized modifications
- Complete system compromise

---

## 🛡️ Prevention & Mitigation
- Enforce access control checks on the server side
- Implement role-based access control (RBAC)
- Deny access by default
- Validate user permissions on every request
- Avoid exposing sensitive endpoints

---

## 🎯 Purpose of This Section
This folder contains **hands-on labs and write-ups** related to Broken Access Control from:
- OWASP Top 10
- PortSwigger Web Security Academy

The goal is to understand, exploit, and learn how to prevent Broken Access Control vulnerabilities through practical examples.


### Real Application Examples

1. **Online Banking Website**

   * Customers can view their own account balance and transactions.
   * Only bank staff (admins) can approve loans or freeze accounts.
   * A normal user cannot see or edit another customer’s account.

2. **Social Media Application**

   * Users can create posts and edit or delete their own posts.
   * Users cannot delete posts created by other users.
   * Admins can remove posts that violate rules.

3. **E-commerce Website**

   * Customers can browse products and place orders.
   * Sellers can add or update their own products.
   * Admins can manage users, products, and orders.

4. **School or Learning Management System**

   * Students can view their grades.
   * Teachers can upload assignments and grade students.
   * Students cannot change grades or access other students’ records.

 application secure and organized.
