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

You need to attach your domain to your application (This isn't supported yet..)

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

`vapor cloud letsencrypt --app=my-example --env=production --domain="example.com,www.example.com"`

`vapor cloud letsencrypt --app=my-example --env=staging --domain="staging.example.com"`
