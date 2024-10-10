
<h1>1. Introduction</h1>
1.1 Purpose
The purpose of the "Рослини App" project is to create a mobile application that allows users to register, add their plants with photos, descriptions, and event dates, and monitor plant conditions through ESP32 sensors. The app will display events in a calendar and provide plant care statistics. This SRS covers all major functionalities and subsystems of the application.</br>
</br>
1.2 Intended Audience and Reading Suggestions
This document is intended for developers, project managers, testers, and end-users. It is organized to start with an overview of the product and move into specific functional and non-functional requirements. Developers should focus on sections 2 and 3, while users can refer to section 3 for a description of key features.</br></br>
1.3 Product Scope
"Рослини App" aims to provide an all-in-one tool for plant enthusiasts to monitor and care for their plants. Users can add plants with recurring or one-time events, view them in a calendar, track plant care statistics, and monitor soil moisture using ESP32 sensors. This product will assist users in maintaining healthy plants through timely care reminders and sensor data integration.</br>
</br>
1.4 References
Any references to external documents or resources, such as user manuals or external API documentation, will be provided here once they are finalized.</br>
</br>
<h1>2. Overall Description</h1>
2.1 Product Perspective
"Рослини App" is a standalone mobile application designed to integrate with ESP32 sensors for monitoring plant moisture levels. The application is new, self-contained, and designed to operate on both Android and iOS platforms. A diagram of the system architecture will be included in later versions of this document.</br>
</br>
2.2 Product Functions
User Registration and Login: Users can register and log in via email.
Add/Edit Plants: Users can add plants with names, descriptions, photos, and set events (watering, fertilizing).
Calendar View: Display plant care events on a calendar with the ability to click on an event to see plant details.
Plant Care Statistics: Track statistics for individual plants and display them to the user.
ESP32 Sensor Monitoring: Integrate with ESP32 sensors to monitor soil moisture levels and display the data in the app.</br>
</br>
2.3 User Classes and Characteristics
Plant Enthusiasts: Casual users who wish to track their plant care.
Gardeners/Greenhouse Owners: More advanced users with a larger number of plants and more frequent care activities.
Sensor Users: Users with ESP32 sensors connected to their plants for automated monitoring.</br>
</br>
2.4 Operating Environment
The application will operate on Android and iOS platforms. It will require internet access to sync data with cloud storage and pull data from ESP32 sensors. It will also communicate with Firebase for backend operations and Firestore as a database.</br>
</br>
2.5 Design and Implementation Constraints
The system must support real-time synchronization with ESP32 sensors.
The application must comply with Android and iOS design guidelines.
Firebase and Firestore will be used for user data management and storage.</br>
</br>
2.6 User Documentation
Online help, video tutorials, and a user guide will be provided to assist users with app features and configuration of ESP32 sensors.</br>
</br>
2.7 Assumptions and Dependencies
The user will have a stable internet connection for syncing data.
ESP32 sensors need to be correctly set up and integrated for real-time monitoring.</br>
</br>
<h1>3. External Interface Requirements</h1>
3.1 User Interfaces
The app will feature a simple, user-friendly UI with the ability to add/edit plants, view the calendar, and monitor statistics. Sample screens will be included in the final design document.
</br>
</br>
3.2 Hardware Interfaces
The app will connect to ESP32 sensors for monitoring soil moisture. It will support communication over Wi-Fi for sensor data retrieval.</br>
</br>
3.3 Software Interfaces
The application will integrate with Firebase for user authentication and Firestore for plant data storage.
API integration with ESP32 sensors to receive real-time moisture data.</br>
</br>
3.4 Communications Interfaces
Data synchronization between the app and Firebase will occur over HTTPS.
Real-time sensor data will be retrieved via the Wi-Fi module of the ESP32.</br>
</br>
<h1>4. System Features</h1>
4.1 User Registration and Login
4.1.1 Description and Priority
Users must be able to register and log into the app using their email addresses. This is a high-priority feature to ensure that data is saved securely for each user.</br>
</br>
4.1.2 Stimulus/Response Sequences
User Action: The user enters their email and password to register.
System Response: The app checks if the email is already registered and, if not, creates a new account.</br></br>
4.1.3 Functional Requirements
The app must validate email formats.
Passwords must meet security criteria (e.g., minimum 8 characters, including letters and numbers).</br></br>
4.2 Add/Edit Plants</br></br>
4.2.1 Description and Priority
Users must be able to add, edit, and delete plants with associated events. This feature is essential for the core functionality of the app.</br></br>
4.2.2 Stimulus/Response Sequences
User Action: The user adds a new plant, uploading a photo and setting event dates.
System Response: The app stores the plant data in Firestore and updates the calendar.</br></br>
4.2.3 Functional Requirements
Users can upload images up to 5MB.
Users can set one-time or recurring events for each plant.</br></br>
4.3 ESP32 Sensor Integration</br></br>
4.3.1 Description and Priority
ESP32 sensors will monitor soil moisture levels and send data to the app for display. This feature is of medium priority but is key for users with sensors.</br></br>
4.3.2 Stimulus/Response Sequences
User Action: The sensor records soil moisture levels.
System Response: The app receives and displays the sensor data in real time.</br></br>
4.3.3 Functional Requirements
The app must display moisture data in a graph or numerical format.
The app should alert users if moisture levels fall below a certain threshold.</br></br>
<h1>5. Nonfunctional Requirements</h1>
5.1 Performance Requirements
The app must load plant data within 2 seconds.
Sensor data must be updated in real time with a delay of no more than 5 seconds.</br></br>
5.2 Security Requirements
All user data must be encrypted in transit and at rest.
User authentication must be secured via Firebase Authentication.</br></br>
5.3 Software Quality Attributes
The app must be highly reliable, with 99% uptime for core features.
Usability should be intuitive, with most users able to add plants without external help.</br></br>
5.4 Business Rules
Users can only delete plants that they have added.
The app will notify users of upcoming plant care events via push notifications.
This SRS will be updated regularly as the project progresses.
