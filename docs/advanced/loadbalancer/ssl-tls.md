# SSL/TLS

## SSL/TLS Settings

Our setup is built with security in mind, all our vapor.cloud domains automatically have https enabled. With the option of forcing all users on https.

We also provide the feature of adding free certificate for custom domains for all our clients, even on our free plan.
We strongly believe in encrypt everything, so we always recommend our clients to force HTTPS.

## Support

**Enabled versions**

We have enabled the following versions:

- TLSv1
- TLSv1.1
- TLSv1.2

The following is disabled, because they are found insecure:

- SSLv1
- SSLv2
- SSLv3

All our certificates are encrypted with SHA256 and uses a Diffie Hellman key length of 4096 bits.

## SSL Termination

To keep load on the replicas low, our load balancers will terminate the SSL connection. So when your app receives the request, it will be read as HTTP.

If you need to know if the request was served on HTTPS, you can always read the `X-Forwarded-Proto` header. This will be set with either `http` or `https`

Vapor example:

```
if drop.request.headers["X-Forwarded-Proto"] == "https" {
	print("Secure connection")
} else {
	print("Insecure connection")
}
```

All requests from the loadbalancers are served on our internal network, and can't be accessed from the outside, so the security is the same even when we terminate the SSL connection.