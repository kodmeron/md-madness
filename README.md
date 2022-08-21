```mermaid
User->>+Login Page: Visit
User->>+Login Page: Enter a username/password
User->>+Login Page: Login
Login page->>-Database: Send username/password hash
Database->>Database: Validate user data
alt Login data is correct
Database-->>+Login Page: User login accepted
Login Page->>+Login Page: Redirect
Login Page-->>-User: Successful login (message)
else Login data is incorrect
Database-->>Login Page: User login rejected 
Login Page->>Login Page: Redirect
Login Page-->>User: Clear the password field
end
```
