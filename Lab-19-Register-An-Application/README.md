# Lab 19 – Register an Application

## Objective

This lab focused on registering and configuring an application in Microsoft Entra ID. The exercise included configuring authentication settings, creating application credentials, exposing an API with delegated scopes, and creating a custom Microsoft Entra role using least-privilege permissions.

## Skills Practiced

- Microsoft Entra ID App Registrations
- Application authentication configuration
- Redirect URI configuration
- Client secrets and application credentials
- API exposure and delegated permission scopes
- User and administrator consent
- Microsoft Entra custom roles
- Least-privilege access management
- Application and service principal credential management

---

## Exercise 1 – Register and Configure an Application

### Step 1 – Register Demo App

Created a new application registration named **Demo app** within Microsoft Entra ID using the organization's single-tenant configuration.

![Register Application](01-App-Registration.png)

![Demo App Overview](02-Demo-App-Overview.png)

### Step 2 – Configure Web Authentication

Configured the application to use the **Web** platform and added the following redirect URI:

`https://localhost`

![Web Redirect URI](03-Web-Redirect-URI.png)

### Step 3 – Create Application Credential

Created a client secret named:

`SC300 lab secret`

The credential was configured with a **90-day (3 month)** expiration.

> Security Note: The client secret value was intentionally not captured or stored in this repository.

![Client Secret Created](04-Client-Secret-Created.png)

### Step 4 – Expose an API

Configured the Demo app to expose an API and created the following delegated permission:

**Employees.Read.All**

Consent configuration:

- Admins and users
- Read-only access to employee records
- State: Enabled

![Employees Read Scope](05-Employees-Read-Scope.png)

### Step 5 – Configure Admin-Only API Scope

Created an additional delegated permission:

**Employees.Write.All**

Consent configuration:

- Admins only
- Write access to employee records
- State: Enabled

![Employees Write Scope](06-Employees-Write-Scope.png)

The application now exposes both read and write scopes with different consent requirements.

![API Scopes Configured](07-API-Scopes-Configured.png)

---

## Troubleshooting – Application ID URI

The lab originally specified the following Application ID URI:

`api://DemoAppAPI`

The Microsoft Entra tenant rejected this URI because the tenant's identifier URI policy required newly created Application ID URIs to contain a verified domain, tenant ID, or application ID.

To resolve the issue, I used the application's unique **Application (client) ID** in the Application ID URI:

`api://<application-client-id>`

This allowed the Application ID URI to be successfully registered while satisfying the tenant's identifier URI policy.

---

## Exercise 2 – Create a Custom Application Role

Created a Microsoft Entra custom role named:

**My custom app role**

The role was configured using least-privilege permissions specifically related to application and service principal credential management.

The following permissions were assigned:

`microsoft.directory/servicePrincipals/managePasswordSingleSignOnCredentials`

`microsoft.directory/servicePrincipals/synchronizationCredentials/manage`

![Custom Role Permissions](08-Custom-Role-Permissions.png)

### Review Custom Role

Verified the custom role name and selected permissions before creation.

![Custom Role Review](09-Custom-Role-Review.png)

### Custom Role Created

Successfully created **My custom app role** in Microsoft Entra ID.

![Custom Role Created](10-Custom-Role-Created.png)

---

## Key Takeaways

This lab provided hands-on experience with the relationship between **application registrations, authentication, credentials, API permissions, consent, and Microsoft Entra roles**.

The lab also demonstrated the importance of **least-privilege access**, particularly when delegating application credential-management capabilities.

A key troubleshooting lesson was understanding how tenant security policies can restrict Application ID URI formats and how the application's unique client ID can be used to satisfy those requirements.

---

## Technologies Used

- Microsoft Entra ID
- Microsoft Entra Admin Center
- App Registrations
- OAuth 2.0 permission scopes
- Application credentials
- Microsoft Entra RBAC
