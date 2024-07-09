# **Flight Fare Prediction**

## **Overview**
- This project is a web application that predicts the fare of a flight based on various input features provided by the user. The application is built using Flask for the backend and employs a Random Forest model for the prediction, which has been trained on historical flight data

## **Features**
- Predicts flight fare based on user inputs.
- User inputs include date and time of journey, departure and arrival times, number of stops, airline, source, and destination.
- Utilizes a pre-trained Random Forest model for accurate predictions.

## **How It Works**
1. User Input: The user provides details about their journey through a web form, including:

- Date and time of departure and arrival
- Number of stops
- Airline
- Source and destination
2. Data Processing: The application processes the input data:

- Extracts day and month from the date of journey
- Extracts hours and minutes from the departure and arrival times
- Calculates the duration of the flight in hours and minutes
- Encodes categorical features such as airline, source, and destination
3. Model Prediction: The processed data is fed into the pre-trained Random Forest model to predict the flight fare.

4. Output: The predicted fare is displayed to the user on the web page.

## **Technologies Used**

- **Flask** : A lightweight WSGI web application framework in Python.
- **Scikit-Learn** : A machine learning library in Python, used for building and training the Random Forest model.
- **Pandas** : A data manipulation library in Python, used for data processing.
- **NumPy** : A library for numerical computations in Python, used for handling arrays.
- **HTML/CSS** : For designing the web interface.
- **Flask-CORS** : To handle Cross-Origin Resource Sharing (CORS).

## **Project Structure**
- app.py: The main Flask application file.
- model/flight_rf.pkl: The pre-trained Random Forest model serialized using pickle.
- templates/home.html: The HTML template for the home page.

## **Usage**
- Ensure all dependencies are installed. You can use the following command to install the required Python packages: 

    ```bash
    pip install -r requirements.txt


## **Run the Flask application:**
- Run your python file using :
    ```bash  
    python app.py

## **Installation**

1. Clone the repository:
   ```bash
   git clone https://github.com/abuawaish/final_project_pw.git

- Open a web browser and go to http://192.168.206.14:5000 to access the application.
- Fill in the journey details in the form and submit to get the predicted flight fare.

# **Future Improvements**

- Add more features to improve prediction accuracy.
- Implement user authentication and save past searches.
- Enhance the UI for a better user experience.
- Expand the model to include more airlines and routes.

## **License**

- This project is licensed under the MIT License.

## **Acknowledgments**

- The dataset used for training the model was obtained from Kaggle - [https://www.kaggle.com/datasets/nikhilmittal/flight-fare-prediction-mh].
- Inspiration for the project from various online tutorials and courses.

## **Screenshots**

- Here is a screenshot of the application:
- 1. Application Screenshot - [https://drive.google.com/file/d/1fhoBl2it7Udt7o7YcgjLO5Akiar1_0i7/view?usp=sharing]
- 2. Application Screenshot - [https://drive.google.com/file/d/1D5Z87WS_rlTD9RitH3HhnZtQ_YBZeLJk/view?usp=sharing]

## **Video Demo**

- Watch a demo of the application in action:

[![Watch the video](https://data.textstudio.com/output/sample/animated/1/3/0/5/demonstration-3-15031.gif)](https://drive.google.com/file/d/1AKgPkT8s3Mrb75x8QQN7mFf3t8_-G9ln/view?usp=sharing)


