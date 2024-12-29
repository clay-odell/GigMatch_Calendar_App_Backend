**GigMatch Calendar App**  
*A calendar application serves as a collaborative platform where artists and venues can easily create and manage events, ensuring there are no scheduling conflicts. It centralizes calendar events to streamline planning and enhance connectivity between artists and venues. This fosters better coordination, allowing for more efficient event management and maximizing booking opportunities.*

| Instruction | Description | Menu |
| :---- | :---- | :---- |
| **Stack** | Tech stack used for the project | React, Node, Express, JavaScript, HTML, CSS, PostgreSQL, Supabase, Render |
| **Focus** | Is the frontend UI or the backend going to be the focus of the project? Or are you going to make an evenly focused fullstack application | Fullstack application that is primarily focused on backend. Backend will support data management and integration with my own API.Frontend will be focused on creating a user-friendly design, allowing user and administrative accounts to navigate seamlessly.User accounts will be able to sign up, login, and submit event requests to the administrative calendar.Administrator accounts will be able to sign up, login, and approve or deny calendar requests, as well as establish the base-level site calendar. |
| **Type** | Will this be a website? Mobile app? Something else? | Web application |
| **Goal** | What goal will your project be designed to achieve? | To give music venues and artists a way to connect with one another, to share calendar availability, submit event requests, and for administrative users to approve and deny event requests. |
| **Users** | What kind of users will visit the app? | Administrative users will be music venues or entertainment-booking agencies.Non-admin users will be musicians and entertainment acts seeking to connect and book gigs at music venues. |
| **Data** | What data will be used? How will it be collected? | **Data Sources**: My own API and possibly other calendar API resources. **Data to Collect**: Calendar event requests to save and update calendar information, administrator and user information requests to save administrator and user information. **Collection Method**: API requests |

**Outline**:

* **Database Schema**: Tables for \[Admins/venues\], \[Users/artists\], \[Calendar\_Events\], \[event\_requests\], \[confirmed\_requests\], \[denied\_requests\], \[pending\_requests\]  
* **API Issues**: custom error handling.  
* **Sensitive Information**: Securely store user/admin account credentials, and ensure full calendar access (updating and event accepting) are protected by admin privileges. Ensure encryption and safe handling of passwords.  
* **Functionality**:   
  * Events \-\> Users can create event requests following the API. These events are displayed with start time, end time, title, description, compensation and will be in pending status until admin approval. Non-admin users cannot ultimately update the master calendar. \-\> Admin users can create, approve, and deny calendar event requests.  Their handling of events will update the master calendar.   
    * An email/message will be generated and sent to both the Admin and Non-admin users after admin approval or denial of non-admin users’ requests.  
  * **User Flow**:  
    * **Non-admin/Artist User Flow \-** Sign up/share info \-\> Artists after being prompted to fill out basic info like email phone first name and last name their info will be saved in db. After this they will have the option to make calendar event requests to the .This information and associated info will be stored in db for GigMatch use.  
    * **Admin/Venue/Booking Agent Flow** \-Sign up/get verified \-\> Admin users will be prompted to fill out the basic information. Continuing on they will be prompted to make an account with password email etc and first verifying email or sms through a third party service , so they cannot use invalid info. Admins will have full access to all GigMatch info, sending messages to artists , scheduling , approving and denying calendar event requests. They will be able to create, update, and remove the master calendar.  
      * Event Creation: Logged in users can create event requests. Non-admin users will only be able to see their requests, pending, accepted, and denied. Admin users will be able to see all user calendar requests, including all of the various statuses.

