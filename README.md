# Supabase Password Reset (Static HTML)

Lightweight, framework-free pages to support Supabase Auth flows:

- ✅ **Email confirmation** page (`confirm.html`)
- ✅ **Generic landing** page for auth redirects (`index.html`)
- ✅ **Password reset** page (`reset.html`) that updates the user's password using `@supabase/supabase-js` v2

These pages work on any static host (GitHub Pages, Netlify, Vercel, S3, etc.).

---

## 📁 Project Structure

```plaintext
.
├── index.html        # Generic landing page for Supabase auth redirects
├── confirm.html      # "Email confirmed" success page
└── reset.html        # Password reset form + Supabase session restore/update
```
---

## 📧 How the Email Confirmation Flow Works

1. **User signs up in your app**
   - They provide their email and password during registration.

2. **Supabase sends a confirmation email**
   - This email contains a link with a short-lived verification token.

3. **User clicks the confirmation link**
   - They are redirected to your configured confirmation page (`confirm.html`).

4. **`confirm.html` shows success**
   - Displays a message like **"Email Confirmed 🎉"** to let the user know their email has been successfully verified.

5. **User can now log in**
   - The account is marked as confirmed in Supabase Auth, and the user can sign in normally.

---

## 🔐 How the Reset Flow Works

1. **Trigger a reset email**

2. **User clicks the email link**  
   They land on `reset.html` with a URL hash that contains a short-lived session.

3. **Restore the session on `reset.html`**

4. **Update the password**

5. **Show success**  
   Display a success message; the user can now sign in with the new password.
