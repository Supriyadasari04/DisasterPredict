# 🌍 Predictive Natural Disaster Management System

DisasterPredict is a full-stack web application that leverages AI to predict natural disasters, display real-time news and satellite data, and facilitate donations to affected areas. It's designed for governments, NGOs, and individuals to stay informed and act quickly.

## 🔗 Live Demo

- **Frontend** (Vercel): [https://disasterpredict.vercel.app](https://disasterpredict.vercel.app)  
- **Backend** (Render): [Deployed via Render](https://dashboard.render.com/)

---

## 📌 Features

- 🔮 **AI-Powered Disaster Prediction**
- 📰 **Real-Time News Aggregation** from NewsAPI and The Guardian
- 🗺️ **Interactive Map** using Leaflet and NASA APIs
- 💸 **Donation Management System**
- 👥 **User Authentication** (Login / Signup for contributors and donors)
- 🚀 **Caching** of external API data to reduce redundant calls

---

## 🛠️ Tech Stack

### Frontend
- React (Vite)
- Tailwind CSS
- Leaflet.js (for maps)
- NASA Earth Imagery API (satellite visuals)

### Backend
- Flask (Python)
- MySQL (hosted on Railway)
- Flask-Caching
- Gunicorn (for deployment)
- Render (deployment platform)

---

## 🧪 ML Models (Backend)
- Trained Random Forest model for disaster prediction
- Encoded & scaled inputs: `country`, `disaster type`, `magnitude scale`, etc.
- Uses joblib for loading:
  - `random_forest_model.joblib`
  - Encoders & scaler for preprocessing

---

## ⚙️ Setup Instructions

### 🔧 Backend Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/DisasterPredict.git
   cd DisasterPredict/backend
   ```

2. **Create virtual environment and install dependencies**
   ```bash
   python -m venv venv
   source venv/bin/activate  # or venv\Scripts\activate on Windows
   pip install -r requirements.txt
   ```

3. **Create `.env` file**
   ```bash
   cp .env.example .env
   ```

4. **Run the Flask server locally**
   ```bash
   python app.py
   ```

### 🌐 Frontend Setup

1. Go to frontend directory:
   ```bash
   cd ../frontend
   ```

2. Install packages:
   ```bash
   npm install
   ```

3. Run locally:
   ```bash
   npm run dev
   ```

---

## 📁 Project Structure

```
DisasterPredict/
├── backend/
│   ├── app.py
│   ├── config.py
│   ├── models/
│   ├── routes/
│   ├── services/
│   ├── ml/ (Model + Encoders)
│   └── requirements.txt
├── frontend/
│   ├── src/
│   ├── public/
│   └── vite.config.js
```

---

## 🧠 Caching Strategy

To reduce API calls (especially from NewsAPI and The Guardian), Flask-Caching is used:
- News results are memoized for 1 hour.
- Deployed backend supports proper caching via `SimpleCache`.

---

## 🧪 API Endpoints

- `GET /api/disaster-news?limit=5&query=earthquake`  
- `POST /api/predict` – Predicts likelihood of a disaster  
- `POST /api/donate` – Submit donation  
- `GET /api/health` – Health check endpoint

---

## 🏁 Future Scope

- Integrate SMS alerts for early warnings
- Expand model training datasets
- Add admin dashboard to verify donations

---

## 📜 License

MIT License. See `LICENSE` for more details.
