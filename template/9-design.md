# Design and Implementation

## Frontend

*List the key libraries, languages, components used by the MVP.*

The key libraries, languages, components used by the MVP are:
- Kotlin

*If applicable, describe essential screens.*

## Backend

*Decompose the MVP into functional blocks.*

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

