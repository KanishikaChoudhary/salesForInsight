# Sales Insight System Setup Guide

This guide explains how to set up and run the Sales Insight System project on a local machine.

## 1. Requirements

Before starting, make sure your system has:

- Python 3.12 installed
- Git installed
- Internet access for installing dependencies
- Windows PowerShell or Command Prompt

> Important: The project dependencies in `requirements.txt` are compatible with Python 3.12. Python 3.14 may cause NumPy import issues.

---

## 2. Clone the Project

Open PowerShell and run:

```powershell
git clone https://github.com/KanishikaChoudhary/salesForInsight.git
cd salesForInsight
```

If you already have the project locally, just go to the project folder:

```powershell
cd "D:\kanishika\SalesInsightSystem"
```

---

## 3. Create a Virtual Environment

Run the following commands:

```powershell
py -3.12 -m venv .venv312
.\.venv312\Scripts\Activate.ps1
```

If the activation script is blocked by PowerShell policy, run:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv312\Scripts\Activate.ps1
```

---

## 4. Install Dependencies

Inside the activated virtual environment, install the required packages:

```powershell
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

This will install:

- Flask
- Flask-SQLAlchemy
- pandas
- numpy
- scikit-learn
- matplotlib
- reportlab

---

## 5. Run the Project

From the project folder, run:

```powershell
python run.py
```

The app should start and display a URL similar to:

```text
http://127.0.0.1:5000
```

Open that URL in your browser.

---

## 6. Default Login Details

The project creates default users automatically when the database is first initialized.

### Admin
- Email: admin@demo.com
- Password: admin123

### User
- Email: user@demo.com
- Password: user123

---

## 7. Project Structure

```text
SalesInsightSystem/
├── app/
│   ├── __init__.py
│   ├── models.py
│   ├── routes.py
│   ├── services.py
│   ├── static/
│   └── templates/
├── data/
│   └── sample_sales.csv
├── instance/
├── README.md
├── requirements.txt
├── run.py
├── .gitignore
├── SETUP.md
└── .venv312/
```

---

## 8. Troubleshooting

### Error: Python 3.14 is installed and NumPy fails

This project is tested with Python 3.12.

Use:

```powershell
py -3.12 -m venv .venv312
.\.venv312\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

### Error: Module not found

Make sure the virtual environment is active before running the project:

```powershell
.\.venv312\Scripts\Activate.ps1
python run.py
```

### Error: Git command not found

Install Git from:

```text
https://git-scm.com/downloads
```

Then reopen PowerShell and continue.

---

## 9. Push to GitHub as a Private Repository

If you want to put this project on GitHub privately:

1. Create a new repository in GitHub
2. Set it to Private
3. Run:

```powershell
git init
git branch -M main
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git push -u origin main
```

If the repository already exists and you just need to connect it:

```powershell
git remote set-url origin https://github.com/<your-username>/<your-repo-name>.git
git push -u origin main
```

---

## 10. Quick Start Summary

```powershell
py -3.12 -m venv .venv312
.\.venv312\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python run.py
```

Then open:

```text
http://127.0.0.1:5000
```

---

## 11. Final Note

This project uses Flask for the web application, SQLite for local data storage, and machine learning for the forecasting functionality. It is suitable for academic and project demonstration use.

If you want to customize the app, update the code in the `app` folder and restart the Flask server.
