# Setup Guide for Static Website Hosting on S3

Follow these steps to host your website using an AWS S3 bucket.

## Step 1: Create an S3 Bucket

1. Log in to your [AWS Management Console](https://aws.amazon.com/console/).
2. Navigate to **S3** under Services.
3. Click **Create Bucket**.
4. Choose a unique name for your bucket (e.g., `my-static-website`).
5. Select a region for your bucket.
6. Uncheck "Block all public access" under Permissions.
7. Click **Create**.

## Step 2: Upload Your Website Files

1. Navigate to your newly created bucket.
2. Click **Upload** and select the `index.html` and `style.css` files from the `website/` folder.
3. Upload these files to the bucket.

## Step 3: Enable Static Website Hosting

1. Go to the **Properties** tab of the bucket.
2. Scroll to the **Static website hosting** section and click **Edit**.
3. Select **Enable**.
4. Set the **Index document** to `index.html` (or your main HTML file).
5. Set the **Error document** (optional) to `error.html` if you have one.
6. Save changes.

## Step 4: Update Bucket Policy for Public Access

To allow the public to access your website:

1. Go to the **Permissions** tab in your bucket.
2. Click **Bucket Policy**.
3. Add the following policy (replace `your-bucket-name` with the actual name of your S3 bucket):

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
