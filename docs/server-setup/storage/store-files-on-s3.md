# Store files on S3

Our replicas does not support persistent storage of files. So if you save a file in side the replica, it will eventually be purged.
files are furthermore not shared between replicas.

But in some cases, persistent storage are needed. For this, you can save the files on S3. All applications have access to save files in a folder
on our system.

Each applications files can only be modified/deleted/added by that particular application.

To store files on S3, you need the following details: `Bucket`, `Access key`, `region` and `Secret key`.

These can be accessed as environment variables in a JSON file like this:

```
{
  "bucket": "$AWS_S3_BUCKET",
  "accessKey": "$AWS_ACCESS_KEY",
  "secretKey": "$AWS_SECRET_KEY",
  "region": "eu-west-1",
}
```

For now region is always `eu-west-1`

When you upload the files, you should always start with adding your application slug e.g.:

`my-cool-app/my-folder/my-file.txt`

If you don't prefix with your application slug, it will get a permission denied.
