# **Flight Fare Prediction**

## **High-Level Design (HLD)**
## **Overview**

- This project is a web application that predicts the fare of a flight based on various input features provided by the user. The application is built using Flask for the backend and employs a Random Forest model for the prediction, which has been trained on historical flight data

## **User Interface (UI)**

- **Home Page** : A form for users to input flight details (departure time, arrival time, stops, airline, source, destination).
- **Prediction Page** : Displays the predicted flight fare based on the user inputs.

## **Backend**

- **Flask Application** : Handles HTTP requests, processes user inputs, interacts with the database, and returns predictions.
- **Prediction Model** : A pre-trained Random Forest model serialized using pickle.
- **Database** : Stores user inputs and prediction results.

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

## **Low-Level Design (LLD)**
## **Detailed Components**

## **1. Flask Application (app.py)**
### **Routes** :

- **home()** : Renders the home page with the input form.
- **predict()** : Handles form submission, processes inputs, makes predictions, stores data in the database, and renders the result.

### **Functions** :

- **process_input()** : Extracts and processes date, time, and categorical features from user inputs.
- **make_prediction()** : Uses the pre-trained model to predict the flight fare.
- **store_data()** : Stores user inputs and prediction result in the database.

## **2. Templates**

- **home.html** : The HTML template for the home page, containing the input form and displaying the prediction result.

## **3. Model (flight_rf.pkl)**

- A pre-trained Random Forest model serialized using pickle.

## **4. Database (database.py)**

### **Functions** :
- **create_connection()** : Establishes a connection to the database.
- **create_table()** : Creates tables in the database using schema.sql.
- **insert_data()** : Inserts user inputs and prediction result into the database.

## **5. Schema (schema.sql)**

- SQL script to create necessary tables for storing user inputs and prediction results.

# **Detailed Data Flow**
## 1. **User Input**

- **Form Fields** : Dep_Time, Arrival_Time, stops, airline, Source, Destination
- User submits the form.

## **2. Request Handling (predict() function)**

- Extracts form data using request.form.
- Processes date and time fields using pd.to_datetime.
- Encodes categorical variables (airline, source, destination).

## **3. Data Processing (within predict() function)**

- Extracts day, month, hour, minute from date and time fields.
- Encodes categorical features into binary format.
- Calculates flight duration in hours and minutes.

## **4. Prediction (make_prediction() function)**

- Passes processed data to the Random Forest model.
- Receives the predicted fare.

## **5. Database Interaction (store_data() function)**

- Stores the user inputs and prediction result in the database.

## **6. Response**

- Renders home.html with the prediction result.

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

- The dataset used for training the model was obtained from 

    [Kaggle](https://www.kaggle.com/datasets/nikhilmittal/flight-fare-prediction-mh).

- Inspiration for the project from various online tutorials and courses.

## **Screenshots**

- Here is a screenshot of the application:

1. [Application Screenshot](https://drive.google.com/file/d/1fhoBl2it7Udt7o7YcgjLO5Akiar1_0i7/view?usp=sharing)
2. [Application Screenshot](https://drive.google.com/file/d/1D5Z87WS_rlTD9RitH3HhnZtQ_YBZeLJk/view?usp=sharing)

## **Video Demo**

- Watch a demo of the application in action:

[![Watch the video](https://data.textstudio.com/output/sample/animated/1/3/0/5/demonstration-3-15031.gif)](https://drive.google.com/file/d/1AKgPkT8s3Mrb75x8QQN7mFf3t8_-G9ln/view?usp=sharing)

## **Deployment**

- This project is deployed on Render.com. You can access the live model through the following link:

    [Live Model](https://flight-fare-model.onrender.com)

## **High-Level Architecture Diagram**

```mermaid
graph LR
   A[User Interface] <---> B[Flask Backend] <---> C[Prediction Model]
   
   B --> D[Data Processing]
   B --> E[User Input]
   C --> F[Database]
   ```

## **Low-Level Architecture Diagram**

```mermaid
graph TD
    A[home.html] --> B[Flask Application]
    B --> C[Data Processing]
    C --> D[Database]

    B --> E[Prediction Model]
    E --> F[flight_rf.pkl]

    B -.->|Routes:| G
    G[Routes:
        - home()
        - predict()]
    C -.->|Processes:| H
    H[Data Processing:
        - Input Parsing
        - Feature Encoding]
    D -.->|Database Files:| I
    I[Database:
        - database.py
        - schema.sql]

    E -.->|Model Details:| J
    J[Prediction Model:
        - Random Forest Model
        - Serialized with pickle]