# Final StudyBuddy  
### A Real-Time Collaborative Learning Platform with ML-Based Toxicity Detection  

StudyBuddy is a collaborative web platform designed for students and developers to join topic-based rooms, discuss problems, share knowledge, and chat in real time.  
The platform integrates **Machine Learning–based Toxic Message Detection** to ensure safe and respectful communication.

---

## 🚀 Key Features

### 🧑‍🤝‍🧑 Real-Time Chat System
- Powered by **Django Channels**, **WebSockets**, and **Redis**
- Messages update instantly across all connected users
- Smooth chat UI with automatic message rendering

### 🛡️ ML-Based Toxicity Detection
- All messages are validated through an ML model
- Toxic messages are:
  - Blocked instantly
  - Not saved in the database
  - Replaced with `[message removed due to toxic content]`
  - User receives a warning alert

### 💬 Smart Toxic Word Sanitization
- Detects individual toxic words
- Replaces them with `[censored]`
- Prevents harmful communication while maintaining usability

### 👤 User Accounts & Profiles
- User registration & login
- Custom profile with avatar upload
- Fully visible in Django admin panel

### 🏷️ Rooms & Topics
- Create or join rooms grouped by topics (AI, Python, Web Dev, etc.)
- See room activity and history
- Persistent chat storage (non-toxic only)

### 📚 Activity Feed
- Displays platform activities such as:
  - New messages
  - Room updates
  - User participation

### 🎨 Modern Responsive UI
- Clean, minimal look inspired by TailwindCSS
- Templates for login, signup, room creation, chat, profile, etc.

---

## 🧠 Machine Learning – Toxicity Model

### ✔ Model Pipeline
- **TF-IDF Vectorizer**
- **Logistic Regression Classifier**
- Trained on a structured dataset containing toxic & non-toxic messages
- Saves model as:


Final_StudyBuddy/
│
├── base/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── consumers.py
│   ├── forms.py
│   ├── migrations/
│   │   ├── 0001_initial.py
│   │   ├── 0002_auto_20210921_1315.py
│   │   ├── 0003_user_avatar.py
│   │   ├── 0004_alter_user_avatar.py
│   │   ├── 0005_alter_user_avatar.py
│   │   ├── 0006_alter_user_managers.py
│   │   ├── 0007_alter_room_description.py
│   │   ├── 0008_message_is_toxic.py
│   │   ├── 0009_message_is_visible.py
│   │   └── __init__.py
│   ├── models.py
│   ├── routing.py
│   ├── templates/base/
│   │   ├── activity.html
│   │   ├── activity_component.html
│   │   ├── delete.html
│   │   ├── feed_component.html
│   │   ├── home.html
│   │   ├── login_register.html
│   │   ├── profile.html
│   │   ├── room.html
│   │   ├── room_form.html
│   │   ├── topics.html
│   │   ├── topics_component.html
│   │   └── update-user.html
│   ├── tests.py
│   ├── urls.py
│   └── views.py
│
├── studybud/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   ├── utils/
│   │   ├── toxic_words.txt
│   │   ├── toxicity_checker.py
│   │   └── toxicity_model.pkl
│   └── wsgi.py
│
├── ml/
│   └── train_toxicity_model.py
│
├── data/
│   └── train.csv
│
├── static/
│   ├── images/
│   ├── js/
│   └── styles/
│
├── templates/
│   ├── main.html
│   └── navbar.html
│
├── theme/
│   ├── *.html
│   ├── assets/
│   └── style.css
│
├── manage.py
├── requirements.txt
└── README.md


---

## 🧩 Installation & Setup

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/Ujwal1121/Final_StudyBuddy.git
cd Final_StudyBuddy

2️⃣ Create Virtual Environment
python3 -m venv venv
source venv/bin/activate

3️⃣ Install Requirements
pip install -r requirements.txt

4️⃣ Run Redis Server

Default:

redis-server


Or on a custom port:

redis-server --port 6375

5️⃣ Migrate the Database
python manage.py makemigrations
python manage.py migrate

6️⃣ Create Superuser
python manage.py createsuperuser

7️⃣ Start the Application
Option A — With WebSockets (recommended)
daphne -b 127.0.0.1 -p 8000 studybud.asgi:application

Option B — Standard Django runserver
python manage.py runserver


Note: runserver will NOT activate real-time WebSockets.
Use Daphne for full chat functionality.

🎥 Demo Video (Add your link)

Upload your demo to:

YouTube

Google Drive

GitHub Releases

Then link it here:

🎬 Demo: https://your-demo-video-link

🖼️ Screenshots (Optional)

You can add your images like this:

![Home Page](assets/home.png)
![Chat Room](assets/chat-room.png)
![Toxic Filter](assets/toxic-detection.png)

📝 License

This project is created for educational and academic use.
Feel free to modify and extend it for personal or portfolio use.

🙌 Acknowledgements

Inspired by the "StudyBud" original project structure

Toxic dataset structure inspired by open-source comment classification datasets

Scikit-learn, Redis, Django, and Channels communities
