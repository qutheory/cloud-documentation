
[TOC]

## Can i store images inside my replicas?

You can, but we don't recommend it, since data in the replicas might be wiped. For persistent file storage, please use S3, you can use S3/CDN through Vapor Cloud, look [here](./storage/store-files-on-s3.md)

## I really need feature X, how do i contact you?

If you have an idea for a feature, we would love to hear about it. Please add it [here](https://ideas.vapor.cloud) this would allow other users to see, comment and vote for your idea.

## Do you have a roadmap, so i know what features are planned?

Yes we have. You can find our public roadmap [here](https://trello.com/b/YZEX66FS/vapor-cloud-public-roadmap)

## Is my data secure on Vapor Cloud?

Security is one of our absolute highest priorities. All data is hosted on AWS (Amazon Web Services), besides that, everything we have build on top, have been build with a security first principle. You can read more about security [here](./advanced/security/responsibilities.md)

## On the free plan, can i still see requests and memory usage

Yes, all our replicas support resource and request monitoring. We think it's important for people to be able to monitor and optimize their apps, even when using our free plans.
