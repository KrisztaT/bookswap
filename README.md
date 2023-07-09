# BookSwap - Share. Swap. Explore.

## R1 - Description of the website

**Purpose:**

BookSwap is an online platform designed to connect book enthusiasts and facilitate the sharing of books within a community of readers. The primary purpose of the platform is to foster a sense of community, encourage book sharing, and provide a convenient way for users to explore and borrow books from fellow readers.

The organisation Konyvek.hu has shown interest in integrating the application into their existing platform. To facilitate this, they have assigned a resource named Jozsef to collaborate on the project. Jozsef's responsibilities include defining the project scope, participating in standup meetings, and conducting user testing.

Please note that the inclusion of Konyvek.hu as part of the context is purely fictional and has been added solely for assessment purposes.

**Functionality/Features:**

In collaboration with Jozsef, we have identified three tiers of functionality based on the applied agile methodology. These tiers define the progressive levels of features of the project. By dividing the these functionalities into tiers, we can prioritise and implement them incrementally, ensuring a focused and efficient development process. The customer expressed their satisfaction with the Minimal Value Product (MVP) scope and stated that any additional features implemented would be considered a bonus.

### 1. Minimal Value Product

- User Registration: Users can join and create an account to access the functionalities of the application.
- User Login: Users can log in to access the functionalities of the application.
- User Logout: Users can ensure the protection and privacy of their information and prevent unauthorised access.
- Add and Edit Books: Lenders can add books to the database of BookSwap and edit their details.
- Book Listing Management for Lenders: Lenders can create, list, update, and delete their book listings.
- Book Search for Borrowers: Borrowers can search for books based on the title and in the result list view basic book information and lender's name and email.
- Borrowers can contact lenders externally via email for borrowing requests.

### 2. Advanced functionalities

- Additional Information for Listed Books: Lenders can provide additional details such as location and condition for their listed books
- Advanced Book Search: Borrowers can search for books using various search criteria.
- Borrowing Requests: Borrowers can send borrowing requests through the app.
- Requested Books in Lender's List: Lenders can conveniently view requested books within their listed books section
- Request Management for Lenders: Lenders can accept or deny borrowing requests within the app.
- Requested Books Listing: Borrowers can view the list of their borrowed books.
- Request Status for Borrowers: Borrowers can view the status of their borrowing requests within their borrowed books list.
- Book Status Tracking: Book status will be color-coded based on due dates for both the lenders and borrowers.
- Lenders can contact the borrowers instead the other way around via external email.
- Book Image Upload: Lenders have the ability to upload images of books from their computer.
- Advanced Listing: Book information will be pre-filled based on the title if it was previously added to the database.

### 3. Nice to have functionalities

- Detailed Book Information: Lenders can provide and borrowers can view detailed book information, including descriptions.
- Account Management: Users can manage their account settings, such as changing their password or email address.
- Integration with an API for book data to autofill book details.
- Internal messaging system between borrowers and lenders.
- Users can rate and provide feedback on borrowed books.
- Administrator functionality (manage user accounts, moderate listings, admin dashboard).

**Target Audience:**

The target audience for BookSwap includes book enthusiasts and avid readers who are interested in sharing and borrowing books within a community. It caters to individuals who are looking for an online platform to connect with like-minded readers and access a diverse range of books.

**Tech Stack:**

