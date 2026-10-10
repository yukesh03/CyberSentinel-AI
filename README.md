# 🛡️ CyberSentinel AI
### AI-Powered Network Traffic Anomaly Detection

CyberSentinel AI is a machine-learning-based network traffic analysis dashboard that identifies unusual network activity using the **Isolation Forest** algorithm. Built with Python and Streamlit, it provides an interactive interface for analyzing network traffic records, reviewing suspicious patterns, visualizing anomalies, and exporting investigation reports.

This project demonstrates the application of machine learning and data visualization to cybersecurity monitoring.

> **Disclaimer:** CyberSentinel AI is an educational research prototype. It analyzes traffic-flow records and flags statistical anomalies; it is not a replacement for a production IDS/IPS or a real-time packet monitoring system.

## ✨ Features

- **Interactive security dashboard:** View network traffic analysis results in a modern interface.
- **Machine learning detection:** Uses the Isolation Forest algorithm to identify unusual traffic patterns.
- **Traffic classification:** Summarizes records classified as normal or anomalous.
- **Interactive visualizations:** Explore traffic classification and anomaly score distributions.
- **CSV upload:** Analyze your own network traffic datasets.
- **Investigation table:** Search, filter, and sort traffic records for further investigation.
- **Priority indicators:** Review records flagged for investigation.
- **CSV report export:** Download analysis results for further examination.
- **Synthetic data generation:** Generate sample traffic data for testing without needing a live network capture.

## 🧰 Technology Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Streamlit | Interactive web dashboard |
| Pandas | Data processing and manipulation |
| NumPy | Numerical operations |
| Scikit-learn | Isolation Forest anomaly detection |
| Plotly | Interactive charts |
| Pytest | Automated testing |

## 🏗️ Project Architecture

```text
CyberSentinel-AI/
│
├── app.py                 # Streamlit dashboard
├── detector.py            # ML anomaly detection
├── generate_data.py       # Synthetic traffic generation
├── requirements.txt       # Python dependencies
├── README.md              # Project documentation
├── .gitignore             # Files excluded from Git
│
├── tests/
│   └── test_detector.py   # Automated tests
│
└── sample_data/
    └── cybersentinel_network_traffic_demo.csv
```

## ⚙️ Requirements

Before starting, install:

- Python 3.10 or later
- Git
- Visual Studio Code (recommended)
- A modern web browser

Python 3.11 is a suitable choice for this project.

## 🚀 Installation and Setup

### 1. Clone the repository

Open a terminal and run:

```bash
git clone https://github.com/YOUR_USERNAME/CyberSentinel-AI.git
cd CyberSentinel-AI
```

Replace `YOUR_USERNAME` with your GitHub username.

### 2. Create a virtual environment

**Windows PowerShell:**

```powershell
python -m venv .venv
```

Activate the environment:

```powershell
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, you can use Command Prompt instead:

```bat
.venv\Scripts\activate.bat
```

### 3. Install dependencies

Upgrade pip and install the required packages:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Launch the application

Run:

```bash
python -m streamlit run app.py
```

Open the local URL shown in your terminal. By default, Streamlit uses:

```text
http://localhost:8501
```

The dashboard should open in your browser.

## 📊 Using the Dashboard

1. Launch CyberSentinel AI.
2. Choose whether to use the generated demo data or upload a CSV file.
3. Adjust the expected anomaly proportion in the sidebar.
4. Review the security overview metrics.
5. Explore the traffic classification chart and anomaly score distribution.
6. Filter flagged records and search investigation indicators.
7. Download the filtered analysis report as a CSV file.

### Uploading a CSV dataset

Your CSV must contain the following numeric feature columns:

| Column | Description |
|---|---|
| `flow_duration` | Duration of the network flow |
| `total_packets` | Total packets in the flow |
| `total_bytes` | Total bytes transferred |
| `packet_rate` | Packets per unit of flow duration |
| `bytes_per_packet` | Average bytes per packet |
| `failed_logins` | Number of failed login attempts |

Additional columns, such as timestamps, IP addresses, protocol, destination port, and labels, can be included for investigation and reporting.

The detector uses the six numeric feature columns listed above. The `label` column is not used as the model's ground-truth target.

## 🧠 How the Detection Works

CyberSentinel AI uses **Isolation Forest**, an unsupervised machine-learning algorithm.

1. Network traffic records are loaded from a generated dataset or an uploaded CSV.
2. The required numeric features are selected and prepared.
3. The Isolation Forest model is fitted to the traffic records.
4. Records classified as unusual are flagged for review.
5. Anomaly scores, indicators, and priority information are displayed in the dashboard.
6. Results can be exported for further investigation.

The expected anomaly proportion (`contamination`) influences the model's decision threshold. A flagged record is not necessarily malicious, and legitimate traffic can also be flagged.

## 🧪 Sample Dataset

A synthetic sample dataset is provided in `sample_data/` for testing the upload functionality.

It contains example traffic records with timestamps, IP addresses, protocols, ports, flow statistics, and illustrative labels.

The dataset is synthetic and does not represent actual network traffic. Its labels are included for demonstration and are not used to train the Isolation Forest model.

## 🧑‍💻 Running Tests

If the `tests/test_detector.py` test file is included in the repository, run:

```bash
python -m pytest -v
```

Tests validate the detector's expected behavior. Ensure that the test dependencies are installed through `requirements.txt`.

## 🔒 Security and Privacy

- Run the project locally unless you intentionally configure a deployment.
- Use sanitized network logs when testing with real traffic.
- Avoid uploading confidential IP addresses, user information, credentials, or sensitive organizational data to a public repository.
- Do not commit virtual environments, secrets, or private datasets.
- Review flagged records before taking security-related action.

## ⚠️ Limitations

- The project analyzes existing CSV traffic records; it does not capture live packets directly.
- Isolation Forest detects statistical outliers, not confirmed attacks.
- Results depend on the quality and distribution of the input data.
- The synthetic dataset is intended for demonstration, not production security evaluation.
- This prototype does not automatically block connections or respond to incidents.

## 🔮 Future Enhancements

- Live network traffic collection and flow extraction
- Real-time anomaly monitoring
- Integration with Zeek or Suricata logs
- Historical trend analysis and alert notifications
- Model evaluation using labeled benchmark datasets
- Authentication and role-based access control
- Deployment with Docker or a cloud hosting platform

## 👨‍💻 Author

**Yukeshwaran S.**

- GitHub: [@yukesh03](https://github.com/yukesh03)
- LinkedIn: [Yukeshwaran](https://www.linkedin.com/in/yukesh-waran-815aa3369/)

## 📄 License

This project is available under the MIT License if you choose to distribute it under that license. Add a `LICENSE` file to the repository before claiming that the project is MIT-licensed.

---

**CyberSentinel AI — Machine learning for network traffic investigation.**
