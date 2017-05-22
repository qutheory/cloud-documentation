# TLS With Let's Encrypt

Let's Encrypt is a modern approach to SSL/TLS. They provide completely free certificates.

Let's Encrypt is an easy way to get https on your domain, with absolutely no maintenance. Our platform makes sure always to update your certificates.

!!! info
    You need to get your application up and running on Vapor Cloud, before you can use Let's Encrypt, you need to have it running on Vapor Cloud.
    The reason for this, is we use this to verify ownership of the domain.

!!! info
    Let's Encrypt dosn't support wildcard certificates, so you will need to create a certificate for each domain e.g.:

    test1.example.com

    test2.example.com

## Step 1 - Attach domain to application

```
vapor cloud create domain
```

!!! info
    At the moment, after adding the domain, you need to redeploy your application, for our systems to recongnize it.

## Step 2 - Add DNS record

You need to point your domain to your Vapor Cloud application. To do this, go to the DNS management for your domain.

Create a `CNAME` record. Your domain need to point to <your-app>.vapor.cloud

Example:

I want `example.com`, `www.example.com` to point to my application `my-example` on production

And `staging.example.com` to point to my application `my-example` on staging

example.com CNAME my-example.vapor.cloud

www.example.com CNAME my-example.vapor.cloud

staging.example.com CNAME my-example-staging.vapor.cloud

## Step 3 - Setup certificate

We will now setup certificates for the domains we setup in previous step. Go to your terminal, and run the following commands:

```
vapor cloud create tls
```

!!! info
    Use `vapor cloud create tls --force` if you wan't it to force https with a 301 redirect
