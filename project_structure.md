## The Goal

## Microservices

### Users

This microservice mainly handles user authentication and keeps track of users' permissions.

Users with `user-edit` permission can create new users and managing user's permissions.

**UI Pages:**
- Login Page
- List of all users on platform
- New user creation
- User management (page for managing individual user's personal info and permissions and potentially user deletion)

### Projects

Developing new features on a certain project while maintaining several other projects requires great organization. The aim of this module is to have an overview of all active projects, keeping all deadlines under control. 

Users with `project-edit` permission can create new new projects and assign other users to projects. Users assigned to specific project can see all relevant info for project they are working on.

Each project can have several stages, where every stage has its own specification (which features should be delivered), deadlines and payment information.

**UI Pages:**
- List of active projects
- List of archived projects (already completed projects)
- New project creation
- Add new stage to existing project
- Project details (page where one can see all of project stages, past, present and upcoming)
- Edit project stage details

### Payouts

Developers are not free and organising how much money the company needs to be payed and how much should go to the developers requires some sort of organizaiton. This module keeps track of all the payouts.

Every stage of the project has its own list of payouts. Each payout has date by which is due, amount each developer is payed and amount that is left in the company.

This module also keeps track of the money in the company and the amount that has been spent for various items in the inventory.

**UI Pages:**
- Monthly view of the payouts and expenses (buying items in inventory)
- List of payouts that are overdue
- Adding a payout
- Editing a payout

### Inventory

While working on multiple projects, one might have to buy some hardware, software licenses or food. This module keeps track of all items owned by the company.

Users with `inventory-edit` permission can create edit items in the inventory.

**UI Pages:**
- List of items in inventory
- Page for adding an item to the inventory
- Item edit page


### Per-Project Password Manager

Each project requires a lot of different accounts for various different products, i.e. cloud provider accout, DNS provider, accounts for differnent 3rd party APIs, Error logging services, etc.

This microservice will allow storing passwords for all those accounts while keeping them secure. Each project will have a separate encrypted password storage, which can be accessed only by users working on that project.



## Technologies