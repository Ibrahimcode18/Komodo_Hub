# Komodo Hub 🦎

A comprehensive web-based platform designed to create an interconnected community for organizations (schools and communities) to collaborate, share educational content, and engage with interactive learning resources focused on endangered species and conservation.

---

## 🎯 Overview

Komodo Hub is an interactive, multi-tenant web application that serves as a centralized hub for organizations to manage their communities, share educational articles about endangered species, and provide interactive learning through games and discussions. The platform emphasizes conservation awareness through content about species like Komodo dragons, Sumatran tigers, Javan rhinoceros, and other endangered animals.

The application supports a hierarchical role-based access control (RBAC) system allowing different user types to have specific permissions and responsibilities within their organizations.

---

## ✨ Features

### General Features (All Authenticated Users)
- 🏠 **Home Page** - Central hub with platform overview
- 📚 **Articles** - Read educational content about endangered species
- 🎮 **Games** - Interactive learning through educational games
- 👥 **Community Engagement** - Participate in community discussions
- 📧 **Contact Us** - Get in touch with administrators

### Organization Management
- Create and manage multiple organizations (schools or communities)
- Hierarchical user management within organizations
- Role-based access control with granular permissions
- Organization-specific content isolation

### Content Management
- 📝 Create, publish, and manage articles with rich text editing
- 🖼️ Image uploads with validation (PNG, JPG, JPEG, GIF)
- 💬 Comment system for community engagement
- 📰 Article categorization by organization

### Interactive Learning
- 🎯 **Card Match Game** - Memory-based learning game
- ❓ **Quiz Game** - Test knowledge on conservation topics
- 🔤 **Word Scrabble** - Word-based learning game

### School-Specific Features
- 📍 School Information Pages - Manage school announcements
- 🏫 School Lobby - Community discussion space
- 📚 School Content Library - Organization-specific resource collection
- 🎓 Program Management - Track educational programs

---

## 🛠️ Technology Stack

| Layer | Technologies |
|-------|---------------|
| **Frontend** | JavaScript, HTML5, CSS3, Bootstrap 5 |
| **Backend** | Python, Flask |
| **Database** | SQLite with SQLAlchemy ORM |
| **Authentication** | Flask-Login with password hashing (pbkdf2:sha256) |
| **File Upload** | Werkzeug for secure file handling |
| **Rich Text Editor** | TinyMCE |

---

## 📁 Project Structure
```text
Komodo_Hub/
│
├── main.py
├── requirements.txt
├── Procfile
├── README.md
│
├── instance/
│   └── (Flask instance configuration)
│
└── website/
    ├── __init__.py
    ├── auth.py
    ├── models.py
    ├── views.py
    ├── database.db
    │
    ├── __pycache__/
    │
    ├── templates/
    │   ├── base1.html
    │   ├── base2.html
    │   ├── login.html
    │   ├── signup.html
    │   ├── resetpassword.html
    │   ├── homePage.html
    │   ├── AboutPage.html
    │   ├── Contact.html
    │   ├── articlespage.html
    │   ├── articleopener.html
    │   ├── addarticle.html
    │   ├── addcontent.html
    │   ├── sumatran-tiger.html
    │   ├── komodo-dragon.html
    │   ├── javan-rhino.html
    │   ├── javan-eagle.html
    │   ├── celebes-macaque.html
    │   ├── tarsius.html
    │   ├── game.html
    │   ├── cardMatch.html
    │   ├── quiz.html
    │   ├── wordScrabble.html
    │   ├── schoolinformation.html
    │   ├── schoollobby.html
    │   ├── schoolcontent.html
    │   ├── program.html
    │   ├── content.html
    │   ├── contentopener.html
    │   ├── information.html
    │   ├── addorganization.html
    │   └── adduser.html
    │
    └── static/
        ├── css/
        │   ├── navfoot.css
        │   ├── articlestyles.css
        │   ├── cardMatch.css
        │   ├── quiz.css
        │   ├── login.css
        │   └── signup.css
        │
        ├── javascript/
        │   ├── homepage.js
        │   ├── cardMatch.js
        │   └── quiz.js
        │
        ├── images/
        │   ├── Contact/
        │   ├── articles/
        │   ├── authentication/
        │   ├── base2/
        │   ├── cardMatch/
        │   ├── games/
        │   ├── homePage/
        │   ├── upload/
        │   └── bat.png
        │
        └── tinymce/
            └── (Rich text editor library)
```
---

