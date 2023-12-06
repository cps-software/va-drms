# va-drms
Reference application to demonstrate a VA Drug Risk Management System (DRMS)

## Overview
The VA DRMS is a simple web application that demonstrates potential VA pharmacovigilance functionality. It uses a modern web-based technology stack and follows software engineering best practices.

The DRMS will operate as if it were running within the VA secure network. In other words, it should include functionality to read a PIV card and interface with the VA IAM service to create sessions. It should also interface with other VA services such as MVI and data access API's.

The initial thinking is to go with Java Spring + JavaScript React + a relational database. It would also be good to explore options related to Microsoft 365 and Azure, such as the Power Platform, Copilot, and hosting options within Azure.

## Code Organization
This application is organized into a frontend component using Javascript and React, and a backend component using Java and Spring. The backend will includes a relational database. Refer to [Frontend Dev Guide](./frontend/docs/frontend-dev-guide.md) and [Backend Dev Guide](./backend/docs/backend-dev-guide.md) for infomration on setting up a local development environment.


## Jobs to be Done
This app will be designed using Jobs Theory, or "Jobs to be Done" (JTBD). My understanding is that this is similar to the Use Case approach, but maybe more from a product manager perspective. It seems like an okay way to capture and organize requirements, specific funcions, and acceptance criteria, which should help with actual development.

### Single Sign-On using Smart Card
VA uses multifactor authentication using a PIV card and PIN to provide Single Sign-on capability. In my opinion, this "convenience" can be more cumbersome than using a separate username and password (and perhaps 2FA via text code). But, that's the way VA (and others) do it, so that's one of the first things to understand and support.  

The steps for this Job are:

1. User opens a browser
2. User navigates to the application URL 
3. The app checks for a valid security token and does not find one
4. The URL is redirected to the SSO service
5. The SSO service walks user through selecting smart card, certificate, and PIN
6. The SSO service validates that the user is legitimate
7. The SSO service provides security token that can be used for the remainder of the session
8. The SSO service redirects user back to the original URL and provides token



