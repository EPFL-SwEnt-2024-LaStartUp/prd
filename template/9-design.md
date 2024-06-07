# Design and Implementation

## Frontend

**Implementation Framework** 
The application is developed in Kotlin and utilizes Jetpack Compose, a modern UI toolkit by Google
designed for building native Android UIs. This framework integrates seamlessly with the existing 
Android ecosystem, offering powerful features. Jetpack Compose's seamless integration with Kotlin 
results in a more readable, and maintainable codebase, guaranteeing a faster development and easier
maintenance of Android applications.

**Authentication**
For authentication, we use Firebase Authentication, a powerful and easy-to-use tool for implementing 
user authentication. It supports various authentication methods including email and password, phone 
authentication, and other identity providers like Google, Facebook, and Twitter, offering 
flexibility for different user preferences. It also handles the security aspects of authentication,
ensuring that the user credentials are safely stored and managed. 

**Geocoding** 
In TripTracker we use Nominatim that is a powerful and efficient geocoding engine provided by 
OpenStreetMap (OSM). It converts addresses into geographic coordinates. Nominatim provides us with 
accurate geocoding results and uses detailed data from OpenStreetMap. It covers a wide range of 
locations globally, including less-populated or remote areas, ensuring global service availability.

**Login Screen**
This is the screen that appears when you first start the app. On this screen, you can login using 
the different login methods supported by the app. After having successfully logged in, you will be 
redirected to the Home Screen. This screen will not appear again while you are still logged in.

**Home Screen**
This screen is the main screen of TripTracker. On this screen you can see every other trip that 
other people have created. A list of the itineraries appear, with information about the trip such as 
its name, number of flames and the user who created it. There is a button to add a trip to your 
favorites, allowing the user to save it and view it in offline mode. You can show trips from 
everyone or only from the users you follow. There is also a search bar that supports different 
search criteria to help you find the Trip that suits you best. You can also start an itinerary, 
which will move you to the Map Screen and guide you to follow the itinerary.

**Maps Screen**
On this screen, a map starts at your position. You can see the itineraries of other users. Clicking 
on an itinerary will show more detailed information about the trip. And you can decide to follow the 
trip. 

**Record Screen**
This screen is a map on which you cannot see the itineraries of other users. You can start recording 
your trip from this screen using the record button. You can add points of interests along your 
recorded trips, give descriptions to these points of interest and add pictures. These points of 
interests will show up in the itinerary preview and details.

**Profile Screen**
The profile screen is where you can find all the informations about yourself and others. In this 
screen, you can edit your profile, modify your username and update your profile picture. You can 
also edit your privacy settings to manage who is allowed to see your trips and your profile. 
Additionally, you can find your saved trips, the trips you created, your followers and the persons 
you are following. You can also access the friend finder that will allow you to find your friend's 
profile and start following them !


## Backend

*Decompose the MVP into functional blocks.*
**Framework**
The backend of TripTracker will be implemented thanks to the Firebase suite. The database will use 
Firestore, and the medias (profile pictures and photos of points of interests) will be stored on the 
Firebase Cloud Storage. This implementation ensures efficiency and scalability while being reliable 
and intuitive. 

**Application Logic** 
The backend of the application will manage the majority of the application logic, acting as the 
central hub for processing and decision-making. By ensuring the reliability of the core 
functionalities on the backend, we establish a solid base that enhances security, maintainability, 
and scalability over the long term. This centralized approach simplifies updates and maintenance, 
ensuring that the application can easily be modified to match future enhancements requirements.

**Interaction with Frontend**
The backend will be responsible for ensuring a responsive UI. It will dynamically update UI 
components based on the latest data, ensuring that the informations displayed to the user are 
up-to-date and accurate. The backend will be monitoring the state of the data and will notify the 
frontend about the validity and freshness of the information, guaranteeing seamless and reliable 
user experience. The goal is to achieve a state where all the pieces of information showed to the 
user are up-to-date and reliable. 

## Data Model

With the TripTracker application, we collect and manage various types of data to provide users with
a seamless and personalized experience. The data collected and managed by the application includes:

- **User Data:** This includes personal data such as the name, surname, email, profile picture and
date of birth of the user. It also includes the list of followers and following, the profile privacy
settings as well as the list of interests, languages and travel styles. Finally, the the list of 
itineraries created and list of favorite paths are also stored.
- **Itineraries Data:** This encompasses the main information about a path, as the name, description, 
author and date of creation. It also includes the list of spots of interest with their photos, the
trending score, as well as the latitude and longitude points representing the path on the map.
- **List of Spots of Interest (or Pins):** This includes the name of the point of interest, its
description, and precise latitude and longitude coordinates.
- **Location Data:** Real-time location coordinates are collected and stored while recording a trip.
These coordinates are linked to a Google Maps API key, and the points of interest information is
connected to the Nominatim API.
- **Google Authentication Data:** Account data for Google authentication is implicitly stored on 
Firebase when a user is logged in.

