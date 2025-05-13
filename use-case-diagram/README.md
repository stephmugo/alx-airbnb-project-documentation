# Design the Use Case Diagram of the Features and Functionalities

## Objective

Visualize the interactions between users (**actors**) and the **Airbnb Clone backend system** using a **use case diagram**, capturing key functionalities such as user registration, property booking, payments, and other features.

---

## Diagram Details

The `use_case_diagram.png`, created using **Draw.io**, illustrates the **Airbnb Clone backend’s** use cases and actor interactions.

### Actors

- **Guest**  
  - Books properties  
  - Makes payments  
  - Writes reviews  
  - Sends/receives messages

- **Host**  
  - Manages properties  
  - Responds to bookings  
  - Communicates with guests

- **Admin**  
  - Manages users  
  - Manages properties  
  - Manages bookings  
  - Monitors analytics

### Use Cases

- **User Authentication**  
  - Register  
  - Login  
  - Manage Profile

- **Property Management**  
  - Create Property  
  - Update Property  
  - Delete Property  
  - List Properties  
  - View Property Details

- **Booking System**  
  - Book Property  
  - Cancel Booking  
  - Update Booking Status  
  - View Bookings

- **Payment System**  
  - Process Payment  
  - View Payment History

- **Review System**  
  - Write Review  
  - View Reviews

- **Messaging System**  
  - Send Message  
  - Receive Message  
  - View Message Threads

- **Admin Features**  
  - Manage Users  
  - Manage Properties  
  - Monitor Bookings/Payments  
  - View Analytics

### Relationships

- **Associations**:  
  Lines connecting actors to use cases (e.g., *Guest → Book Property*)

- **Include**:  
  Certain actions require Login (e.g., *Book Property*, *Create Property*)

- **Extend**:  
  *Cancel Booking* extends *Book Property*


## Purpose

This diagram clarifies how different user roles **interact** with the system, helping to:

- Guide backend development  
- Ensure accurate implementation of user-specific functionality
