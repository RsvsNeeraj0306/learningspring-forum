

# Notification System Documentation

## Introduction

In the fast-paced world of online interactions, staying informed is key to keeping users engaged and informed about relevant activities. Notifications play a pivotal role in delivering real-time updates, ensuring that users are aware of important events within our platform. 

In this documentation, we explore our Notification System, designed to enhance the user experience by delivering timely notifications whenever a significant event occurs. Our system is specifically tailored to notify a logged-in user about various actions within our platform. These actions include:

- **Likes**: When another user likes content created by the logged-in user.
- **Comments**: When another user leaves a comment on the logged-in user's content.
- **Replies**: When a reply is made to a comment or when the logged-in user's comment is replied to.

Our Notification System leverages Java, Spring Boot, and JPA to efficiently manage and deliver notifications, ensuring that users are always in the loop.

## Notification Page

To provide a user-friendly interface for viewing notifications, we have created an HTML page that displays notifications to the logged-in user. 

## Notification Repository

The `NotificationRepository` is a Spring Data JPA repository responsible for managing notifications in the application.

### Custom Query Methods

1. **findByUserOrderByCreatedAtDesc**
   - Description: Retrieves a list of notifications for a specific user and orders them by the creation timestamp in descending order (most recent notifications first).
   - Method Signature: `List<Notification> findByUserOrderByCreatedAtDesc(User user)`
   
2. **findAll**
   - Description: Retrieves all notifications in the database.
   - Method Signature: `List<Notification> findAll()`

# Entity-Relationship Diagram Explanation

In this section, we provide an explanation of the Entity-Relationship (ER) diagram that illustrates the structure and relationships within our database. The ER diagram is a visual representation of how data is organized in our system. Below, we describe key elements of the diagram:

[ER Diagram]([learningspring/er.PNG at main · RsvsNeeraj0306/learningspring ](https://github.com/RsvsNeeraj0306/learningspring/blob/main/er.PNG))






## Notification Entity

The `Notification` entity represents notifications in the application.

### Attributes

1. `id` (Primary Key)
   - Description: An auto-generated primary key for the notification.
   - Data Type: Integer

2. `notificationType`
   - Description: Stores the type of notification (e.g., "like," "comment").
   - Data Type: String

3. `message`
   - Description: Stores the message associated with the notification.
   - Data Type: String

4. `createdAt`
   - Description: A timestamp indicating when the notification was created.
   - Data Type: Date
   - Annotation: `@CreationTimestamp`

### Relationships

1. `user`
   - Description: A many-to-one relationship with the `User` entity, representing the user to whom the notification belongs.
   - Data Type: User entity

2. `post`
   - Description: A many-to-one relationship with the `Post` entity, indicating the post associated with the notification.
   - Data Type: Post entity

### Annotations

- `@Entity`: Marks the class as a JPA entity.
- `@Data` (Project Lombok): Generates common boilerplate code automatically.


## Conclusion

In this comprehensive documentation, we have delved into the intricacies of our Notification System, designed to enhance the user experience and keep users informed about important events on our platform. We have covered various aspects of our system, including its components, functionalities, and implementation details.

As you have seen, our Notification System, powered by Java, Spring Boot, and JPA, plays a crucial role in delivering real-time updates to our users. It keeps them informed about activities such as likes, comments, and replies, ensuring that they remain engaged and connected with our platform.

We have also provided a detailed explanation of our Entity-Relationship (ER) diagram, offering insights into how data is organized and relationships are established within our database. This visual representation helps you understand the core structure of our system.


## Done by

This documentation was created by:

- RSVS Neeraj
- Bibhu Sunder Pattanaik