All those data are integral to the application and must be securely handled to prevent any 
information leaks or hacks.


Currently the data is stored on Firestore. There are two collections for the textual fields : 

- The user data are organised in a user collection 
- The itineraries data are organised in an itinerary collection

The pictures and videos are stored in the Firestore storage : 

- The profile pictures are stored in a specific pin collection
- The pin pictures are stored in a specific pictures collection


The data collected by TripTracker are stored in the following locations:

- **User Data:** Stored securely in a Firestore database within a dedicated user collection. This 
ensures real-time synchronization and robust data security.
- **Itineraries Data:** Managed within Firestore, specifically in the itinerary collection. This 
allows for structured data storage and real-time updates.
- **List of Spots of Interest (or Pins):** Stored in Firestore within the itineraries collection, 
facilitating efficient retrieval and updates.
- **Location Data:** Collected in real-time and stored in Firestore. These location coordinates are
linked with a Google Maps API key for accurate mapping and enriched with Nominatim API for detailed
points of interest information.
- **Google Authentication Data:** Handled implicitly by Firebase Authentication, which securely 
manages authentication tokens and user session data.
- **Profile Pictures:** Stored in Firebase Storage within a designated collection for profile 
pictures, ensuring easy access and management.
- **Pin Pictures:** Also stored in Firebase Storage, within a specific pictures collection for 
seamless retrieval and display.

All stored data is protected by stringent security measures, including encryption in transit and at
rest with the help of the Firebase functionalities.


Currently, the data is stored on Firestore and retrieved in real-time by all running instances of 
the TripTracker app. This ensures that users always have the most up-to-date information. However, 
the background processes of the app handle more data than what is immediately visible to the user. 
This involves several mechanisms:

- **Real-Time Synchronization:** Firestore enables real-time data synchronization across all devices. 
Any changes made to the data are instantly reflected across all running instances of the app.
- **Background Data Management:** The app retrieves additional data in the background to support 
features such as recommendations, trending scores, and personalized itineraries. This background 
data is also kept up-to-date through real-time synchronization with Firestore.
- **Caching:** To improve performance and ensure data availability during intermittent connectivity, 
the app caches frequently accessed data locally on the device. This cached data allows for quicker 
load times and a seamless user experience. This is implemented automatically with help of the 
firestore library. 
- **Data Sharing:** User-generated content such as photos and itineraries is shared across the user 
base. This sharing is managed through Firestore, ensuring that all users have access to the latest 
contributions from the community with respect ot the privacy settings that are implemented in the 
settings.
- **Offline mode:** To allows to download some paths in local this implies that even offline 
instances of the app can have access to user based data and these trips can be followed. 

All these processes ensure that the app delivers a smooth and responsive experience while keeping 
the data secure and up-to-date.

## Security Considerations

Currently, TripTracker uses Firestore, a highly secure database service. However, as the app is 
still in the Proof of Concept (PoC) stage, it operates in a relaxed development mode, which is not 
suitable for a production environment. This mode facilitates rapid development but poses significant 
security risks due to less stringent security configurations.

The app stores certain account and user profile information in the background, which is necessary 
for functionality but not immediately visible to users. This over-privileged data handling increases 
the risk of data leakage or misuse.

Transitioning TripTracker to a production-ready application requires improving security, refining 
data handling, and conducting thorough testing. These steps will ensure the app is secure, reliable, 
and ready for real-world use.


## Infrastructure and Deployment

Our database infrastructure will consist of two Firestore databases. This is needed if we want to 
make changes to the data model or the database itself in future updates. We will require a
development database for conducting tests and modify the data classes. Another database will handle
the normal workflow of the app for users. Modifications to the user database will need to be applied 
during scheduled maintenances periods, during which people will not be able to use the app. 
These maintenances should be scheduled during times of low app usage.

We will use Firebase to deploy our backend and to link it to our application. We will need to ensure 
that our applications is not rate-limited, and Firebase will automatically allocate the appropriate 
amount of resources. 

## Test Plan

In order to ensure that our application meets the highest standards, we will use different methods 
of testing throughout the development of the app :

- **Unit Tests:**  We will first verify the functionality of individual components or units of the 
application. Each component will be tested in isolation to ensure it works as expected.

- **Integration Tests:**  We will ensure that different modules and services of the application work 
together correctly. This includes verifying the integration between the application and Firebase 
services.

- **Performance Testing**  We will assess the responsiveness, stability, scalability, and resource 
usage of the application under different conditions. This includes stress testing the app during
high usage periods, such as specific events or in areas where a large number of trips can be fetched. 
The goal is to keep the fetch latency low and to ensure that we do not generate a large number of 
requests to Firebase in some situations.
