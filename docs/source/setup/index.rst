#######
Setup
#######

This is the guide to getting your Department configured in the resgrid system. This setup guide is a high level overview of the settings to get your department up and running with Resgrid both the OnPrem and Hosted versions of the system. 

.. note:: Only one person in your department or organization needs to sign up for a new Resgrid department, when you create an account from the Resgrid homepage this happens automatically. If this is an on-premises installation, use the default department information to log in.

Getting Started
**************

Once you have your first user registered with Resgrid (or using the default OnPrem department) you can log into the system. The first page you will land on will be the dashboard page or home page. Here is a list of your personnel, groups and their statuses. You can also set your status and staffing level on the widgets on the right hand side. In the top of the screen you can click your name in the left hand side to view or update your profile. The 2 icons in the middle are your active calls and your inbox messages. The menus on the right are your Department Menu (it's the name of your department) and is the primary location to configure your department, a help menu and a logout button.


.. list-table:: Department Menu Items
   :header-rows: 1

   * - Item
     - Visibility
     - Description
   * - Department Settings
     - Admins Only
     - General Department settings like name, main address, time zone and resets.
   * - Stations & Groups
     - Admins Only
     - Create and Manage Groups and Membership in those Groups
   * - Call Import Settings
     - Admins Only
     - Call Email Import Settings and Call Auto Close (Prune) Settings
   * - Custom Statuses
     - Admins Only
     - Create Department Specific Personnel and Unit Statuses and Staffing Levels
   * - Text Messaging
     - Admins Only
     - Type of Inbound Text Messages allowed (Call or Command)
   * - Api Settings
     - Admins Only
     - Allocate a System level API Key and Key for Active Calls RSS Feed
   * - Types
     - Admins Only
     - Manage Department Wide Types (Call Types, Call Priorities, Unit Types, Certifications)
   * - Distribution Lists
     - Admins Only
     - Create and Manage Membership is custom defined email distribution lists
   * - Security & Permissions
     - Admins Only
     - Configure Permissions (i.e. who can create calls) for the department and view Audit Logs
   * - Subscription & Billing
     - Admins Only
     - Manage your departments subscription and billing information. (Hosted Version only)
   * - Orders
     - Everyone
     - Your Resource Order Requests and those from other departments (i.e. Mutual Aid)
   * - Links
     - Everyone
     - Links with other Departments in Resgrid (i.e. sister stations)
   * - Notifications
     - Everyone
     - Create and Manage your custom notifications (i.e. be notified if a unit goes out of service)
   * - Commands
     - Everyone
     - Create and manage Command definitions for call types (for the Commander app)
   * - BigBoard
     - Everyone
     - A configurable dashboard where you can see your departments info at a glace on a TV\Monitor

.. note:: Main administrative operations (both department and group) are only available to be performed via the website. The Mobile application (like Resgrid Responder) are intended for personnel specific functions, like setting ones own status or staffing level, or viewing call information.

Department Settings
**************

After you log into the website, click your department menu, it's the name of your Department in the upper right hand corner of the web application next to the Help menu. The menu will drop down and expose a list (detailed above), click on Department Settings.

.. list-table:: Department Settings Options
   :header-rows: 1

   * - Setting
     - Description
   * - Department Name
     - The name of your department or how you want it displayed in Resgrid
   * - Time Zone
     - The primary time zone your department is in. If your department is in multiple time zones, this should be the time zone of your headquarters or main office.
   * - Use 24-Hour Time
     - Do you want time displayed in 24 hour format for your department? For example 8:00PM is 2000 in 24 hour format.
   * - Managing User
     - This is the 'master' admin for the Department and that user cannot be removed from the system. 
   * - Disable Auto-Available
     - By default the Resgrid system will ignore personnel statuses (instead just showing "Standing By") submitted after an hour when displaying their current status in a list. Checking this box will disable that feature. 

The Address section should be your home office, headquarters or main location. This will be used as the default center for most of the maps. Centers can also be adjusted in each map as well.

Personnel Staffing Reset will add a Staffing level (selected in 'Reset Staffing Level To') for every user in the Department at the specified time. For example if you want to ensure all personnel staffings are up to date every day at 0800, you can have the system set a default staffing, like Unavailable, at 0200 so you know if there is a different staffing it's accurate as of that morning.

Personnel Status Reset will add a Status (selected in 'Reset Status To') for every user in the Department at the specified time. For example if you want to ensure all personnel statuses are up to date every day at 0800, you can have the system set a default status, like Standing By, at 0200 so you know if there is a different status it's accurate as of that morning.

Force Department Update will clear out all of the in memory cached information for your department. This is a scheduled job and can take up to 15 minutes to process. Resgrid caches a lot of static data, like groups and group names, personnel names, etc that don't change frequently and store them in memory for fast access. Forcing a Department Update will clear that cache and force it to be pulled from the Database. This will negatively impact your performance until all data is recached.  

.. warning:: Forcing a Department Update to clear the cache should only be used it some data, i.e. a group name or personnel name, is not updated for EVERYONE, not just one computer or phone. That device may have cached the output or call itself. This operation will slow down the system for ALL USERS until the cache is rebuilt.

Creating Groups
**************

After you log into the website, click your department menu, it's the name of your Department in the upper right hand corner of the web application next to the Help menu. The menu will drop down and expose a list (detailed above), click on Stations and Groups.

Resgrid has 2 types of groups Station and Organizational. Station groups require a physical address and are the only group types allow to have Units under them. A Station group is intended to denote a physical location that personnel or units may be responding out of, or responding to (i.e. to pick up some equipment or staff). Organizational groups have no physical location and are intended to allow users to be grouped together. For example you can use Organizational groups like East or West denote which users are in those response areas.

.. note:: Users can only be in 1 group at a time, but a user can be a part of many roles. Ideally you would use Groups to define something static like Stations, Districts, Response Areas, etc and use Personnel Roles to define more dynamic information like if a person is a Paramedic or HAZMAT Technician.

.. _organizational_groups:

Organizational Groups
=======================

Organizational groups are intended to organize groups of users. This group type can only have personnel assigned to it.


.. _station_groups:

Station Groups
=======================

Station groups can have personnel and units assigned to them and must have a physical address. This address could be a building or open staging area. 


.. list-table:: Creating a Group Options
   :header-rows: 1

   * - Setting
     - Description
   * - Group Type
     - The type of group you want to create Organizational or Station
   * - Group Name
     - The name of your group
   * - Parent Group
     - You can have a group under a group, if you want this newly created group to show up underneath another group select the parent group here
   * - Address
     - Optional. If you have selected a Station group you need to supply a physical address for this group. An example would be a Fire Station, Staging Area, Ambulance Bay, etc.  
   * - Group Admins
     - These are the administrators for this group. Group Admins can modify personnel in the group, for example updating their profile
   * - Group Users
     - Personnel that are in the group

.. note:: You do not have to add personnel here, you can leave both Group Admins and Group Users blank and add users to the groups when you add the users or edit their profiles. For very large groups the list of personnel in the group will be too big to maintain here and is best maintained at the personnel profile level.

Personnel Metadata
**************

Adding Personnel
**************

Units Metadata
**************

Adding Units
**************