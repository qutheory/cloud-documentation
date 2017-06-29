# Accessing files through CDN

Vapor Cloud provides users with a easy to use CDN to access files stored on S3.

There are multiple ways to expose the files depending on the type.

## Images

Our CDN support multiple image types. When uploading a file as an Image, it gives the option to to real-time resizing of files.

To make sure this is stable, you need to upload your files to a folder called `images` on S3.

So e.g.:

`my-app/images/my-folder/my-sub-folder/my-image.png`

I will then be able to access the file in the browser:

`https://cdn.vapor.cloud/my-app/images/my-folder/my-sub-folder/my-image.png`

To resize or crop the image, i can do:

```
# Resize to 50px width
https://cdn.vapor.cloud/my-app/images/my-folder/my-sub-folder/my-image.png?w=50

# Resize to 50px height
https://cdn.vapor.cloud/my-app/images/my-folder/my-sub-folder/my-image.png?h=50

# Crop to 50x50px
https://cdn.vapor.cloud/my-app/images/my-folder/my-sub-folder/my-image.png?w=50&h=50&type=crop
```

## Other files & Large files

To access other file types (PDF, docx etc.) you can use `cdn-raw.vapor.cloud` raw means it will access S3 directly, and by then not have problems with larger files.
