# System-Design-Enhancement-Week
## Streaming Service for Videos.
1.	Auth Service: Responsible for Authenticating the user, Single entry point. Return if the user is invalid.
2.	Subscription Service: Responsible for checking the user’s subscription, can be ENUM of subscription. E.g.: HD Plan, Standard, Mobile.
3.	Location Service: Used for mapping the video catalogue to the user’s location. Can be determined using the user’s IP for now. 
4.	Video Transcoding Service: Used for transcoding video into different format, User can have issues with bandwidth and to make sure the video keeps playing we need to degrade the video quality this can be done by checking the stream bandwidth and then sending back the video of appropriate size for auto or force the video in particular format if user selects it.
5.	Notification Service: This service is broadcast service; this can be combined with upload service. When a video is uploaded to the server then a push can be done to the queue for notification. We are focusing on async communication as this service is not that time sensitive.
6.	Payment Service: This can be third party service like stripe which gives us successful response once the payment is authorized.
7.	User Profile Service: Can be used to get the user details, Like the profile of the user who relates to the login ID can be also checked up with the auth service and combined for a short traffic application.
8.	Video Upload Service: This service can be used by the internal teams for uploading the video and then that video is transcribed and made available to the people in authorized regions.


