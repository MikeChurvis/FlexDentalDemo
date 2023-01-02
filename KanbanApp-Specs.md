# Kanban App Specifications

## API

This is what the server does. Each heading in this section is a category of actions. Each action in a category is defined as a three-step function:

1. **Requires:** Assertions about the data that the action needs in order to proceed, i.e. Request + Validation.
2. **Performs:** An overview of what the action does once it has that data.
3. **Returns:** What the action returns to the invoker once it's done, i.e. a Response.

> [!important]
> All actions may return a generic "something went wrong" error. The Client must account for this at each point of interaction with the API. All such errors will contain an Error Reference ID corresponding to an entry in the API's logs.

### Authentication

Foundational user self-management actions.

#### Sign-Up Request

Requires:

- The user must be signed out.
- A User ID is required.
- A Display Name is required.
- A Password is required.
- The User ID must be at least 8 characters long.
- The User ID must be no more than 20 characters long.
- The User ID must contain only letters, numbers, and hyphens.
- The Display Name must be at least 3 characters long.
- The Display Name must be no more than 30 characters long.
- The Password must be valid according to Django's default authentication scheme.

Performs:

- Create a new user account with the given details.
- Generate a new session for that account.

Returns:

- Status 200.
- A login token.

#### Log In Request

Requires:

- The user must be logged out.
- A User ID is required.
- A Password is required.
- The User ID and Password must correspond to an existing user account.

Performs:

- Creates a new session for the given user account.
- Generates a login token for the session.

Returns:

- Status 200.
- A login token.

#### Log Out Request

Requires:

- The user must be logged in.

Performs:

- Invalidates the session corresponding to the user's given login token.
- Notifies all connected boards that this user has logged out.

Returns:

- A statement of success.

#### Change Display Name Request

Requires:

- The user must be logged in.
- A Display Name is required.
- The the Display Name must be valid according to the rules shown in [Sign Up Request](#sign-up-request).

Performs:

- Changes the Display Name field in the user's account.
- Notifies all boards that the user is using that the username has changed.

Returns:

- Status 200
- The user's new display name.

#### Destroy Account Request

Requires:

- The user must be logged in.
- A User ID is required.
- A Password is required.
- The User ID and Password must belong to the account of the user making the request.

Performs:

- Invalidates all sessions for that account.
- Notifies all boards that the user has logged out.
- Sets the User ID field for all DB tables related to the user account to a Deleted User Sentinel Value.
- Drops the user's account from the DB.

Returns:

- Status 200.
