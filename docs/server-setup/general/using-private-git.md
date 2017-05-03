# Using private external git repository

Using a private GIT repository is quite simple. Depending on if you are using GitHub or another git provider.

## GitHub

...

## Another git provider (Gitlab, Bitbucket or self hosted)

If you are using another provider than GitHub, this could be Gitlab, Bitbucket or a self hosted git server. You will need to create a user and give this user READ access to your repository.

On the user, add the public key below. This will allow our deployment servers to make a git clone of your projects. And you will maintain control over what projects we are allowed to use.

```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDAzw8ek9ulu8h2kTcdY21wicljfltsT8SRXOCozKsEy8Qq2dZJ7aDP1Zcn8VqCzSj46RRNGAvYNwegWJ77IbQNgrrgVpTNEovzG1XcCugl94oGQ2FMz4xOSWyDriIu2e22R8KweFEu2vlRSo29Wv9Maqxprf2LZR3Z2svgDZ9uMyxfa7LhryYZmHdm6ndN6CUSIq96rtCI8YjbofU7T63O5hAiv/SaYRpydKUgNJuR1adUTECuLhZx7pcJP5nm4a8k5ge+yhVJISm/Tblp5pNk9yiOXzCjPE1fnkZsRdxCu8U0GP+KAbLJ/CHa5Atw7fk/3OsdgaBhwtB5rgLJWxPj
```

The private key is kept safe inside our private network, and is under the same security as all other data in Vapor Cloud.
