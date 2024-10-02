
Here’s the complete README.md file for your log processing web app:

Log Processor Web Application
This project is a web application for processing device log files. It allows users to upload log files, search for specific sentences within the logs, and display statistics such as the number of lines and occurrences of the target sentence. The processed logs are stored in a Django backend, and the frontend is built using React.

Features:

Upload log files 
Input a custom sentence to search for within the log file
Display total lines and occurrences of the target sentence
Save processed logs in the database
View a list of previously processed logs

Tech Stack:

Backend (Django)
Django: Web framework for building the backend.
Django REST Framework: Used to create the API for the frontend to interact with.
PostgreSQL: Database used for storing logs.
Celery: For handling background tasks.
django-cors-headers: To allow cross-origin requests from the React frontend.
Frontend (React)
React: The framework for building the user interface.
Axios: Used to make HTTP requests to the backend.
HTML5 & CSS: Basic styling for the frontend.

Project Structure:

Backend (Django)
Log_processor/
│
├── backend/                   # Backend (Django) files
│   ├── logs/                     # App for handling log-related features
│   │   ├── models.py              # Defines the Log model
│   │   ├── views.py               # API views for processing logs
│   │   ├── serializers.py         # Serializers for log processing
│   │   └── urls.py                # URL routing for logs
│   ├── log_processor_backend/     # Main Django project folder
│   │   ├── settings.py            # Django project settings
│   │   └── urls.py                # Root URL configurations
│   ├── manage.py                  # Django entry point
│   ├── requirements.txt           # Project dependencies
│   └── README.md                  # Backend README file
│
├── frontend/                  # Frontend (React) files
│   ├── public/                    # Static files
│   │   ├── index.html             # Main HTML file
│   ├── src/                       # React source files
│   │   ├── components/            # Reusable components
│   │   │   ├── UploadForm.jsx      # Form to handle log file upload
│   │   │   └── LogList.jsx         # Displays processed logs
│   │   ├── App.js                 # Main app component
│   │   └── index.js               # Entry point of the React app
│   ├── package.json               # Frontend dependencies
│   └── README.md                  # Frontend README file
├── README.md                  # Main project README file
└── LICENSE                    # Project license


Installation
Prerequisites
Node.js: Required for running the frontend (React).
Python 3.8+: Required for running the Django backend.
PostgreSQL: The database used by Django.

Backend Setup (Django)
1. Clone the repository:
https://github.com/Ephyz8/Log_processor
cd Log_processor/backend

2. Create and activate a virtual environment:
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

3. Install dependencies:
pip install -r requirements.txt

4. Set up the database (PostgreSQL): Create a PostgreSQL database and configure the connection in settings.py:
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'your_db_name',
        'USER': 'your_db_user',
        'PASSWORD': 'your_db_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}

5. Apply migrations and create a superuser:
python manage.py migrate
python manage.py createsuperuser

6. Run the backend server:
python manage.py runserver

Frontend Setup (React)

1. Navigate to the frontend directory:
cd ../frontend

2. Install dependencies:
npm install

3. Run the frontend:
Run the frontend:
npm start

The frontend should be available at http://localhost:3000.

API Endpoints
Upload Log File
URL: /api/logs/upload/
Method: POST
Description: Uploads a log file and processes it for the specified sentence.
Request Body:
file: Log file to be uploaded.
target_sentence: Sentence to search for in the log file.
Response: JSON with file details, total lines, occurrences of the sentence, and occurrence details.
Get Processed Logs
URL: /api/logs/
Method: GET
Description: Retrieves all processed logs.
Response: List of processed logs.

Contributing
Fork the project.
Create your feature branch (git checkout -b feature/new-feature).
Commit your changes (git commit -m 'Add new feature').
Push to the branch (git push origin feature/new-feature).
Open a pull request.
License
This project is licensed under the MIT License. See the LICENSE file for details.