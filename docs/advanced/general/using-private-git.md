# Using private external git repository

Using a private GIT repository is quite simple. Depending on if you are using GitHub or another git provider.

There are 2 ways you can grant access to a private repository on Github

## Invite ouri GitHub Cloud API user

!!! info
    This is only temporary. And only works for GitHub

You can invite our API User to your repository/organisation, details below:

Username: vapor-cloud-api

E-mail: github@vapor.codes

Link to profile: https://github.com/vapor-cloud-api

## Add your SSH Key to Vapor Cloud

!!! info
    This will not be online before September 17 23:45 UTC. You can already now send your key in, and it will be onlien when we roll the system out.

!!! info
    SSH Keys will be linked to the organization, so they are automatically available to all users and projects under your organization.

### Add your SSH Key.

As this system is still in beta, you need to send your key to our support system, and they will manually add it to the system. Be aware there can be a slight delay in adding the key. You will get a reply once it's added.

We will later create an automatic system to manage the keys.

Send an Email to `support@vapor.cloud`

**Subject:** Add SSH Key: **[Organization name]**

Attach the SSH key as a file to the Email.

If you don't have an SSH Key, you can see how to create a new one [here](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

The file is usually located at `~/.ssh/id_rsa`.

!!! info
    It's important that the key you send us, is the one you have setup at GitHub, BitBucket, GitLab etc.

### Modify/remove SSH Key

Send us an Email to `support@vapor.cloud`

**Subject:** Modify/remove SSH Key: **[Organization name]**
