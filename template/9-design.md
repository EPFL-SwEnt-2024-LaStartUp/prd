# Design and Implementation

## Frontend

*List the key libraries, languages, components used by the MVP.*

The key libraries, languages, components used by the MVP are:
- Kotlin

*If applicable, describe essential screens.*

## Backend

*Decompose the MVP into functional blocks.*
**Framework**
The backend of TripTracker will be implemented thanks to the Firebase suite. The database will use Firestore, and the medias (profile pictures and photos of points of interests) will be stored on the Firebase Cloud Storage. This implementation ensures efficiency and scalability while being reliable and intuitive. 

**Application Logic** 
The backend of the application will manage the majority of the application logic, acting as the central hub for processing and decision-making. By ensuring the reliability of the core functionalities on the backend, we establish a solid base that enhances security, maintainability, and scalability over the long term. This centralized approach simplifies updates and maintenance, ensuring that the application can easily be modified to match future enhancements requirements.

**Interaction with Frontend**
The backend will be responsible for ensuring a responsive UI. It will dynamically update UI components based on the latest data, ensuring that the informations displayed to the user are up-to-date and accurate. The backend will be monitoring the state of the data and will notify the frontend about the validity and freshness of the information, guaranteeing  seamless and reliable user experience. The goal is to achieve a state where all the informations showed to the user are up-to-date and reliable. 

## Data Model

*What data are you collecting / managing?*

For this application, we are collecting and managing the following data:

- User Data: This includes name, surname, email, profile picture, date of birth, list of itineraries created, list of followers and following, list of favorite paths, profile privacy settings, interests, languages, and travel styles.
- Itineraries Data: This encompasses the name, description, date, author, list of spots of interest, photos, trending score, and latitude and longitude points representing the path on the map.
- List of Spots of Interest (or Pins): This includes the name of the point of interest, description, and precise latitude and longitude coordinates.
- Google Authentication Data: Account data for Google authentication is implicitly stored on Firebase when a user is logged in.
- Location Data: Real-time location coordinates are collected and stored while recording a trip. These coordinates are linked to a Google Maps API key, and the points of interest information is connected to the Nominatim API.

All this data is integral to the application and must be securely handled to prevent any information leaks or hacks.

*How is it organised?*

Currently the data is stored on Firestore. There are two collections for the textual fields : 
- The user data are organised in a user collection 
- The itineraries data are organised in an itinerary collection

The pictures and videos are stored in the Firestore storage : 
- The profile pictures are stored in a specific pin collection
- The pin pictures are stored in a specific pictures collection


*Where is it stored?*

All those data are stored in a Firestore database.

*How is it shared/copied/cached?*


## Security Considerations
Since the app

## Infrastructure and Deployment

*How is the application developed, tested and deployed?*

*Any special infrastructure requirements.*

## Test Plan

*How is the application developed, tested and deployed?*

*Any special infrastructure requirements.*

In order to make sure that our application meets the highest standars we will use different methods of testing throughout the making of the app :

**Unit Tests**  We will first need to verify the functionality of individual components or units of the application. Each unit is tested in isolation to ensure it works as expected.

**Integration Tests**  We will need to ensure that different modules and services of the application work together correctly. This includes verifying the integration between the application and Firebase services.

**Performance Testing**  We will need to assess the responsiveness, stability, scalability, and resource usage of the application under different conditions. This includes stress testing the app in case of high usage at the occasion of specific events for example or simply when around areas where a lot of trips can be fetched. The goal is to keep the fetch latency low and to make sure that we do not create huge amounts of requests to the firebase in some situations.

