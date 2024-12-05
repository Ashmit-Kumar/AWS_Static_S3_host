
#### **`docs/troubleshooting.md`**

Include common issues and troubleshooting tips.

```markdown
# Troubleshooting

Here are some common problems you might encounter and how to fix them.

## Problem: "403 Forbidden" Error

### Cause:
This typically happens if the S3 bucket is not configured with the correct permissions.

### Solution:
Ensure your bucket policy includes permission for public access. Check the bucket's permissions and verify that the public read policy is set correctly.

## Problem: "Website Not Found" Error

### Cause:
This can happen if the bucket is not properly configured for static website hosting.

### Solution:
Double-check that you've enabled static website hosting in the **Properties** tab and that the correct index and error documents are set.

## Problem: Files Not Displaying Correctly (Missing CSS, JS)

### Cause:
Your website files may not have been uploaded correctly, or you might not have set the correct MIME types.

### Solution:
Check that all necessary files (CSS, JS) are uploaded and that the correct content type (MIME type) is assigned to each file in S3. For example, ensure `.css` files are set to `text/css`.
