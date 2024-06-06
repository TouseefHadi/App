# App
This project is a web application developed with FastAPI, SQLAlchemy, and MySQL, following the MVC (Model-View-Controller) design pattern. The application offers endpoints for user authentication (signup and login) and post management (create, retrieve, and delete posts). It uses JWT for secure authentication and in-memory caching for efficient data retrieval.

Project Structure
The project is organized into the following directories and files:

app: Contains the core application code.
main.py: Entry point of the application, initializes FastAPI app, and includes routers.
models.py: Defines SQLAlchemy models for User and Post.
schemas.py: Contains Pydantic models for request and response validation.
database.py: Configures the database connection.
routes: Contains route definitions.
auth.py: Handles user signup and login.
posts.py: Manages post creation, retrieval, and deletion.
crud: Contains CRUD operations.
auth.py: Manages user-related database operations.
posts.py: Manages post-related database operations.
utils: Contains utility functions.
auth.py: Provides authentication utilities like password hashing and token creation.
cache.py: Implements in-memory caching.
Endpoints
Signup (/auth/signup): Accepts email and password, returns a JWT token.
Login (/auth/login): Accepts email and password, returns a JWT token.
AddPost (/posts/addpost): Accepts text and a token, validates payload size (max 1 MB), saves the post, and returns postID.
GetPosts (/posts/): Requires a token, returns all user's posts, and caches responses for up to 5 minutes.
DeletePost (/posts/post/{post_id}): Accepts postID and a token, deletes the corresponding post.
Key Features
Authentication: Utilizes JWT for secure user authentication.
Database Integration: Uses SQLAlchemy for ORM and MySQL for data storage.
Field Validation: Employs Pydantic models for robust data validation.
Dependency Injection: Efficiently manages dependencies such as database sessions and user authentication.
Caching: Implements in-memory caching to enhance performance for retrieving posts.
