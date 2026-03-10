# DevBlog — Django Blog Application

A fully functional blog website built with Django + Tailwind CSS.

## Features
- **User Authentication**: Register, Login, Logout with session management
- **User Profiles**: Edit username/email, bio, profile picture upload
- **Blog Posts**: Create, edit, delete posts with optional cover images
- **Authorization**: Only logged-in users can create/edit; only post authors can edit/delete their own posts
- **Responsive UI**: Tailwind CSS, mobile-friendly navbar
- **Dark Mode**: Toggle with localStorage persistence
- **SQLite**: Zero-config database

## Setup

```bash
# 1. Install dependencies
pip install django pillow

# 2. Apply migrations
python manage.py migrate

# 3. (Optional) Create superuser for admin panel
python manage.py createsuperuser

# 4. Run the dev server
python manage.py runserver
```

Then open http://127.0.0.1:8000

## Project Structure
```
blogproject/
├── blogproject/         # Django project config
│   ├── settings.py
│   └── urls.py
├── blog/                # Main app
│   ├── models.py        # Post, Profile models
│   ├── views.py         # All view logic
│   ├── forms.py         # RegisterForm, PostForm, ProfileForm
│   └── urls.py          # App URL routes
├── templates/
│   ├── base.html        # Navbar, dark mode, messages
│   └── blog/            # All page templates
├── media/               # Uploaded images (auto-created)
└── db.sqlite3           # Database (auto-created)
```

## Pages
| URL | Description |
|-----|-------------|
| `/` | Home — post list |
| `/register/` | Register new account |
| `/login/` | Login |
| `/logout/` | Logout |
| `/profile/` | View & edit profile |
| `/post/create/` | Write new post |
| `/post/<id>/` | View post |
| `/post/<id>/edit/` | Edit post |
| `/post/<id>/delete/` | Delete post |
| `/admin/` | Django admin panel |
