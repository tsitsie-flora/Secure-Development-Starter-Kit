### Authentication

Authentication is the process of verifying that an individual, entity or website is who or what it claims to be by determining the validity of one or more authenticators (like passwords, fingerprints or security tokens) that are used to back up this claim.
[Link to cheatsheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)

Authentication verifies who a user is.
Authorization determines what that user is allowed to do.

Simple example:

```
User → Login → Authentication → "This is Alice"
                         ↓
                  Authorization
                         ↓
             "Alice can view invoices"
```

#### Password Storage

When storing passwords, do not do this:

```password → database```

or this:

```MD5(password) → database```

Instead, do this:

```
password
   ↓
Argon2id / bcrypt / scrypt
   ↓
password hash → database
```
