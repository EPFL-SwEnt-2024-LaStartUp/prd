# Non-Functional Requirements

## Security, privacy, and data retention policies

*Which are the applicable laws and regulations?*

In Switzerland, the data are protected by the new Law on Data Protection (LPD) which is in line with the General Data Protection Regulation (GDPR) of the European Union.
The (GDPR) is a regulation on data protection and privacy in the European Union (EU) and the European Economic Area (EEA). 
It also addresses the transfer of personal data outside the EU and EEA areas. 

*What are your internal policies?*

Our internal policies are the following:

- Data collection: we **do not collect** personal data unless explicit consent is given by the user.
- Data storage: personal data is stored using very secure encryption algorithms and access control measures.
- Data retention: personal data is retained only as long as necessary for the purposes for which it was collected, in compliance with legal obligations.
- Data access: access to personal data is restricted to authorized personnel only.
- Data sharing: personal data is not shared with third parties without the user's explicit consent.
- Data deletion: users have the right to request deletion of their personal data. Data will be deleted within 14 days of the request.
- Incident response: in case of a data breach, affected users will be notified within 48 hours, and appropriate measures will be taken to mitigate the breach.
- Compliance: regular audits will be conducted to ensure compliance with the LPD and GDPR.


*Which privacy features do you need from the phone?*

The privacy features needed from the phone are:

- Location services: to record and suggest walking paths
- Camera: to take pictures of the spots of interest
- Storage: to download the saved paths to make them available offline and to access the gallery to select pictures to add to the path

## Adoptions, Scalability and Availability

*What kind of traffic patterns do you expect to see?*

We expect traffic patterns to vary based on the time of year, with notable peaks during certain periods. However, we can also define general usage patterns such as:

- Daily active users: we expect consistent daily activity from users who use the app for their regular travels and exploration.
- Weekly active users: peaks in activity during weekends when users are more likely to explore new places or plan short trips.
- Monthly active users: steady growth with peaks around monthly special events, local festivals, and holidays.

*Are there known periods of bursty traffic that the MVP must be designed to support?*

The MVP must be designed to support bursty traffic during:

- The summer months, due to higher tourism activity.
- The holidays, such as Christmas, New Year, October vacation, and other public holidays, as there would be higher usage of the app and the application must be able to handle this.
- Special events: There are also some period of heavy traffic that can occur outside of holidays due to specific events in a given city, such as festivals, concerts, or sporting events.

To accommodate these patterns, our system should be designed with:

1. A scalable infrastructure: utilizing cloud services that can scale dynamically based on traffic.
2. Some load balancing: ensuring good and even distribution of traffic across servers to prevent overload.
3. Caching mechanisms: implementing caching to reduce the load on databases and improve response times (the load on the database was already observed in our app if we were too many to use it at the same time, on the free firestore plan).
4. Redundancy and failover mechanisms: ensuring high availability through redundant systems and automatic failover mechanisms.
5. Monitoring and alerts: continuous monitoring of system performance and automated alerts for unusual traffic spikes or potential issues

