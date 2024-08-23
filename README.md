# authentication-and-authorisation-with-expressjs

## Understanding Authentication and Authorization

### Authentication vs. Authorization

Authentication is the process of verifying the identity of a user. When a user logs in, they provide credentials (e.g., username and password) which the system checks to confirm their identity. If the credentials match, the user is authenticated and allowed to access the system.

Authorization, on the other hand, determines what an authenticated user is allowed to do. Once the user’s identity is confirmed, the system checks what permissions they have. For example, a regular user may only be able to view and edit their own data, while an administrator may have access to manage all users in the system.

### Scenario: Deleting a User Account

In the context of this project, the task was to implement a feature allowing users to delete an account. This action is protected by both authentication and authorization:

Authentication ensures that the request to delete an account comes from a legitimate user who is logged in.
Authorization checks if the authenticated user has the right to delete the account. For example, a user should only be able to delete their own account unless they have elevated permissions (e.g., admin privileges).

#### **_Is Allowing Deletion After Authentication a Good Idea?_**

Allowing users to delete any account after simply being authenticated is generally not a good idea. While authentication ensures the user is who they say they are, it doesn’t restrict actions based on their role or permissions. If a regular user could delete any account, it could lead to serious security issues, such as unauthorized deletion of other users' accounts.

Best Practice: The deletion functionality should be protected by both authentication and authorization. For instance:

Regular users can only delete their own accounts.
Admin users can delete any account, but even this action should be carefully controlled and logged.
In summary, while authentication confirms identity, authorization defines what actions that identity is allowed to perform. Both are critical in maintaining a secure system.
