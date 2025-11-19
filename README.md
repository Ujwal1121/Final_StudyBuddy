# 📚 Final StudyBuddy — A Real-Time Collaborative Learning Platform

**Final StudyBuddy** is a real-time collaboration platform built using **Django**, **Django Channels**, **Redis**, and **Machine Learning** for **toxic message detection**.  
Users can join study rooms, chat instantly, discuss topics, and collaborate with real-time WebSockets.

This project showcases:
- 🧠 ML-based toxic message detection  
- 🔥 Real-time chat using Django Channels + Redis  
- 🎨 Custom UI built with modern frontend styling  
- 👥 Room-based collaboration & user profiles  
- 📁 Clean project structure with production-ready code  

---

## 🚀 Features

### 🌐 **Real-Time Chat**
- Built with **WebSockets**
- Powered by **Daphne** + **Redis**
- No page refresh required

### 🤖 **Machine Learning Toxicity Detection**
- Custom-trained ML model (`toxicity_model.pkl`)
- Blocks harmful messages
- Auto-sanitizes or replaces toxic content
- Prevents saving toxic messages to the database

### 🧑‍💻 **User Authentication**
- Sign up, Login, Profile Update
- Admin panel to manage users, rooms, topics, and messages

### 🏷️ **Rooms & Topics**
- Users can create public rooms
- Join and collaborate with others
- Search posts and topics easily

### 📱 **Responsive UI**
- Clean and minimal design
- Flexible styling for mobile & desktop

---

## 📁 Project Directory Structure

Below is the structure of the project:

![Project Structure](project_structure.png)

> Make sure the file `project_structure.png` exists in the root of the repo.

---

## 🧠 ML Model Details

### Toxicity Detection Includes:
- Offensive language  
- Insults  
- Threats  
- Identity hate terms  

### Model Trained Using:
- TF-IDF Vectorizer  
- Logistic Regression Classifier  
- Training script in `ml/train_toxicity_model.py`

### Runtime Filtering:
Chat messages pass through:
1. **Model prediction**
2. **Keyword blacklist filtering**
3. **Message sanitization**

If toxic → blocked or auto-modified before saving to DB.

---

## 🛠️ Tech Stack

### Backend
- Python 3.9+
- Django 4.2
- Django REST Framework
- Django Channels 4.0
- Daphne
- Redis Server

### Machine Learning
- scikit-learn  
- pandas  
- numpy  
- pickle model loading

### Frontend
- HTML  
- CSS  
- JavaScript  

---

## 📦 Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/Ujwal1121/Final_StudyBuddy.git
cd Final_StudyBuddy
2️⃣ Create & Activate Virtual Environment
python3 -m venv venv
source venv/bin/activate

3️⃣ Install Requirements
pip install -r requirements.txt

4️⃣ Run Redis Server
redis-server --port 6375


Or default port:

redis-server

5️⃣ Run Django Migrations
python manage.py migrate

6️⃣ Start Development Server

Backend server:

python manage.py runserver


WebSockets with Daphne:

daphne -p 8000 studybud.asgi:application

🧪 Testing Toxicity Detection

Try entering messages such as:

Allowed
✔️ “What topic are we discussing today?”
✔️ “Can you help me with AI?”

Blocked / sanitized
❌ “You are such an idiot”
❌ “Go kill yourself”

👤 Author

Ujwal Warad
GitHub: https://github.com/Ujwal1121

📜 License

This project is for educational and academic use.
