# News Portal System
# Use Case Diagram
The use case diagram depicts the interactions between users and the system of a news portal.
# Actors:
1. Admin: Represents the administrator of the news portal.
2. User: Represents any user who interacts with the news portal.
# Use Cases:
1. Login: Both the admin and users need to login to access the system.
2. Manage Category: The admin manages categories of news.
3. Manage Subcategory: The admin manages subcategories under each category.
4. Manage Post: The admin creates, edits, and manages news posts.
5. Manage Page Data: The admin manages the content of various pages in the news portal.
6. Manage Comment: The admin manages comments on the news posts.
7. Update: Allows the admin to update their password.
8. Visit News Portal: Users can browse and read the news content.
9. Search for News: Users can search for specific news using keywords or filters.
10. View News Category: Users can view news based on categories.
11. Leave Comment: Users can leave comments on news posts.
12. View Page Data: Users can view details about specific pages within the news portal.
# Relationships:
1. Includes: Indicates that one use case contains the functionality of another. For instance, "Manage Category" includes "Manage Subcategory" as a subcategory is managed within a larger category.
2. Extends: Indicates that one use case provides an optional or alternative functionality to another. For example, "Logout" extends "Login" as the user can log out of the system after a login.
# System Sequence Diagram
The system sequence diagram depicts the interaction between a User and the News Portal system when the User attempts to create a new post. Here's a breakdown of the steps:
1. User Initiates Post Creation:
The user interacts with the News Portal system, intending to create a new post.
2. User Sends Request:
The user provides the required information, including the title, content, and category of the post. This information is sent as a request to the system.
3. System Validates Data:
The News Portal system receives the request and starts validating the provided data. This step ensures that the user-supplied data is valid and conforms to the system's requirements.
4. System Stores the Post:
If the data validation is successful, the system stores the post in the database, thereby creating the new post.
5. System Sends Confirmation:
The system sends a confirmation message back to the user indicating the success or failure of the post creation process.
If the post was created successfully, the user receives a success message.
If there was an error during validation or storage, the user receives a failure message, possibly with error details.
# Communication Diagram
This diagram illustrates the flow of events in a news portal system when a user creates a new post. Let's break it down step by step:
1. User Interface: The user starts by initiating the creation of a new post through the user interface. This could be done via a button, form, or other UI element.
2. Controller: The user interface sends a "create post" request to the controller. The controller is the entry point for handling this request.
3. Service: The controller delegates the task of creating the post to the service layer. The service is responsible for business logic and data validation.
4. Validation: The service checks if the provided post data is valid. This may include things like ensuring all required fields are filled, validating formatting, and potentially checking for duplicate content.
5. Repository: If the post data is valid, the service saves it to the database through the repository. The repository interacts with the database to persist the post.
6. Confirmation: Once the post is saved, the service generates a confirmation and sends it back to the controller. This confirmation might include a message indicating success and potentially some information about the newly created post.
7. Display Confirmation: The controller receives the confirmation from the service and displays it to the user through the user interface. This provides feedback to the user that their action was successful.
# Important Notes:
1. Layers: Communication diagram illustrates a common layered architecture (UI, Controller, Service, Repository) in software development.
2. Separation of Concerns: Each layer focuses on a specific set of responsibilities. This promotes maintainability and scalability.
3. Error Handling: Real-world implementations would include error handling mechanisms to gracefully deal with failures at any point in the process.
# Class Diagram
The class diagram represents a news portal system with different entities like Category, Subcategory, Posts, Comments, Pages, and Admin. 
# Entities:
1. Category: This entity defines different categories like News, Sports, Entertainment, etc.
2. SubCategory: A subcategory further refines the category, for example, "Sports" can have subcategories like "Cricket", "Football", etc.
3. Posts: This is the core entity representing individual news articles or blog posts. It stores information like the post title, content (Post Detail), category and subcategory information, author details, posting date, update date, whether the post is active or inactive.
4. Comments: This entity holds comments associated with a particular post.
5. Pages: This entity likely refers to static pages like 'About Us', 'Contact Us', 'Terms & Conditions', etc.
6. Admin: This entity represents an administrator who has the privilege to manage the website content, including creating, editing, and deleting posts.
# Communication Diagram incorporates several GRASP principles:
The "Create Post" use case of news portal system, in its communication diagram incorporates several GRASP (General Responsibility Assignment Software Patterns) principles;
1.	Controller: 
The PostController handles the user's input and coordinates the creation of a post. It’s responsible for delegating the validation and saving processes to other objects.
2.	Information Expert: 
The PostService has the expertise needed to validate and save the post. It contains the logic required for these operations, making it the right choice for handling the validation.
3.	Low Coupling: 
The interactions between the PostController, PostService, and PostRepository aim to keep dependencies between objects minimal. Each class handles specific tasks, reducing direct dependencies on other classes.
4.	High Cohesion: 
Each object (e.g., PostController, PostService, PostRepository) has a well-defined role. This specialization helps maintain focus, making each object highly cohesive. For example, PostRepository is solely responsible for saving the data to the database.
5.	Creator: 
The PostRepository creates and stores the Post object. Since it manages access to the database, it makes sense for it to handle the instantiation and storage of post data.
