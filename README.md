# Nexo – Social Media Web App
**Web Systems and Technologies – Final Project**  
Saint Michael College of Caraga

---

## Quick Setup (XAMPP / Local)

### 1. Place files
Copy the `nexo-app` folder into your XAMPP `htdocs`:
```
C:\xampp\htdocs\nexo-app\
```

### 2. Import the database (IN ORDER)
Open **phpMyAdmin** → **Import** each file in this exact order:

| # | File | What it creates |
|---|------|-----------------|
| 1 | `sql/nexo_app.sql` | `nexo` database, `users`, `posts`, `comments`, `likes` + sample data |
| 2 | `sql/navbar_features.sql` | `friendships`, `conversations`, `messages`, `notifications`, `user_preferences`, `saved_posts` + sample data |
| 3 | `sql/forgot_password.sql` | `password_resets` table |

> ⚠️ **Do not skip step 2.** The navbar, friends, messages, notifications, and settings will all fail without it.

### 3. Configure database
Edit `config/database.php`:
```php
define('DB_HOST', 'localhost');
define('DB_NAME', 'nexo');
define('DB_PORT', '3306');   // XAMPP default
define('DB_USER', 'root');
define('DB_PASS', '');        // blank for XAMPP default
```

### 4. Visit the app
```
http://localhost/nexo-app/public/
```

### 5. Sample login credentials
| Username | Password |
|----------|----------|
| marcos_reyes | password |
| claire_santos | password |
| javier_dc | password |

---

## Hosting on InfinityFree

1. Upload the contents of `public/` to your `htdocs` folder.
2. Upload everything else (`app/`, `config/`, `lib/`, `sql/`) **outside** `htdocs` (one level up).
3. Update `config/database.php` with InfinityFree's credentials (host is something like `sql200.infinityfree.com`).
4. Import SQL files via InfinityFree's phpMyAdmin in the same order above.
5. Make sure `public/assets/uploads/` is writable (`chmod 777`).

---

## Features
- 🔐 Auth (register, login, logout, forgot password)
- 📰 Feed (create, edit, delete posts with images)
- 💬 Comments (add, edit, delete)
- ❤️ Likes & 🔖 Saved posts
- 👤 User profiles (editable: name, username, bio, photo, mobile, birthday, gender)
- 👥 Friends (send/accept/decline requests, suggestions)
- 💌 Direct Messages (real-time polling)
- 🔔 Notifications (likes, comments, friend requests)
- ⚙️ Settings (email, password, dark mode, privacy)
- 🌙 Dark mode (default) / ☀️ Light mode toggle
- 🔍 Search (users + posts)
- 📱 Mobile responsive with bottom nav bar
