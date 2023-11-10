# Snatch Budget App

  **Snatch Solutions** proudly presents the _Snatch Budgeting App__ for all your budgeting needs. _Snatch Budget_ features a simple, easy to use GUI meant to make budgeting a fluid practice, especially on the go. _Snatch Budget_ breaks down expense periods into paychecks, so each set of expenses can always be filed in a structured budget. _Snatch Budget_ promises ease of use for the populus to help everyone organize finances in a quick and simple manner.

  _Snatch Budget_ will feature an authenticated login/logout system, where each user is able to create their own budget, enter in corresponding expenses, and see the budget update instantly. These feautures will be held within a secure database, promising data privacy for all users.

  To use _Snatch Budget_, a user will first enter in a paycheck. Paychecks are always associated with budgets in this system. The corresponding budget will be tied to a date, and will feature various categories that the paycheck can be split into (mirroring the envelope system). Once a paycheck is made, users can register expenses to the paycheck budget on the go. Each paycheck/budget will feature a breakdown of the expenses made. Future work could include data analysis of spending habits, pay amounts, and more.

![image](https://github.com/Chaser2143/SnatchSolutions/assets/105551586/b6839700-19ad-416f-8e39-82f9c85086cc)

### Key features
- Https Login Page
- Dynamically Loaded Budgets from DB
- Ability to create a new budget and load it with data
- Ability to easily add an expense from the budgets page for _on the go__ expenses
- Budget amounts load from expenses, so each budget is always up to date

### Technologies

I am going to use the required technologies in the following ways.

- **HTML** - Structure for each page of the web app (login, budget overview, budget, quick expense)
- **CSS** - Styling for each page of the web app ^
- **JavaScript** - Communicates with the DB to log users in, fetch corresponding budget data, create budgets and edit them on the go
- **Service** - Backend service endpoints for
- Login Page
- Loading all budgets chronilogically
- Registering a new budget
- Editing an existing budget (on the go expense)
- **DB** - Holds all the budget and expense data under each individual user
- **Login** - Users will be registered if they don't have an account. If they do, associated data will be loaded
- **WebSocket** - Methods for posting and requesting to and from budgets
- **React** - Dynamically loads budgets, serves for the template page for budgets and expenses

## HTML deliverable

For this deliverable I built out the structure of my application using HTML.

- **HTML pages** - 5 Different Pages; Index(About), Login, Console, Quick Expense, and Budget Template
- **Links** - Within each page linking to the other html pages as necessary
- **Text** - Within each page, but most especially within the about page
- **Images** - Within mostly each page, but mostly the about page
- The landing page also holds a picture of a dog which is my placeholder for a 3rd party service, which provides a random picture of a dog everytime its called.
- **Login** - Within the login page
- **Database** - Will be accessed via console.html and budget template (Placeholder marked on console page)
- **WebSocket** - Will be accessed within Quick Expense (Placeholder marked on quickExpense page)

![image](https://github.com/Chaser2143/SnatchSolutions/assets/105551586/d409512d-5e20-4a57-923e-a88f9f6cd3d5)

## CSS Deliverable

For this deliverable, I styled the CSS of my startup, mostly using bootstrap.

- **Header, footer, and main content body**
- **Navigation elements** - I added a really nice drop down and styled all my buttons
- **Responsive to window resizing** - My app looks great on all window sizes (works great on phones)
- **Application elements** - UI is clear and simple
- **Application text content** - Properly styled to my liking
- **Application images** - Images have been added; Moving from my old dog pic api to a greetings API

## JavaScript Deliverable

For this deliverable, I added the JS foundations for the future implementations on the site.

- **Login Support** - I saved the username and password from the login page into the user's local storage as a user object, and moved them on to the budget console page. In the future, I can change these to be verified in the DB before moving them onward.
- **Interaction Logic Support** - Expense objects are created and loaded into local storage from the quick expense page. Budget objects are nade when you create a budget (Place holder still present on console.html). Login page also calls a web service which greets the user in a new language.
- **Websocket Support** - Implemented proper class structure to facilitate updating in realtime. I also made the budget views editable with a double click, so in the future this can update the objects in real time.
- Because of the design of users, budgets, and expenses dynamically loading, every change will automatically be reflected when the user loads the page. So if multiple people (a couple) share an account, they will both always see updated information in realtime.
- **Future Database Support** - Every place where I put something into local storage will eventually go into a database (User Info, Expenses, and Budgets/Categories in the future). Everything I put into local storage is organized into a class of some kind, which will interact well and keep everything organized as it needs to be.

## Services Deliverable
- (Required) Simon Service deployed to your production environment (simon.snatchsolutions.click)
- (Required) A link to your GitHub startup repository prominently displayed on your application's home page (Linked via the icon in the bottom right corner)

**Create an HTTP service using Node.js and Express** 
- My server file is index.js
**Frontend served up using express static middleware**
- Done using the public folder, specifically with a default call to index.html when someone searches the domain
**Your frontend calls third party service endpoints**
- The Welcome Screen on Login calls and endpoint to get a greeting in a different langauge
**Backend Service Endpoints**
- Accessible through '/api/'
  -'/budgets/' lists all budgets (also shown in local storage)
  -'/budget/' adds a budget to all budgets (easiest through the create a budget button on the console)
  -'/expense/' adds an expense to the budget with the matching budget number (easiest through the add Expense button, make sure to add to the right number)

**Frontend Calls to my Service Endpoints**
-The console "create a budget" button takes the user to a form to make a budget. The budget is submitted to my '/api/budget/' endpoint to add it to all of my budgets.
-The console "add expense" buttons takes the user to a form to make an expense. **Make sure to get the budget number right.** The expense is submitted to my '/api/expense' endpoint to add it to the corresponding budget. 

