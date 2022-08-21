```mermaid
participant User
participant Login_Page
participant Database
User->>+Login_Page: Visit
User->>+Login_Page: Enter a username/password
User->>+Login_Page: Login
Login_Page->>-Database: Send username/password hash
Database->>Database: Validate user data
alt Login data is correct
Database-->>+Login_Page: User login accepted
Login_Page->>+Login_Page: Redirect
Login_Page-->>-User: Successful login (message)
else Login data is incorrect
Database-->>Login_Page: User login rejected 
Login_Page->>Login_Page: Redirect
Login_Page-->>User: Clear the password field
end
```
