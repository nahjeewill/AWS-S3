🚀 AWS S3 Static Website Hosting
This project demonstrates how to host a static website using Amazon S3, leveraging the AWS Free Tier. It includes creating an S3 bucket, enabling static hosting, and making the content publicly accessible.

📦 What I Used
AWS S3 (Free Tier)

HTML (basic index page)

Bucket Policy (for public access)

AWS Console

🛠️ Step-by-Step Setup
1. Create a Simple HTML File
html
Copy
Edit
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
  <title>Hello from S3</title>
</head>
<body>
  <h1>My First AWS S3 Website!</h1>
</body>
</html>
2. Log into AWS Console
Visit: https://console.aws.amazon.com/

Navigate to S3

3. Create a New S3 Bucket
Click "Create bucket"

Name: your-unique-bucket-name

Uncheck Block all public access

Acknowledge the warning

Click Create bucket

4. Upload the HTML File
Open your new bucket

Click Upload

Add index.html

5. Enable Static Website Hosting
Go to the Properties tab

Scroll to Static website hosting

Click Edit

Choose Enable

Set:

Index document: index.html

Save changes

6. Make Content Public via Bucket Policy
Go to Permissions > Bucket policy

Paste the following (replace your-unique-bucket-name):

json
Copy
Edit
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-unique-bucket-name/*"
    }
  ]
}
Save policy

7. Access the Website
Go back to Properties > Static Website Hosting

Copy the Endpoint URL

Visit the URL in your browser (e.g., http://your-bucket-name.s3-website-us-east-1.amazonaws.com)
