
# PJBL Project - C4 Model and Arc42 Topics

## 1. Arc42 Topic 1: System Scope and Context
This section describes the overall context and scope of the system.

### PJBL System Context Diagram (C4 Model - Level 1)
```mermaid
C4Context
    title PJBL System Context Diagram
    Boundary(SystemBoundary_PJBL, "PJBL System") {
        Person(User, "End User")
        Person(Admin, "Administrator")

        System(PJBL_System, "PJBL", "Customizable Sports Activity Tracker")

        User -> PJBL_System: Uses the platform to track activities
        Admin -> PJBL_System: Manages users and system settings
    }
```

### Arc42 - Context and Constraints
- The system supports users tracking sports activities.
- Administrators are responsible for user management and system settings.
- External constraints include data privacy regulations and integration with third-party devices.

---

## 2. Arc42 Topic 2: Solution Strategy
This section outlines the high-level strategy of how the solution is built.

### Technologies and Architecture
- **Frontend**: ReactJS for a responsive and modern interface.
- **Backend**: Node.js for API development and Python for data analysis.
- **Database**: MongoDB for storing user activity data.
- **Cloud**: Deployed on Google Cloud Platform (GCP) for scalability and reliability.

---

## 3. Arc42 Topic 3: Building Blocks
This section provides an overview of the main building blocks of the system.

### PJBL System Container Diagram (C4 Model - Level 2)
```mermaid
C4Container
    title PJBL System Container Diagram
    Person(User, "End User")
    Person(Admin, "Administrator")

    System_Boundary(PJBL_System, "PJBL") {
        Container(WebApp, "Web Application", "ReactJS", "User interface for tracking activities")
        Container(API, "Backend API", "Node.js", "Handles business logic and API requests")
        Container(Database, "MongoDB", "Stores user data and activity records")
        Container(DataAnalysis, "Python Data Analysis Module", "Python", "Analyzes user activity data and generates reports")
    }

    User -> WebApp: Interacts with UI
    WebApp -> API: Sends API requests for data
    API -> Database: Reads/Writes user data
    API -> DataAnalysis: Triggers data analysis tasks
    Admin -> WebApp: Accesses admin functionalities
```

### Building Blocks
- **Web Application**: ReactJS-based frontend to allow users to track and view their activities.
- **Backend API**: A Node.js-based API that handles all business logic, including user authentication and activity tracking.
- **Database**: MongoDB as the primary data store for users, activities, and reports.
- **Data Analysis Module**: Python scripts and libraries that analyze activity data and produce user reports.
