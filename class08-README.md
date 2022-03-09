# Access Control (ACL)

* When is Basic Authorization used vs. Bearer Authorization?

*The basic Auth: allows you to directly access the API using your user/password credentials.Integration with reporting tools is an example of how this might be used.*

*Bearer Token: When possible, it is the recommended authentication technique. It's perfect for scripting, designing external apps, and integrating with third-party software.*

* What does the JSON Web Token package do?

*is an open standard that allows two parties, a client and a server, to share security information. JSON items, containing a set of claims, are encoded in each JWT. JWTs are signed with a cryptographic algorithm to ensure that the claims can't be changed after they've been distributed.*

* What considerations should we make when creating and storing a SECRET?

1. Add.env to.gitignore to prevent it from being pushed online.
2. Save the SECRET in the.env file.
3. Never store secrets in.git repositories that aren't encrypted.
4. When using git, avoid using the git add * commands.
5. Make a.gitignore file for sensitive files.
6. Don't rely on code reviews to figure out what's going on.
7. Don't disclose sensitive information in unencrypted messaging platforms like Slack.
8. Keep your secrets protected.
9. Control API permissions and access.

## Term

+ encryption: Encryption is a method of securing digital data that involves the use of one or more mathematical procedures, as well as a password or "key" to decrypt the data. The encryption procedure converts data using an algorithm that renders the original data unreadable. 

+  Access: Access tokens are used by programs to make API queries on a user's behalf. The access token denotes a certain application's permission to access specified elements of a user's data.

+ bearer: The most common type of access token used with OAuth 2.0 is a Bearer. A Bearer Token is an obfuscated string that has no meaning for the clients who use it. Some servers will utilize a short string of hexadecimal characters as tokens, while others will employ structured tokens like JSON Web Tokens.

+ secret: is a password that only the application and the authorization server have access to. 

+ JSON Web Token: JSON Web Token (JWT) is a URL-safe way of representing claims to be transferred between two parties in a compact format.

## 5 steps to RBAC (role-based access control)

**What is role-based access control RBAC?**

*RBAC refers to the concept of assigning system access to users based on their organizational function. Users are divided into roles based on similar job duties and system access demands, and the system needs of a specific workforce are examined. Each person is then given access based only on their role assignment.*

**What are the advantages of RBAC?**

1. The assignment of access privileges becomes systematic and repeatable with the proper deployment of RBAC. Furthermore, auditing user permissions and correcting any errors discovered is significantly easier.

2. RBAC may appear frightening, but it is actually rather simple to deploy and will make access rights management more easier and more secure.

**The Implementation of RBAC**

1.  Inventory your systems

*If you don't already have a list of resources for which you need to manage access, make one now. An email system, a customer database, a contact management system, and significant directories on a file server are all examples.*

2. Analyze your workforce and create roles

*You should organize your employees into roles with similar access requirements. Don't succumb to the temptation of having too many jobs specified. Maintain as much simplicity and stratification as feasible.
For example, a basic user position would have access to email and the intranet site, which every employee would require. A customer care representative with read/write access to the customer database and a customer database administrator with full control of the customer database are two alternative roles that could be considered.*

3. Assign people to roles

*Determine which role(s) each employee belongs in, and adjust their access accordingly, now that you have a list of roles and their access rights.*

4. Never make one-off changes

*If an employee has special needs, resist the urge to make a one-time adjustment. Your RBAC system will swiftly fall apart if you start doing this. Change the roles as needed, or create new ones as needed.*

5. Audit

*Review your positions, the personnel assigned to them, and the access granted to each on a regular basis. If you find that a role has unneeded access to a system, for example, alter the role and adjust the access level for all employees in that job.*

## wiki - RBAC

*Role-based access control (RBAC) or role-based security is a method of controlling system access to authorized users in computer security. It's a method for implementing either mandatory or discretionary access control (DAC).*

*RBAC (role-based access control) is a policy-independent access-control method based on roles and privileges. RBAC components such as role-permissions, user-roles, and role-role connections make user assignments straightforward. RBAC meets many needs of commercial and government organizations, according to a NIST research. In large organizations with hundreds of users and thousands of permissions, RBAC can be utilized to make security administration easier. Despite the fact that RBAC differs from MAC and DAC access control frameworks, it can easily enforce these policies.*
