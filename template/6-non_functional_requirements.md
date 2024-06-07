# Non-Functional Requirements

## Security, privacy, and data retention policies

In Switzerland, data is protected by the new Law on Data Protection (LPD), which align with the 
General Data Protection Regulation (GDPR) of the European Union. The GDPR is a regulation on data 
protection and privacy in the European Union (EU) and the European Economic Area (EEA). It also 
addresses the transfer of personal data outside the EU and EEA areas. 


Our internal policies are the following:

- **Data collection:** We **do not collect** personal data unless explicit consent is given by the 
user. According to the LPD, the collected data is limited to what is necessary for the purpose of 
the application.
- **Data storage:** Personal data is stored using highly secure encryption algorithms and access 
control measures.
- **Data retention:** Personal data is retained only as long as necessary for the purposes for which 
it was collected, in compliance with legal obligations.
- **Data access:** Access to personal data is restricted to minimum of authorized personnel.
- **Data sharing:** Personal data is not shared with third parties without the user's explicit 
consent. In case of subcontracting, only necessary data is shared, and the subcontractor is bound by 
the same data protection obligations according to the LPD and GDPR.
- **Data deletion:** Users have the right to request the deletion of their personal data. Data will 
be deleted within 14 days of the request.
- **Incident response:** In case of a data breach, affected users will be notified within 48 hours, and 
appropriate measures will be taken to mitigate the breach.
- **Compliance:** Regular audits will be conducted to ensure compliance with the LPD and GDPR. The 
TripTracker organization will appoint a Data Protection Officer (DPO) to oversee data protection
efforts.


Several privacy features are needed from the phone to provide the best user experience:

- **Location services** are needed to record a new path. However, without enabling the location 
services, users can still access the map and see the paths created by others, but won't be able to 
record their own path.
- **Camera** access is needed to take pictures and add them to a spot of interest along the path.
Users can also upload pictures from the gallery, allowing them to add pictures to the path without 
enabling the camera access.
- **Photo storage** is needed to upload pictures from the gallery to an interest point and to change
the profile picture. Users can still use the app without enabling the photo storage access but
won't be able to upload pictures to the app. 
- **Phone storage** is needed to download the paths to make them available offline. Users can 
still use the app without enabling the phone storage access but won't be able to download paths for
offline usage.


## Adoptions, Scalability and Availability

We expect traffic patterns to vary based on the time of year, with notable peaks during certain 
periods. However, we can also define general usage patterns such as:

- **Daily active users:** We expect consistent daily activity from users who use the app for their 
regular travels and exploration.
- **Weekly active users:** Peaks in activity during weekends when users are more likely to explore 
new places or plan short trips.
- **Monthly active users:** Steady growth with peaks around monthly special events, local festivals,
and holidays.


The MVP must be designed to support bursty traffic during:

- **Summer months:** This is when most people go on vacation and travel.
- **Holidays:** Such as Christmas, New Year, October vacation, and other public holidays, as there 
would be higher usage of the app.
- **Special events:** Period of heavy traffic that can occur outside of holidays due to specific 
events in a given city, such as festivals, concerts, or sporting events.

To accommodate these patterns, our system should be designed with:

1. **A scalable infrastructure:** Utilizing cloud services that can dynamically scale based on 
traffic.
2. **Load balancing:** Ensuring good and even distribution of traffic across servers to prevent 
overload.
3. **Caching mechanisms:** Implementing caching to reduce the load on databases and improve response 
times (the load on the database was already observed in our app if we were too many to use it at the 
same time, on the free firestore plan).
4. **Redundancy and failover mechanisms:** Ensuring high availability through redundant systems and 
automatic failover mechanisms.
5. **Monitoring and alerts:** continuous monitoring of system performance and automated alerts for 
unusual traffic spikes or potential issues.
