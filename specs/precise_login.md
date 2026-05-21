# Precise Login Spec

Build a login system for a web application with the following requirements:

- Users log in with email and password.
- Passwords must be hashed before storage.
- Sessions expire after 30 minutes of inactivity.
- After 5 failed login attempts, the account is locked for 15 minutes.
- Users can reset passwords through a time-limited email link.
- The system must reject invalid email formats.
- The system must return generic error messages for failed login attempts.