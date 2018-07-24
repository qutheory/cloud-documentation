# Delete Application

To delete your application, you first need to scale your replicas down to 0.
To do this, run the following command

```
vapor cloud deploy --replicas=0
```

After this, you can delete the application through the dashboard

1. Go to https://dashboard.vapor.cloud
2. Click the organization
3. Click the project
4. Click the application
5. Click Edit in the top right corner
6. Click delete in the top right corner.