## 👥 User Roles and Permissions

### 1. **Komodo Hub Admin** 👑
Administrative super-user with platform-wide control.

**Capabilities:**
- ✅ Add and manage new organizations (schools or communities)
- ✅ Automatically register the first user as organization admin
- ✅ Create and manage platform-wide articles
- ✅ Access all pages and content from all communities
- ✅ Platform-wide oversight and management

### 2. **School Admin** 🏫
Organizational administrator responsible for school management.

**Capabilities:**
- ✅ Add new users to the school
- ✅ Assign user roles during registration (teacher, student, etc.)
- ✅ Access all hub pages and community content
- ✅ Manage organizational settings

### 3. **School Teacher** 👨‍🏫
Educational staff member managing school content.

**Capabilities:**
- ✅ Manage School Information pages (add/delete)
- ✅ Post and delete messages on School Lobby
- ✅ Add new content to School Content page
- ✅ Access all hub pages and community content
- ✅ Create educational resources

### 4. **Student** 👨‍🎓
Learning community member with limited permissions.

**Capabilities:**
- ✅ Access all general hub content
- ✅ View school information, lobby, content, and programs
- ✅ Post messages in school lobby
- ✅ Delete only their own messages
- ✅ Participate in games and discussions

### 5. **Community Admin** 👥
Administrator for community organizations.

**Capabilities:**
- ✅ Access all hub and community pages
- ✅ Add new users to community
- ✅ Add community-specific content
- ✅ Manage community information

### 6. **Community Member** 👤
Regular community participant.

**Capabilities:**
- ✅ Access all hub pages
- ✅ View content from all communities
- ✅ Access their own community's information
- ✅ Participate in discussions

### 7. **Komodo Hub Member** 🌐
General member with basic access.

**Capabilities:**
- ✅ Access all hub pages
- ✅ View content from all communities
- ✅ Participate in games and discussions

---

## 🎯 Core Features by Role

### Content Management
- **Admins & Teachers**: Create articles with image uploads, rich text content, and descriptions
- **All Users**: Read and comment on articles
- **Authors**: Delete their own content

### Information Sharing
- **School Staff**: Post information and announcements
- **Students**: View information and participate in lobby discussions
- **Deletion**: Only authors and admins can delete content

### Community Engagement
- **Comment System**: Users can discuss articles with inline comments
- **Message Board**: Lobby system for real-time community communication
- **Organization Isolation**: Content is separated by organization/school

---

## 💾 Installation & Setup

### Prerequisites
- Python 3.8+
- pip (Python package installer)
- Virtual environment (recommended)

### Setup Steps

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Ibrahimcode18/Komodo_Hub.git
   cd Komodo_Hub
   ```
2. **Create and activate a virtual environment:**
   ```bash
   python -m venv venv
   venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. **Install dependencies**
   ```bash
   pip install flask flask-sqlalchemy flask-login werkzeug
   ```
4. **Run the application:**
   ```bash
   python main.py
   ```
5. **Access the application:**
   Open your browser and navigate to http://localhost:5000

---

## 🔒 Security Features

* **Password Hashing:** Uses `pbkdf2:sha256` for secure password storage
* **Login Manager:** Flask-Login for session management
* **File Validation:** Allowed extensions: PNG, JPG, JPEG, GIF
* **Secure Filenames:** Werkzeug `secure_filename` prevents path traversal
* **Authentication Decorators:** `@login_required` enforces access control
* **Role-Based Access:** Different routes check user roles before granting access

---

## 🎓 Objectives

Komodo Hub aims to:

* 🌍 Raise awareness about endangered species
* 📚 Provide educational resources on conservation
* 👥 Foster community engagement and collaboration
* 🎮 Make learning interactive and engaging
* 🏫 Support institutional knowledge sharing

---

## 📄 License

This project is open source and available under the MIT License.

---

## 📧 Contact

For questions or support, please use the Contact Us page on the platform or reach out to the repository maintainer.
