# AdFraud — Real-Time Ad Click Fraud Detection

Final-year major project (B.E. Computer Engineering, Rizvi College of Engineering, University of Mumbai, 2025–26) for detecting fraudulent ad clicks in mobile advertising with machine learning, deep learning and an explainable, real-time monitoring platform.

**Research paper:** [AdFraud System: Real-Time Ad Click Fraud Detection Using Stacking Ensemble, Deep Learning, and an Agentic AI Chatbot — IJRSI, 2026](https://rsisinternational.org/journals/ijrsi/view/adfraud-system-real-time-ad-click-fraud-detection-using-stacking-ensemble-deep-learning-and-an-agentic-ai-chatbot)

---

## Overview

Click fraud drains advertising budgets through bots, click farms and spoofed devices. This system classifies each ad click as legitimate or fraudulent using click metadata (IP, app, device, OS, channel, timestamps) and engineered behavioural signals.

| | |
|---|---|
| **Models** | Logistic Regression, Random Forest, SVM, XGBoost, LightGBM; ANN, CNN, LSTM, GRU |
| **Final model** | Stacking ensemble (Logistic Regression, Random Forest, XGBoost, LightGBM) |
| **Reported results** | 97.4% accuracy · 0.98 AUC · 96.8% F1 (as published in the paper) |
| **Features** | 18 engineered fraud signals (click bursts, inter-click interval, geo switching, subnet patterns, UA spoofing, CTR anomalies, …) |
| **Explainability** | SHAP |
| **Serving** | Flask REST API (`/api/predict`, `/api/track`, `/api/stream` via Server-Sent Events) |
| **Assistant** | LLM-powered chatbot for fraud analysis |
| **Dataset** | [TalkingData AdTracking Fraud Detection (Kaggle)](https://www.kaggle.com/competitions/talkingdata-adtracking-fraud-detection) |

## ShopNova — live fraud simulation

`shopnova.html` is a simulated e-commerce site connected to the Flask backend. Click normally to generate legitimate traffic, or drag the "bot ball" / trigger attack patterns to generate fraud and watch the dashboard flag it in real time.

## Run locally

```bash
cd "fraud detection"
pip install -r requirements.txt
# download GeoLite2-Country.mmdb from MaxMind and place it in this folder
python app.py            # http://127.0.0.1:5000
```

Or with Docker: `docker compose up`.

## Team

- **Omkar Maruti Sawant** — team lead, model development and platform
- **Shrikar Vidyasagar Gujjeti** — research paper co-author, project report and technical documentation
- **Nikhil Kanti Jain**

Guides: Prof. Manila Gupta (primary), Prof. Ramya Prabhakaran

## License

MIT — see [LICENSE](LICENSE).
