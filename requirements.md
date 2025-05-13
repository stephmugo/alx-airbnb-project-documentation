
# Airbnb Clone - Backend Feature Requirements

## 1. User Authentication

### Objective
Handle user registration, login, and authentication securely.

### API Endpoints
- **POST /api/auth/register**
  - Input: JSON
    ```json
    {
      "first_name": "John",
      "last_name": "Doe",
      "email": "john@example.com",
      "password": "password123",
      "phone_number": "1234567890",
      "role": "guest"
    }
    ```
  - Output: JSON
    ```json
    {
      "message": "User registered successfully",
      "user_id": "uuid"
    }
    ```

- **POST /api/auth/login**
  - Input: JSON
    ```json
    {
      "email": "john@example.com",
      "password": "password123"
    }
    ```
  - Output: JSON
    ```json
    {
      "token": "jwt-token",
      "user_id": "uuid",
      "role": "guest"
    }
    ```

### Validation Rules
- Email must be unique and valid format.
- Password must be at least 8 characters.
- Role must be one of [guest, host, admin].

### Performance Criteria
- Registration/Login should complete within 300ms under normal load.
- Support up to 100 concurrent requests.

---

## 2. Property Management

### Objective
Allow hosts to list, update, and manage properties.

### API Endpoints
- **POST /api/properties**
  - Input: JSON
    ```json
    {
      "host_id": "uuid",
      "name": "Cozy Apartment",
      "description": "A nice place to stay",
      "location": "Nairobi",
      "pricepernight": 50.00
    }
    ```
  - Output: JSON
    ```json
    {
      "message": "Property listed successfully",
      "property_id": "uuid"
    }
    ```

- **PUT /api/properties/{property_id}**
  - Input: JSON
    ```json
    {
      "name": "Updated Name",
      "description": "Updated description",
      "pricepernight": 60.00
    }
    ```

### Validation Rules
- Price must be positive decimal.
- Host ID must reference an existing user with role `host`.

### Performance Criteria
- Listing property should complete within 500ms.
- Update should propagate within 1 second.

---

## 3. Booking System

### Objective
Enable guests to book properties and manage bookings.

### API Endpoints
- **POST /api/bookings**
  - Input: JSON
    ```json
    {
      "user_id": "uuid",
      "property_id": "uuid",
      "start_date": "2025-06-01",
      "end_date": "2025-06-05"
    }
    ```
  - Output: JSON
    ```json
    {
      "message": "Booking created successfully",
      "booking_id": "uuid",
      "total_price": 200.00
    }
    ```

- **GET /api/bookings/{user_id}**
  - Output: JSON
    ```json
    [
      {
        "booking_id": "uuid",
        "property_id": "uuid",
        "start_date": "2025-06-01",
        "end_date": "2025-06-05",
        "status": "confirmed"
      }
    ]
    ```

### Validation Rules
- Dates must not overlap existing bookings for the same property.
- User and property IDs must exist.

### Performance Criteria
- Booking creation should complete within 800ms.
- Support at least 50 simultaneous booking requests.
