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
