# NsukuSambo Fitness Tracker Architecture

## C4 Diagrams

### 1. Context Diagram
The context diagram provides a high-level overview of the system and its interactions with users and external systems.

```mermaid
C4Context
  title System Context Diagram for NsukuSambo Fitness Tracker

  Person(user, "User", "A person who wants to track their fitness activities.")
  System(fitnessTracker, "NsukuSambo Fitness Tracker", "Tracks fitness activities and provides insights.")
  System(wearableDevice, "Wearable Device", "Tracks user's physical activities (e.g., steps, heart rate).")
  System(mobileApp, "Mobile App", "Provides a user interface for viewing fitness data.")

  Rel(user, fitnessTracker, "Uses")
  Rel(fitnessTracker, wearableDevice, "Receives data from")
  Rel(fitnessTracker, mobileApp, "Sends data to")


C4Container
  title Container Diagram for NsukuSambo Fitness Tracker

  Container(mobileApp, "Mobile App", "React Native", "Provides a user interface for viewing fitness data.")
  Container(backend, "Backend Server", "Node.js with Express", "Handles business logic and data processing.")
  Container(database, "Database", "MongoDB", "Stores user data and fitness metrics.")
  Container(cloud, "Cloud Services", "AWS", "Provides data storage and processing capabilities.")

  Rel(user, mobileApp, "Uses")
  Rel(mobileApp, backend, "Sends/Receives data")
  Rel(backend, database, "Reads/Writes data")
  Rel(backend, cloud, "Uses for data storage and processing")


C4Component
  title Component Diagram for NsukuSambo Fitness Tracker Backend

  Component(api, "API Gateway", "Express.js", "Handles incoming requests from the mobile app.")
  Component(auth, "Authentication Service", "Node.js", "Manages user authentication and authorization.")
  Component(dataProcessor, "Data Processor", "Node.js", "Processes fitness data from wearable devices.")
  Component(databaseService, "Database Service", "MongoDB", "Manages interactions with the database.")

  Rel(api, auth, "Uses")
  Rel(api, dataProcessor, "Uses")
  Rel(dataProcessor, databaseService, "Reads/Writes data")
