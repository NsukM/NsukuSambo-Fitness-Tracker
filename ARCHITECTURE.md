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
