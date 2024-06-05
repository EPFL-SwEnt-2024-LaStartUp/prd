# Non-Functional Requirements

## Security, privacy, and data retention policies

*Which are the applicable laws and regulations?*

In Switzerland, the data are protected by the new Law on Data Protection (LPD) which is in line with 
the General Data Protection Regulation (GDPR) of the European Union. The GDPR is a regulation on 
data protection and privacy in the European Union (EU) and the European Economic Area (EEA). It also 
addresses the transfer of personal data outside the EU and EEA areas. 

*What are your internal policies?*

Our internal policies are the following:

- Data collection: we **do not collect** personal data unless explicit consent is given by the user.
Moreover, according to the LPD, the collected data are limited to only the ones necessary for the
purpose of the application.
- Data storage: personal data is stored using very secure encryption algorithms and access control
measures.
- Data retention: personal data is retained only as long as necessary for the purposes for which it 
was collected, in compliance with legal obligations.
- Data access: access to personal data is restricted to minimum authorized personnel only.
- Data sharing: personal data is not shared with third parties without the user's explicit consent.
In case of subcontracting only necessary data is shared and the subcontractor is bound by the same
data protection obligations, according to the LPD and GDPR.
- Data deletion: users have the right to request deletion of their personal data. Data will be 
deleted within 14 days of the request.
- Incident response: in case of a data breach, affected users will be notified within 48 hours, and 
appropriate measures will be taken to mitigate the breach.
- Compliance: regular audits will be conducted to ensure compliance with the LPD and GDPR. The 
TripTracker organization will appoint a Data Protection Officer (DPO) to oversee data protection
efforts.


*Which privacy features do you need from the phone?*

There are several privacy features needed from the phone in order to have the best user experience:

- **Location services** are needed to record a new path. However, without enabling the location 
services, the user can still access the map and see the paths created by others, but they won't be
able to record their own path.
- **Camera** access is needed to take pictures and add them to a spot of interest along the path.
The user can also upload pictures from the gallery so he is still able to add pictures to the path
without enabling the camera access.
- **Photo storage** is needed to upload pictures from the gallery to an interest point and to change
the profile picture. The user can still use the app without enabling the photo storage access but
won't be able to upload pictures to the app. 
- **Phone storage** is needed to download the paths to make them available offline. The user can 
still use the app without enabling the phone storage access but won't be able to download the paths 
to make them available offline.


## Adoptions, Scalability and Availability

*What kind of traffic patterns do you expect to see?*

We expect traffic patterns to vary based on the time of year, with notable peaks during certain 
periods. However, we can also define general usage patterns such as:

- Daily active users: we expect consistent daily activity from users who use the app for their 
regular travels and exploration.
- Weekly active users: peaks in activity during weekends when users are more likely to explore new 
places or plan short trips.
- Monthly active users: steady growth with peaks around monthly special events, local festivals, and 
holidays.

*Are there known periods of bursty traffic that the MVP must be designed to support?*

The MVP must be designed to support bursty traffic during:

- Summer months, as it is the time of the year when most people go on vacation and travel.
- Holidays, such as Christmas, New Year, October vacation, and other public holidays, as there 
would be higher usage of the app and the application must be able to handle this.
- Special events: There are also some period of heavy traffic that can occur outside of holidays due 
to specific events in a given city, such as festivals, concerts, or sporting events.

To accommodate these patterns, our system should be designed with:

1. A scalable infrastructure: utilizing cloud services that can scale dynamically based on traffic.
2. Some load balancing: ensuring good and even distribution of traffic across servers to prevent 
overload.
3. Caching mechanisms: implementing caching to reduce the load on databases and improve response 
times (the load on the database was already observed in our app if we were too many to use it at the 
same time, on the free firestore plan).
4. Redundancy and failover mechanisms: ensuring high availability through redundant systems and 
automatic failover mechanisms.
5. Monitoring and alerts: continuous monitoring of system performance and automated alerts for 
unusual traffic spikes or potential issues

