# Mini-Zanzibar: Global Authorization System

## Tech Stack
- **Frontend**: React (located in `front` folder)
- **Backend**: Spring Boot (located in `back` folder)
- **Database**: LevelDB (for ACL storage), Consul (for namespace configuration)
- **Reverse Proxy**: Nginx (or any other reverse proxy that serves static content)
- **Authorization System**: Custom implementation of Google Zanzibar (located in `zanzibar` folder)

## Description

This project is a simplified implementation of Google's Zanzibar global authorization system. It supports flexible access control policies, stores and evaluates ACLs, and provides consistent and scalable authorization decisions with low latency and high availability.

Key features:
1. **ACL Management**: Create, update, and check access control lists (ACLs).
2. **Namespace Configuration**: Define object-user relations (e.g., owner, editor, viewer) and access rules.
3. **Roles**: Users can be assigned roles such as owner, editor, or viewer for uploaded content (images/videos).
   - **Owner**: Can modify/delete content and share access.
   - **Editor**: Can modify tags/names but cannot delete content.
   - **Viewer**: Can only view content.
4. **Proof of Concept**: Users can register, upload images/videos, assign tags, and define access rights for other users.

## How to Run

1. Clone the repository:
    ```
    git clone https://github.com/VukRadmilovic/mini-zanzibar.git
    ```
2. Install the necessary dependencies for the frontend and backend.

3. Ensure that **LevelDB** and **Consul** are properly installed and configured. 

4. Navigate to the `zanzibar` folder and run the authorization service:
    ```
    cd zanzibar
    mvn spring-boot:run
    ```

5. Navigate to the `back` folder and run the backend:
    ```
    cd back
    mvn spring-boot:run
    ```

6. Navigate to the `front` folder and run the frontend:
    ```
    cd front
    npm install
    npm run dev
    ```

7. Configure and run Nginx or any other reverse proxy to serve the static content.


8. Access the application at:
    ```
    http://localhost:80
    ```
