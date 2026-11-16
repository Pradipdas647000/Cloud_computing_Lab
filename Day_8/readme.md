# Cloud Computing Lab 8: Google App Engine (PaaS)

## Overview
This repository contains the code and configuration files for Cloud Computing Lab 8. The primary aim of this experiment is to explore Platform as a Service (PaaS) by developing, deploying, and managing a simple Python web application using **Google App Engine**.

## Project Structure
* `main.py`: The main Python application file using the Flask web framework.
* `requirements.txt`: Lists the Python dependencies required for the application (Flask).
* `app.yaml`: The Google App Engine configuration file specifying the runtime environment.

## Prerequisites
Before you begin, ensure you have the following installed and set up:
* Python 3.x
* [Google Cloud CLI (`gcloud`)](https://cloud.google.com/sdk/docs/install)
* An active Google Cloud Project with App Engine initialized.

## Local Development and Testing (Task 2)

1. **Clone or create the application directory:**
   ```bash
   mkdir cloud-lab8
   cd cloud-lab8
   ```

2. **Install the required dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
   *(Note: You can also just run `pip install Flask`)*

3. **Run the application locally:**
   ```bash
   python main.py
   ```

4. **Access the application:**
   Open your web browser and navigate to `http://127.0.0.1:8080`.

## Deployment to Google App Engine (Task 3)

1. **Authenticate with Google Cloud:**
   ```bash
   gcloud auth login
   ```

2. **Set your Google Cloud Project:**
   ```bash
   gcloud config set project YOUR_PROJECT_ID
   ```
   *(Replace `YOUR_PROJECT_ID` with your actual Google Cloud Project ID)*

3. **Deploy the application:**
   Ensure you are in the directory containing `app.yaml` and run:
   ```bash
   gcloud app deploy
   ```

4. **Browse the deployed application:**
   ```bash
   gcloud app browse
   ```

## Application Management & Monitoring (Task 4)

Once deployed, you can manage your App Engine application using the following `gcloud` commands or via the Google Cloud Console:

* **List Application Versions:**
  ```bash
  gcloud app versions list
  ```
* **View Application Logs (Real-time):**
  ```bash
  gcloud app logs tail
  ```
* **Update the Application:**
  To deploy a new version, simply make your changes in `main.py`, save the file, and rerun the `gcloud app deploy` command. App Engine will automatically manage the versioning.