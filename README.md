# GRIET-Automated-Result-Portal
# 📊 Student Result Portal with SMS Notification


This is a Django-based web application that is developed for Gokaraju Rangaraju Institute of Engineering and Technology (GRIET) which allows the college staff to view student results from a MySQL database and send automated personalized SMS notifications that includes the subject-wise marks using Twilio API.

## 🚀 Features

- Dynamic filtering of students by **branch** and **section**
- Select specific students and send result SMS
- SMS content is dynamically generated based on subject marks
- Status indicators for each student: ✅ Sent / ❌ Failed
- Modular architecture and environment variable support for credentials

---

## 📂 Project Structure (Highlights)

```

student-result-portal/
├── studentapp/
│   ├── templates/
│   │   └── students\_table.html
│   ├── models.py
│   ├── views.py
├── static/
│   └── aac\_logo.png   # <- Not tracked by Git. See below.
├── .env               # <- Must be created manually (see setup)
├── db.sqlite3 / MySQL (used based on settings)
├── settings.py        # <- Requires DB config updates
└── manage.py

````

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/student-result-portal.git
cd student-result-portal
````

### 2. Create & Activate Virtual Environment

```bash
python -m venv env
# For Windows:
env\Scripts\activate
# For Mac/Linux:
source env/bin/activate
```

### 3. Install Requirements

```bash
pip install -r requirements.txt
```

### 4. Create `.env` File

You need to manually create a `.env` file in the root folder and add your Twilio credentials in the following format:

```env
TWILIO_ACCOUNT_SID=your_account_sid_here
TWILIO_AUTH_TOKEN=your_auth_token_here
TWILIO_PHONE_NUMBER=+91XXXXXXXXXX
```

### 5. Set Up the Database

Update your MySQL database credentials in `settings.py`:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'your_db_name',
        'USER': 'your_mysql_username',
        'PASSWORD': 'your_mysql_password',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

### 6. Apply Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### 7. Run the Server

```bash
python manage.py runserver
```

---

## 🖼️ Static Files and Media

> ⚠️ The `aac_logo.png` file is not pushed to the Git repository (ignored via `.gitignore`). Please add it manually inside the `static/` folder.

---

## 📞 Twilio SMS Format

SMS sent will look like:

```
Hello John Doe (23241A0547), your results for JNR_CORE are: Subject1: 85, Subject2: 77, Subject3: 91.
```

If phone number does not start with `+91`, it will be auto-formatted.

---

## ✅ To-Do / Enhancements

* Add admin login panel
* Export student results to Excel
* Add SMS sending logs dashboard

---

## 📜 License

This project is for educational/demo purposes. You may modify and reuse it freely.

````

---

## 📦 `requirements.txt`

Here’s a basic `requirements.txt` you can include in the root of your repo:

```txt
Django>=4.2,<5.2
mysqlclient>=2.2.0
twilio>=8.10.0
python-dotenv>=1.0.0
````

You can generate your exact versions using:

```bash
pip freeze > requirements.txt
```




## Sample Web-Architecture Demonstration Images
Step 1:- Selection of the name of the exam:-

![image](https://github.com/user-attachments/assets/c96f77f8-5525-4f71-8402-baae1c37879f)


Step 2:- Select the Branch and Section:-

![image](https://github.com/user-attachments/assets/896a53bb-9cb8-488d-8fd4-82a23f1988d5)

Step 3:- The details of all the students who are present in that particualr branch and sectiona are being displayed:-

![image](https://github.com/user-attachments/assets/90a8cce4-46e9-4c94-8288-9ed68fab34ba)


Step 4:- Select the student to whom the result SMS has to be sent:-

![image](https://github.com/user-attachments/assets/faf7a9fe-de17-491c-9bae-a6f087d1b621)


Step 5:- Click the "Send Message" button to send the results to their respective parent's mobile number:-

![image](https://github.com/user-attachments/assets/55c83b4e-50b6-44ef-b9e7-f421d93b4b6c)


Step 6:- The SMS with the student name, rollnumber, exam name and marks are being displayed as below:-

![WhatsApp Image 2025-06-15 at 14 56 41_b603abcf](https://github.com/user-attachments/assets/1df47157-c0bc-4904-a184-a42701443b06)
