# Disaster Management Aggregation Software

![Disaster Management](https://img.shields.io/badge/Disaster%20Management-Real%20Time%20Alerts-blue.svg) ![License](https://img.shields.io/badge/License-MIT-green.svg)

## Overview
Disaster Management Aggregation Software is an open-source platform designed to provide real-time detection, monitoring, and notification of natural disasters like earthquakes, floods, wildfires, and storms. This software aggregates data from multiple sources, processes it using machine learning models, and generates actionable insights to assist in emergency response and disaster management.

### Features
- **Real-Time Data Aggregation**: Collects disaster data from APIs, satellite images, and IoT sensors.
- **Machine Learning Models**: Uses Convolutional Neural Networks (CNNs) for image-based detection (e.g., flooded areas) and Recurrent Neural Networks (RNNs) for time-series data (e.g., seismic activity).
- **Automated Alerts**: Sends notifications via email or SMS when a disaster is detected.
- **Dashboard Interface**: Interactive dashboard to monitor detected events and view data visualizations.

## Table of Contents
1. [Installation](#installation)
2. [Configuration](#configuration)
3. [Usage](#usage)
4. [Project Structure](#project-structure)
5. [Contributing](#contributing)
6. [License](#license)

---

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/disaster-management-aggregation.git
   cd disaster-management-aggregation
   ```

2. **Set Up Environment**:
   - Install Python 3.8 or above.
   - Create a virtual environment:
     ```bash
     python3 -m venv venv
     source venv/bin/activate  # For Linux/Mac
     venv\Scripts\activate     # For Windows
     ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Download Pre-trained Models** (Optional):
   - If using pre-trained models, download and save them to `models/` folder.

## Configuration

1. **Environment Variables**:
   - Create a `.env` file in the project root directory with the following:
     ```
     API_KEY=your_data_source_api_key
     ALERT_EMAIL=your_alert_email@example.com
     ALERT_PHONE=your_phone_number
     ```

2. **Custom Settings**:
   - Adjust settings in `config.json` for model paths, alert thresholds, and data refresh intervals.

## Usage

1. **Start the Data Aggregation Service**:
   ```bash
   python main.py
   ```

2. **Access the Dashboard**:
   - Open your web browser and navigate to `http://localhost:5000` to view the interactive dashboard.

3. **Triggering Alerts**:
   - Alerts are triggered automatically when a disaster is detected based on predefined thresholds.
   - Notifications are sent via SMS/email to the configured contacts.

4. **Running ML Models**:
   - CNN models for image analysis are in `models/cnn_model.py`, and RNN models for time-series analysis are in `models/rnn_model.py`.
   - Train or fine-tune models by running:
     ```bash
     python train_model.py --model cnn --data images/
     ```

## Project Structure

```
disaster-management-aggregation/
├── data/               # Raw data and preprocessed data
├── models/             # Machine learning models (CNN, RNN)
├── notebooks/          # Jupyter notebooks for exploratory data analysis
├── src/
│   ├── data_aggregation.py    # Collects data from sources
│   ├── preprocess.py          # Preprocesses raw data
│   ├── detection.py           # Runs detection models
│   └── alert_system.py        # Sends email/SMS alerts
├── templates/          # HTML templates for the web dashboard
├── config.json         # Configuration settings
├── main.py             # Main application entry point
├── README.md
├── requirements.txt    # Dependencies
└── .env                # Environment variables
```

## Contributing

We welcome contributions! Here’s how you can help:

1. **Fork** the repository and **clone** your fork locally.
2. **Create a new branch** for your feature or fix:
   ```bash
   git checkout -b feature-branch
   ```
3. **Commit** your changes and **push** to your fork.
4. Open a **Pull Request** in the original repository with a description of your changes.

Please read our [CONTRIBUTING.md](CONTRIBUTING.md) for more details on our code of conduct and the process for submitting pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