| Category          | Tools                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------|
| Front-end         | HTML5, CSS3, JavaScript, [React.js](https://reactjs.org/), [Bootstrap](https://getbootstrap.com/), [React-Bootstrap](https://react-bootstrap.github.io/) |
| Back-end          | [Node.js](https://nodejs.org/en/), [Express.js](https://expressjs.com/), [Mongoose](https://mongoosejs.com/)   |
| Database          | [MongoDB](https://www.mongodb.com/)                                                     |
| Hosting           | [Netlify](https://www.netlify.com/), [Heroku](https://www.heroku.com/), [MongoAtlas](https://www.mongodb.com/atlas/database)                 |
| Testing           | [Jest](https://jestjs.io/)                                                               |
| Project Management| [Trello](https://trello.com), [Scrum](https://www.scrum.org/) , [Zoom](https://zoom.us/)                          |
| DevOps Tools      | [GitHub Desktop](https://desktop.github.com/), [GitHub](https://github.com/), [VS Code](https://code.visualstudio.com/)     |
| Design Tools      | [Figma](https://www.figma.com), [Logo](https://logo.com/), [Draw.io](https://app.diagrams.net/)                           |

## R2 - Dataflow Diagram

The data flow diagram incorporates the following aspects as agreed upon with Jozsef:
The inclusion of these elements enhances the clarity and comprehensiveness of the data flow diagram, ensuring that it effectively captures the desired processes and interactions within the system.

1. Diagram Separation: To ensure clarity and avoid clutter, the data flow diagrams are separated into distinct sections for signup-login, lending, and borrowing processes.
2. Happy Path: The diagram primarily captures the ideal flow of data during the various processes. However, it is essential to include error handling mechanisms to account for potential exceptions and error scenarios in the code.
3. MVP and Advanced Scope: The diagram encompasses both the Minimum Viable Product (MVP) and the Advanced scope elements. To distinguish the advanced scope components, they are highlighted in orange, indicating additional features beyond the MVP.
4. Process Orders: The diagram denotes the sequence of processes by assigning them numbers. Processes sharing the same number signify that any of them can commence at that point in the flow.
5. Multiple Queries and Database Order: In scenarios where multiple queries are required to fulfill a request, the diagram demonstrates the order (top to bottom) in which the database operations are executed. For instance, in the context of retrieving borrowed books, the diagram demonstrates the initial querying of the listings collection. Subsequently, utilising the gathered book IDs, a query to the book collection is executed to obtain the relevant details of those books. Finally, the acquired book details are retrieved and sent back to the backend for further processing.

![auth](./docs/authentication_dfd.drawio.png)
![lending](./docs/lending.drawio.png)
![borrowing](./docs/borrowing_dfd.drawio.png)

## R3 - Application Architecture Diagram

Regarding the architecture, the client requested a high-level overview that encompasses the various technologies involved in building a full stack application. The emphasis was placed on understanding the overall structure rather than delving into specific features. Additionally, Jozsef asked for a concise description to facilitate better comprehension of the tasks performed by the client, server, and database components.

![architecture](./docs/architecture.drawio.png)

The MERN stack architecture is a popular web development stack that consists of four key components: MongoDB, Express.js, React, and Node.js.

* **Client (React)**
In terms of the architecture, the client plays a crucial role as the front-end component of the application. It takes charge of rendering the user interface, handling user interactions, and facilitating site navigation. By utilising React, a powerful JavaScript library for building user interfaces, the client creates reusable components and effectively manages the application's state.
To exchange data with the server, the client communicates through API requests. These requests are used to retrieve data from the server or trigger specific actions. By sending these requests, the client can fetch the necessary information from the server's back-end.

* **Server (Node.js with Express.js, Mongoose)**
The server is built using Node.js, a JavaScript runtime, and Express.js, a web application framework for Node.js. The server handles incoming requests from the client, processes them, and returns responses. Express.js provides an organised way to define routes, controllers, and middlewares. Routes define the API endpoints, controllers handle the logic for each route, and middlewares perform tasks such as authentication or request parsing and so on. Mongoose is an Object Data Modeling (ODM) library for Node.js that provides a higher-level abstraction for MongoDB. It allows the definition of schemas and models to structure and interact with the data stored in MongoDB. Mongoose simplifies tasks like validation, querying, and performing operations on the database.

* **Database (MongoDB)**
MongoDB is a NoSQL database that stores data in flexible, JSON-like documents. It is used for persistent data storage in the MERN stack.

According to the current plan, the client application will be hosted on Netlify, the server will be hosted on Heroku, and the database will be hosted on MongoDB Atlas.

## R4 - User Stories

For the BookSwap application project with my client Konyvek.hu, we have adopted Scrum methodology to ensure an iterative and collaborative development process. Jozsef has been working closely with me to define and prioritise user stories that align with the project's goals. In our initial discussions, we identified a set of high-level user stories with 3 different personas (lender, borrower and admin) that served as a starting point for our work. As part of our agreement, we decided to prioritise and define the list of functionalities by assigning numbers to establish the order. This approach allows for transparency and incremental development to be implemented effectively. In addition to user stories, I will also define technical stories on the Trello Board to address specific technical aspects of the project.
To determine the scope of the Minimum Viable Product (MVP), we engaged in further discussions the following day to identify the user stories that are essential for the initial launch and would satisfy the customer's requirements. During these discussions, we finalised the user stories for the Minimal Viable Product (MVP). These user stories encompass functionalities designed to cater to both lenders and borrowers. It was also acknowledged that further changes could arise during the wireframing and flow diagramming process.

### Minimal Value Product

1. As a **user**, I need an informative landing page to evaluate the BookSwap platform and make an informed decision about joining.
2. As a **lender**, I want to be able to sign up to the BookSwap platform so that I can manage my book listings.
3. As a **lender**, I want to be able to log in to the BookSwap platform so that I can manage my book listings.
4. As a **borrower**, I want to be able to sign up to the BookSwap platform so that I can find books that can be borrowed.
5. As a **borrower**, I want to be able to log in to the BookSwap platform so that I that I can find books that can be borrowed.
6. As a **lender**, I want the ability to add new books to the BookSwap database if they are not already added, so I can add them to my listings.
7. As a **lender**, I want to edit the details of the books I have added to the database on BookSwap so that I can rectify any mistakes or inaccuracies.
8. As a **lender**, I want to create a book listing, so that I can share books I have available for borrowing.
9. As a **lender**, I want to view all my books listed, making it easy for me to see and manage them.
10. As a **lender**, I want the ability to edit the status of my listed books, so it will be clear to everyone when they are available.
11. As a **lender**, I want to delete a listed book, so that I can remove books that are no longer available for borrowing.
12. As a **borrower**, I want to be able to search for books by title that are available for borrowing, allowing me to find books that match my interests.
13. As a **borrower**, I want a clear display of search results that shows all available copies of books from different lenders, so I can make a decision on which book to borrow.
14. As a **borrower**, I want to view basic book information and the lender’s name and lender's email, so that I can contact them externally via email for borrowing requests.
15. As a **user**, I want the ability to securely log out of the application, ensuring that my platform details remain protected and inaccessible to unauthorised individuals.
16. As a **user** I would like to be able to navigate between the pages, so I can utilise every functionality.

Building upon the MVP, we also discussed additional functionalities during our subsequent meetings, which are categorised as advanced features.

### Advanced features

17. As a **lender**, I want  to provide additional information such as location and condition for my listed books, so it will be easier for borrowers to make more informed decisions.
18. As a **borrower**, I want to search for books using various criteria (e.g., title, author, location), so that I can find books more accurately and efficiently.
19. As a **borrower**, I want to request a book for borrowing through the app, so that I can easily communicate my interest in borrowing a specific book.
20. As a **lender**, I want to see requested books in my listed books section, so that I can conveniently manage and respond to requests.
21. As a **lender**, I want to accept or deny borrowing requests within the app, so that I can control the lending process and communicate my decision to borrowers.
22. As a **lender**, I want to the system to automatically set the due date to 3 weeks from now and list the borrower’s name and email address on the card, so I can communicate with borrower externally via email for lending details, meeting arrangements, and other discussions.
23. As a **borrower**, I want to list my borrowed books, so that I can track them.
24. As a **borrower**, I want to view the status of my borrowing requests in my borrowed books list, so that I can know whether my request is accepted.
25. As a **user**, I want the book status to be color-coded based on due dates, so that I can easily identify overdue books and those close to the due date.
26. As a **lender**, I would like the ability to upload images of books from my computer, so that I can have more options where images are sourced.
27. As a **lender**, I want the system to auto-fill the information of a book if that is added to the database previously, so the listing would be faster and more convenient.

Additionally, we briefly discussed future nice-to-have plans, which are defined at a higher level compared to the MVP and advanced functionalities fit to the agile eco-system.

### Nice to haves (these user stories are defined on high level)

28. As a **lender**, I want to provide more information about the book including condition, description, so the borrower can make an informed decision about borrowing and minimise disputes.
29. As a **borrower**, I want to view detailed book information, including descriptions and book condition, so that I can make informed decisions about borrowing.
30.	As a **user**, I want to manage my account settings, so that I can update my profile information, change my password, and modify my email or delete my account.
31.	As a **lender**, I want the platform to integrate with an external API for book data, so that book details can be auto filled based on title or other identifiers, saving time when creating listings.
32.	As a **user**, I want an internal messaging system between borrowers and lenders within the app, so that I can conveniently communicate and discuss lending details without relying on external email.
33.	As a **borrower**, I want to rate and provide feedback on borrowed books, so that I can share my experience and help others make informed decisions.
34.	As an **administrator**, I want to manage user accounts, moderate listings, moderate books, and have access to an admin dashboard, so that I can ensure the smooth operation of the platform and handle any necessary administrative tasks.

Following the definition of the user stories, we utilise Trello as a project management tool to create task cards for the MVP and advanced user stories and a collection to the nice to haves. By adopting this approach, we will be able to efficiently monitor and oversee the development process. As the project progresses, each user story will be further broken down into actionable steps. It is important to note that changes are a natural part of the process, and as such, the Trello Board will be continuously refined to accommodate any modifications.

## R5 - Wireframes

[WireFrames](https://www.figma.com/file/mGdliIbudJmbZTl0WUdvfE/bookSwap?type=design&node-id=0%3A1&mode=design&t=oiaLIOWpWt9wgLaB-1)

In collaboration with Jozsef, the wireframes were developed, incorporating the following overarching requirements obtained during our initial meeting:

1. High-fidelity wireframes to facilitate the client's visualisation of the final product.
2. The focus is on developing dedicated, targeted pages that cater to specific role based actions, like lending or borrowing, enabling users to complete all related tasks on a single page without the need to navigate through multiple different pages.
3. Advanced features are incorporated and visually distinguished in the wireframes through the use of orange highlighting or an orange frame.
4. Representation of various card states, including pending, accepted, overdue, and other relevant statuses, within the wireframe designs.

In order to ensure efficiency and adherence to the agile methodology, the wireframes presented below were developed through multiple iterations and meetings, closely aligned with the user stories for the development process. During these iterations options such as presenting book information in a table format or to present content on spreading out on separate pages were explored. Table format was not suitable for mobile view and the customer expressed a preference for a concise design that avoids the use of many separate pages. Furthermore, it was necessary to redesign the cards, particularly in tablet view, as the aspect ratio was significantly different from that of the search and book add forms, leading to readability issues with the cards.

Below the mobile view frames showcases the high-level connections between the pages and their functionalities incorporated. For optimal clarity, please open the image using an image viewer.

![High level connections](./docs/wireframes/high_level_functions_and_page_connections.png)

### Home Page

The home page features a navigation bar that displays the site's logo, along with login and join buttons. Placing these buttons in the navigation bar ensures easy access, as the login process is essential for utilising the application. Furthermore, the home page also includes an image, an introduction, and a book section. These elements are for providing users with a clear understanding of the page's purpose and content.
The spacing, font size, card dimensions, and form sizes, including the input fields, are appropriately adjusted for the desktop, tablet, and mobile views across all the pages. For easy contact with the company, the footer of every page includes social media icons.

| Desktop | Tablet | Mobile |
|---------|--------|--------|
|![Desktop home](./docs/wireframes/Desktop-Home.jpg)|  ![Tablet home](./docs/wireframes/Tablet-Home.jpg)      |  ![Mobile home](./docs/wireframes/Mobile-Home.jpg)      |

### Login and Join modal

The login and join process on the page is facilitated through the use of modals, which are displayed above the home page content upon clicking on the login or join button. This choice ensures that the modals are brought to the forefront, emphasising their importance in the user journey. Additionally, it enhances user convenience by keeping them within the context of the current page, eliminating the need for navigation to a different location which saves time and effort for users while providing visual continuity. Likewise, users can easily toggle between login and signup within the same interface, providing a cohesive and intuitive experience.

| Desktop | Tablet | Mobile |
|---------|--------|--------|
|![Desktop login](./docs/wireframes/Desktop_Login_modal.jpg)|  ![Tablet login](./docs/wireframes/Tablet_Login_modal.jpg)      |  ![Mobile login](./docs/wireframes/Mobile_Login_modal.jpg)      |

| Desktop | Tablet | Mobile |
|---------|--------|--------|
|![Desktop join](./docs/wireframes/Desktop_Join_modal.jpg)|  ![Tablet join](./docs/wireframes/Tablet_Join_modal.jpg)    |  ![Mobile join](./docs/wireframes/Mobile_Join_modal.jpg)      |

### Borrowing Page

As per the client's request, when users log in or join, they are directed to the borrowing page as based on client's data it is highly likely that more users are borrowers than lenders. The display of the hamburger menu in the navigation bar is triggered after the login-join process, ensuring ease of navigation for users. Within the advanced scope of the application, the top section of the page features a concise display of the borrowed books list. Given the standardised borrowing period of 3 weeks, typically no more than 2-3 books are showcased here at the same time. This efficient presentation ensures that the borrowed books list does not occupy excessive space, hence the placement.
For the borrowing page, a card-based display is used, providing a user-friendly interface. Depending on the status of the borrowing process (pending, accepted, or overdue), the card dynamically presents different borrowing information to the borrower. This tailored approach enhances the clarity and relevance of the displayed information and keep everything in the same page as was requested.
Below the borrowing section, a book search form is positioned, allowing users to search for and list available books. This search functionality enables users to quickly locate desired books from the collection. Moreover, within the advanced scope of the application, borrowers also have the capability to send borrow requests directly to the lenders.

| Desktop | Tablet | Mobile |
|---------|--------|--------|
|![Desktop borrowing](./docs/wireframes/Desktop_Borrowing.jpg)|  ![Tablet borrowing](./docs/wireframes/Tablet_Borrowing.jpg)    |  ![Mobile borrowing](./docs/wireframes/Mobile_Lending.jpg)      |

### Lending Page

A book adding form has been implemented alongside the book listings on the lending page. This form allows users to add books to the collection if they are not already included. Below the form, users can find their listed books. Initially, separate tables were created to list the added books and for tracking book requests states. However, this approach proved to be less user-friendly on mobile devices and resulted in a visually complex page layout. Consequently, an alternative solution was sought.
The current card-based solution provides an intuitive and user-friendly interface. The use of color coding aids users in quickly identifying the state of each card, which is crucial information for lending purposes. For instance, if a book is overdue, the book card border is highlighted in red. Additionally, depending on the status, the lending information section of the card presents relevant details. For example, if a book is requested, the card border is purple, and it displays the borrower's name and request date, along with accept and deny icons. Notably, lenders have the ability to modify book details and their own listing information. However, within the "nice to have" scope, only administrators are granted the authority to modify book details.

| Desktop | Tablet | Mobile |
|---------|--------|--------|
|![Desktop lending](./docs/wireframes/Desktop_Lending.jpg)|  ![Tablet lending](./docs/wireframes/Tablet_Lending.jpg)    |  ![Mobile lending](./docs/wireframes/Mobile_Lending.jpg)      |

As per our previous agreement with Jozsef, following the data flow diagram and wireframing, user stories will be revised and updated as the next step.

## R6 - Trello Board

[bookSwap Trello Board](https://trello.com/b/BfJSkwUq/bookswap)

Initial setup of the Trello Board for the documentation of the project.

![initial setup](./docs/Trello_initial_setup_2023-06-30.png)

The following working day the documentation progress

![documentation card](./docs/Trello_documentation_2023-07-03.png)

After the discussions on user stories, the Trello Board was established, incorporating the agreed-upon user stories.

![mvp](./docs/Trello_MVP_2023-07-03.png)
![advanced and nth](./docs/Trello_advanced_and_nice_2023-07-03.png)

These screenshots illustrate the progress I made on the tasks outlined for the readme file, including the creation of the data flow diagram, application architecture, and wireframes.

![DFD](./docs/Trello_documentation_DFD_%202023-07-05.png)
![AAD](./docs/Trello_documentation_AAD_%202023-07-05.png)
![Wireframes](./docs/Trello_wireframes_%202023-07-07.png)

As mentioned previously, the user stories underwent refinement during the creation of the DFD diagram and wireframes, leading to updates and improvements.

![Updated user stories 1](./docs/Trello_user_stories_update_2023-07-09.png)
![Updated user stories 2](./docs/Trello_user_stories_update_2_2023-07-09.png)