# Akrista's Selfhost Vault

This is my personal collection of files for self-hosting various services, while i try to follow [best practices](#practices-followed), be aware that this does not represent a flawless guide to deploy production ready services.

If you want to collaborate, feel free to make a [pull request](https://github.com/akrista/selfhost/pulls).

## Practices Followed

A compose.yml must:

- Use container names that are descriptive and unique
- Use environment variables when needed for dynamic configuration
- Use health checks when possible
- Use the timezone preferred for the container when possible
- Use watchtower for automatic updates when possible
- Unused ports must be commented out
- When possible, separate containers in different networks (proxy, database, services, etc.)
