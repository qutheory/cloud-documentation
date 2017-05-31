# Vapor Cloud security

At Vapor Cloud we strive to provide the best possible security, without making it more difficult for our users to use the system.

## Access control

Everyone in our Operations team is highly trained, and have many years experience in building secure systems. Everyone with server access have strict encryption on their computers, and can be wiped remotely if the hardware should be stolen.

All access to our systems go through a Bastion host (jump-host) server, through the persons personal account with individual 4096-bit encrypted SSH key. Access also requires a password to keep a 2-factor setup.

All access are logged both locally and remotely, and undergoes regular audits

## Network layer

Our network is secured after best practices. We only have very few servers with Internet access, the rest is in a private network with no internet access.

Besides this, all our servers have strong firewall, with a minimal allowed ports on each server. This helps secure no external access to systems with sensitive data (Database, Cache, Web servers etc.)

## Audits

All our systems is logging both internally and externally, and everything is audited regularly, to catch potential inconsistencies, these are investigated by our highly trained team.

## Backup

We perform regular backups of all our systems, both internally and externally, we perform backups of the entire servers, and custom backup e.g. Each applications databases individually. These backups can be provided upon request.
