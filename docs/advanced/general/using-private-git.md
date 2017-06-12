# Using private external git repository

Using a private GIT repository is quite simple. Depending on if you are using GitHub or another git provider.

## GitHub

There are 2 ways you can grant access to a private repository on Github

### Invite our Cloud API user

You can invite our API User to your repository/organisation, details below:

Username: vapor-cloud-api

E-mail: github@vapor.codes

Link to profile: https://github.com/vapor-cloud-api

### Use SSH Key

You can use the same SSH Key as in 'Another git provider'. This can be setup on either your own user or a user you create yourself.

## Another git provider (Gitlab, Bitbucket or self hosted)

If you are using another provider than GitHub, this could be Gitlab, Bitbucket or a self hosted git server. You will need to create a user and give this user READ access to your repository.

On the user, add the public key below. This will allow our deployment servers to make a git clone of your projects. And you will maintain control over what projects we are allowed to use.

```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQCmDZvHHooUhlHuldTW5YVBy8QrUreyJJi6tT3H7st05Pl2VO8Xnj/2FGYct6nYo+N7jAN3AfFzWbVktcO9H/J2GdbOSWbCLKrDezftKsTmmznWT/hX7vVgVY1Rg4ExJYpXg+oHJK91ecwrR0a+i0i/Z/mfdkmrkSoZvz8zpapwgAO9YUSfUJBji31WeczXq/XxoaAy8x3ivVCEvUWyfLmt7G+WKp4uMCRQJhbNyo4L9ogoj4uhq8s1nr3ST2dVdh8waOEptjqI3aa2xTN2tamcKp7H2XEd3jZY5GwmmjXJ1T0uAAeOwOsm/wMw3MqvSJrXmz3IKHz8Wt9CTDeovxWzXZVDDLgcxHAnZx9wcZWogBFYWfYyqY5tpWxc2OiY50AFYf9nvOGzW4cP2yavKbXp9pAWlb28AtiL96A2ZSg4rQJbB1YQC0eobhjVZWUCCS+pg1KhVOLFSgK2QQ1OAnOAWYLPRrlbEUsJfNpb7iNRecxSvqCk1covZBr1c4F5Hu9SDvV5NDaiiFFX3oYXl+RpGQR2SoQoj2YxV/C9x6MgRn95RnioxZa58L+r98TJD08SdLMJgJ6LMSq6Lb4BQv0JD1aFlnTVYZLQOcXadIAtc027OuGeUPbFROld8Kl2HMPI3aYykNKjAM8KPba4pBSDX3ahr3JKlrq4pLGZvIL9ew==
```

The private key is kept safe inside our private network, and is under the same security as all other data in Vapor Cloud.
