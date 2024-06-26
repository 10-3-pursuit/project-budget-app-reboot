# Full Stack Budgeting App Reboot

<img src="./assets/budget.webp" width="500" height="400">

Budgtr is an application where people can log their financial transactions. Building this application will require you to bring together all you've learned about JavaScript, building websites, React, servers and RESTful routes.

## Project setup

**You _SHOULD NOT_ fork and clone this repository.**

Instead, create a parent folder called `Budget-App` to house the frontend and backen repos.

1. `Fork` the [Project Budgeting App Frontend](https://github.com/10-3-pursuit/project-budgeting-app-frontend).
1. `Clone` the forked repository into your `Budget-App` parent folder.
1. `Fork` the [Express Server Starter](https://github.com/10-3-pursuit/express-server-starter)
1. `Clone` the forked repository into your `Budget-App` parent folder
1. Your backend repository should have a `readme.md` file with setup instructions for your application.
1. Your readme should also include links to your frontend GitHub repository.

### Mastery

This section of the project is designed to measure your increasing skill at writing good code and following best practices.

#### backend feature requirements

To complete the backend application, you will need to build a RESTful server that performs CRUD actions on a single resource.

1. Your server should incorporate one table that includes these field names (schema.sql):

   - item_name - string
   - amount - decimal
   - date - date
   - from - string
   - category - string

1. You should seed your database, `seed.sql` with at least 3 transactions

1. Your server should incorporate at least one resource (Router/Controller) that, includes:

   - `id` - A unique number for each item
   - `item_name`- string - the name of the transaction (ie: income, savings, cat food, etc.)
   - `amount` -number - the amount of the transaction
   - `date`- string - the date should be a simple string. As a bonus activity, use the date object and date input field and format it to be human-readable
   - `from` - string - who this transaction was with (ie. employer, bank, pet store, grocery store, etc)
   - `category` - string - what category does this fall into (income, savings, pets, food, etc)

1. Spec for this resource:

   1. A route exists to create new resources.
   1. A route exists to read all resources.
   1. A route exists to read a single resource.
   1. A route exists to update a single resource.
   1. A route exists to delete a single resource.
   1. An appropriate "Not Found" response is given when a route is requested that does not match the created routes.

1. Add a message for when a resource is not found in a particular route.
1. Validate your form requests to make sure you have the proper information to add to the data (array)
1. Add a response message for when an endpoint does not exist.
1. Add Status Codes to your responses. 200 for success. 400 for not found. 500 for server error.

##### backend Example

|  #  | Action  |        URL        | HTTP Verb |    CRUD    |                  Description                   |
| :-: | :-----: | :---------------: | :-------: | :--------: | :--------------------------------------------: |
|  1  |  Index  |   /transactions   |    GET    |  **R**ead  |   Get a list (or index) of all transactions    |
|  2  |  Show   | /transactions/:id |    GET    |  **R**ead  | Get an individual view (show one transactions) |
|  3  | Create  |   /transactions   |   POST    | **C**reate |           Create a new transactions            |
|  4  | Destroy | /transactions/:id |  DELETE   | **D**elete |             Delete a transactions              |
|  5  | Update  | /transactions/:id |    PUT    | **U**pdate |             Update a transactions              |

> **Note:** All of the above routes should work both with Postman and in your React frontend.

#### Frontend feature requirements

To complete the frontend application, you will need to build a React application, using [Project Budgeting App Frontend](https://github.com/10-3-pursuit/project-budgeting-app-frontend), that allows for CRUD operations to be performed on a single resource. You will also need to display the data thoughtfully and clearly.

Use of `React Router 6.2.1` is optional for this project.

```js
npm i react-router-dom@6.2.1
```

Please be mindful as to how you render and toggle components on the page if you do not use Router. Keep User Experience in mind.

**Spec:**

1. How you name the components is up to you but all component file names should be capitalized and end in `.jsx`.
1. All pages should include the same navigation bar, which includes the name of the application and a button to create a new resource.
1. You should have an Index page that presents all of the resources in your database table.
1. After clicking on a single resource, you should be brought to a Show page which includes more detailed information about the specific resource.
1. When the button in the navigation bar to create a new resource is clicked, you should be brought to a new page that includes a form to create a new resource.
1. Forms should be properly labeled and the `type` of inputs should be properly set. For example, an input that requires a `number` should have type `number`, not `text`.
1. When a new resource form is submitted, the resource should be created in the database and the user should be brought to that new resource's Show page or to the main page where the resource had been added.
1. On the resource's Show page or by the resource, there should be a button to edit the current resource. When clicked, the user is brought to a form page with data already filled in that can be edited.
   **Note:** You may use the same component or two different component for the Create and Edit functionality
1. When an edited resource form is submitted, the resource should be edited in the database and the user should be brought to that new resource's Show page or to the main page where the resource has been added.
1. On the resource's Show page, there should be a button to delete the current show page. If not using router that Delete button should be connected to the resource.
1. Using the resource's data, perform a calculation that can be performed on the frontend application and displayed to the user on the Index page. For example, the bank account total should be visible. In addition to the total, the CSS should change based on the value - use a greenish color if the bank account total is above 100, use a yellowish color if the bank account total is between 0 and 100 and a reddish color if the bank account total is less than 0. You can change the background or text or both.

### Stretch goals

This section of the project measures your ability to go above and beyond in creating your project. To score points in this section, you should incorporate a feature, technology, or skill not explicitly required by the project instructions.

When you submit your pull request, _make sure to include a description of any stretch goals you implemented._ You may choose from the list below or come up with features or tasks that are more relevant to your specific implementation of the project.

- Use the `Pages` and `Components` architecture.
- Use [axios](https://www.npmjs.com/package/axios) instead of `fetch` to make calls to the backend
- Make `categories` a `select` HTML element on the new/edit forms to allow the user to choose from a pull-down menu from the available categories, and allow for the addition of new categories to the options menu.
- Display the bank account total in the nav bar (or similar component that is visible on all views), instead of just on the index page.
- Add helpful errors to users when they try to create or edit items with invalid data
- Use the date object for the date, instead of just a string. Be sure to format it on the frontend to make it human-readable. Try using the `date` input type as well.
- Use a checkbox, separate input or similar strategy to allow the user to select whether the transaction is a deposit or withdrawal. If it is a withdrawal, make sure the value subtracts and deposit values add. By default, your user would have be entering values that are positive or negative.
- Add a library like [chartjs](https://www.chartjs.org) to provide visualizations the budget app.
- Add [React Drag and Drop](https://react-dnd.github.io/react-dnd/about) to move your transactions above and below each other.
- Reuse one of the stretch goals from a previous project.

## Example application

![](./assets/index-page.png)

![](./assets/new-page.png)
