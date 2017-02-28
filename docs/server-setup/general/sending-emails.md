# Sending E-mails (SMTP)

Vapor Cloud don't have an SMTP server for sending E-mails. But it's very
easy to setup an external provider.

## External mail providers

Here is an example list of providers that can be used, but is not
limited to this list.

- Mailgun (10.000 free E-mails/month)
- SendGrid (From $9.95/month)
- Amazon SES ($0.10 per 1000 emails)

## Use E-mail provider through Vapor

To setup an external mail provider, setup the following in your
.vcloud.yml file:

```
config:
    all:
        smtp_host: "my.smtp.host",
        smtp_port: "465",
        smtp_user: "my@smtp.user",
        smtp_password: "kjn4kj32n4jkn423",
        smtp_fromEmail: "my@domain.com",
        smtp_fromName: "My awesome APP"
```

This will automatically generate the following file in
`Config/secrets/mail.json`

```JSON
{
    "smtpHost": "my.smtp.host",
    "smtpPort": "465",
    "user": "my@smtp.user",
    "password": "kjn4kj32n4jkn423",
    "fromEmail": "my@domain.com",
    "fromName": "My awesome APP"
}
```
