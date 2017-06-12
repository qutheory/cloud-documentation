# Sending E-mails (SMTP)

Vapor Cloud don't have an SMTP server for sending E-mails. But it's very
easy to setup an external provider.

## External mail providers

Here is an example list of providers that can be used, but is not
limited to this list.

- Mailgun (10.000 free E-mails/month)
- SendGrid (From $9.95/month)
- Amazon SES ($0.10 per 1000 emails)

Simply create an account, and setup the details from the provider in
your Vapor project

## Use E-mail provider through Vapor

Create the following file:

`Config/mail.json`

And add the content below.

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

It's also possible to use the custom configuration, see more under
`Vapor` documentation
