# LuminaLearn User Interface

Student quiz interface and teacher analytics dashboard for the
AI-Powered Adaptive Learning System.

**Live URLs:** - **Frontend**: https://lumina-ui-topaz.vercel.app -
**Backend API**:               https://lumina-learn-five.vercel.app - **Backend
Docs**:                        https://lumina-learn-five.vercel.app/docs

------------------------------------------------------------------------

## 🎨 Features

-   **Student Quiz Interface**: AI-generated questions with real-time
    feedback
-   **Adaptive Learning**: Questions adjust to student performance
-   **AI Feedback**: Personalized explanations for correct/incorrect
    answers
-   **Hint System**: Contextual guidance without revealing answers
-   **Teacher Dashboard**: Real-time analytics on student performance
-   **Visual Analytics**: Chart.js visualizations of class progress
-   **AI Teaching Insights**: Automated recommendations for struggling
    students

------------------------------------------------------------------------

## 📁 Project Structure

    frontend/
    ├── index.html              # Student quiz interface
    ├── teacher-dashboard.html  # Teacher analytics view
    ├── vercel.json             # Vercel routing configuration
    ├── js/
    │   ├── api.js              # Backend API client
    │   ├── student.js          # Student view logic
    │   └── dashboard.js        # Teacher dashboard logic
    └── README.md               # This file

------------------------------------------------------------------------

## 🛠️ Technology Stack

  Component     Technology                        Purpose
  ------------- --------------------------------- -----------------------------
  Styling       Tailwind CSS                      Utility-first CSS framework
  Icons         Phosphor Icons (via SVG)          Consistent iconography
  Charts        Chart.js                          Performance visualizations
  Fonts         Google Fonts (Inter, Noto Sans)   Typography
  HTTP Client   Vanilla Fetch API                 Backend communication
  Hosting       Vercel                            Static site deployment

------------------------------------------------------------------------

## 🚀 Deployment

### Live Deployment

This frontend is deployed separately from the backend at: -
**Production**: https://lumina-ui-topaz.vercel.app

### Backend Connection

The frontend connects to the backend API at:

``` javascript
// js/api.js
const API_BASE_URL = 'https://lumina-learn-five.vercel.app';
```

------------------------------------------------------------------------

## 🔌 API Integration

All API calls go to the separate backend service:

  Endpoint                        Method   Description
  ------------------------------- -------- ---------------------------
  /api/students                   POST     Create new student
  /api/submit-answer              POST     Submit quiz answer
  /api/generate-question          POST     Get AI-generated question
  /api/student-progress/{id}      GET      Get student progress
  /api/analytics/class-overview   GET      Get class analytics
  /api/analytics/struggling       GET      Get struggling students

### Example usage:

``` javascript
const result = await api.submitAnswer({
    student_id: 1,
    topic: "Mathematics",
    question: "What is 2+2?",
    correct_answer: "4",
    student_answer: "4",
    time_taken_seconds: 5
});

// Returns: { is_correct: true, feedback: "AI-generated response..." }
```

------------------------------------------------------------------------

## 📝 Configuration

### Updating Backend URL

If the backend URL changes, update `js/api.js`:

``` javascript
const API_BASE_URL = 'https://your-new-backend-url.vercel.app';
```

### CORS Requirements

The backend must include this frontend URL in its CORS allow_origins:

``` python
# backend/main.py
allow_origins=[
    "https://lumina-ui-topaz.vercel.app",
]
```

------------------------------------------------------------------------

## 🐛 Troubleshooting

### Failed to Fetch / CORS Errors

**Cause:** Backend CORS doesn't allow frontend domain\
**Fix:** Add https://lumina-ui-topaz.vercel.app to backend CORS
settings

### 404 Errors on Refresh

**Cause:** Vercel routing issue\
**Fix:** Ensure vercel.json includes:

``` json
{
  "handle": "filesystem"
}
```

### API Not Responding

Check backend health endpoint:
https://lumina-learn-five.vercel.app/api/health

Should return:

``` json
{"status": "healthy"}
```

------------------------------------------------------------------------

## 📊 Browser Compatibility

  Browser         Support
  --------------- ---------
  Chrome 90+      ✅ Full
  Firefox 88+     ✅ Full
  Safari 14+      ✅ Full
  Edge 90+        ✅ Full
  Mobile Chrome   ✅ Full
  Mobile Safari   ✅ Full

------------------------------------------------------------------------

## 🔒 Security Notes

-   No authentication: Demo version; add auth for production
-   CORS restricted: Backend only allows specific origins
-   API Keys: Stored in backend only (never expose in frontend)
-   HTTPS: Required for secure communication

------------------------------------------------------------------------

## 🚀 Local Development

``` bash
# Serve locally
python -m http.server 3000

# Or use VS Code "Live Server" extension
```

Update `js/api.js` for local testing:

``` javascript
const API_BASE_URL = 'http://localhost:8000';
```

------------------------------------------------------------------------

**Contributor:** Felix Amenya Kenyansa
**Project:** Final Data Science Project --- Cohort 5 LUXTECH

------------------------------------------------------------------------

## 🆘 Support

-   Frontend: https://lumina-ui-topaz.vercel.app
-   Backend: https://lumina-learn-five.vercel.app
-   Docs: https://lumina-learn-five.vercel.app/docs
