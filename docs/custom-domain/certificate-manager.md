# Vapor Cloud Certificate Manager (VCM)

To secure your app when using your own domain, you can use the Vapor Cloud Certificate Manager to get a **FREE** SSL/TLS certificate to your app.

This type of certificate is managed by Vapor Cloud, so you never think about renewing it, or do anything, we handle everything for you.

The VCM uses Let's Encrypt to supply free certificates. This service uses SNI (Server name indication), an extension of TLS. You can read more about SNI, and support for it [here](https://en.wikipedia.org/wiki/Server_Name_Indication)

!!! info
    You need to get your application up and running on Vapor Cloud, before you can use the VCM, you need to have it running on Vapor Cloud.
    The reason for this, is we use this to verify ownership of the domain.

!!! info
    VCM unfortunately don't support wildcard certificates, so you will need to create a certificate for each domain e.g.:

    test1.example.com

    test2.example.com

## Step 1 - Attach domain to application

```
vapor cloud create domain
```

Read more about custom domains [here](./add-domain.md)

!!! info
    At the moment, after adding the domain, you need to redeploy your application, for our systems to recognize it.

## Step 2 - Add DNS record

You need to point your domain to your Vapor Cloud application. To do this, go to the DNS management for your domain.

Create a `CNAME` record. Your domain need to point to <your-app>.vapor.cloud

Example:

I want `www.example.com` to point to my application `my-example` on production

And `staging.example.com` to point to my application `my-example` on staging

www.example.com CNAME my-example.vapor.cloud

staging.example.com CNAME my-example-staging.vapor.cloud

## Step 3 - Setup certificate

We will now setup certificates for the domains we setup in previous step. Go to your terminal, and run the following commands:

```
vapor cloud create tls
```

!!! info
    Use `vapor cloud create tls --force` if you wan't it to force https with a 301 redirect
