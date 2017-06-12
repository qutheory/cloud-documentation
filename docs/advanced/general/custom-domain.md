# Custom domain

All applications on Vapor Cloud is automatically added with a `app-name.vapor.cloud` domain.
But often it can help to be able to have your own domain name to your application e.g. `example.com`.

To accomplish this, there are a couple of small steps you need to go through.

## 1 Create domain in Vapor Cloud

To tell our loadbalancers where to direct the traffic, you can create the domain through the toolbox e.g.:

```
vapor cloud create domain
```

After this, deploy the application, and the domain is created.

## 2 Create DNS

DNS can be a bit different depending on if it's a subdomain or root domain.

**Subdomain** a subdomain is e.g. `www.example.com`

**root domain** a root domain is e.g. `example.com`

### 2.1 Setup subdomain

Make a CNAME record with your DNS provider. Let's say you have `www.example.com` and want to point it to the app on Vapor Cloud called `my-app`

You should create a CNAME record pointing:
`www.example.com` to `my-app.vapor.cloud`

!!! info
    Some DNS providers require a `.` after the ending domain e.g. `my-app.vapor.cloud.` check this with your DNS provider.

### 2.2 Root domain

Because Root domains need to point as an `A` record, and this need to be a IP address, the process is a bit different. Since we don't have fixed ip adresses.

Some DNS providers support `ALIAS` record, if your provider don't support this, and you can't move the domain, you would need to setup a redirect to e.g. `www.example.com`.

If you can move your domain, or you need to register a new domain, we suggest using one of the following:

- [dnsimple.com](https://dnsimple.com) (Personal plan including 5 domains for $5/month)

These providers do support `ALIAS` record, and you can simply create an `ALIAS` record e.g.

`example.com` to `my-app.vapor.cloud`

## SSL/TLS for custom domains

Read more about **free** SSL/TLS for custom domains Read more about custom domains [here](./tls-with-letsencrypt.md)
