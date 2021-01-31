# Coffee Shop Frontend

### Installing Dependencies

This project depends on Nodejs and Node Package Manager (NPM)..

#### Installing Ionic Cli

The Ionic Command Line Interface is required to serve and build the frontend.

### Authentication

The authentication system used for this project is Auth0. `./src/services/auth.service.ts` contains the logic to direct a user to the Auth0 login page, managing the JWT token upon successful callback, and handle setting and retrieving the token from the local store. This token is then consumed by  DrinkService (`./src/services/auth.service.ts`) and passed as an Authorization header when making requests to backend.

### Authorization

The Auth0 JWT includes claims for permissions based on the user's role within the Auth0 system. This project makes use of these claims using the `auth.can(permission)` method which checks if particular permissions exist within the JWT permissions claim of the currently logged in user. This method is defined in  `./src/services/auth.service.ts` and is then used to enable and disable buttons in `./src/pages/drink-menu/drink-form/drink-form.html`.
