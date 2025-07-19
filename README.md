# 🚀 AWS S3 Static Website Hosting

This project demonstrates how to host a static website using Amazon S3, leveraging the AWS Free Tier. It includes creating an S3 bucket, enabling static hosting, and making the content publicly accessible.

📦 What I Used

- AWS S3 (Free Tier)

- HTML (basic index page)

- Bucket Policy (for public access)

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

- Navigate to S3

3. Create a New S3 Bucket
Click "Create bucket"

- Name: your-unique-bucket-name

- Uncheck Block all public access

- Acknowledge the warning

- Click Create bucket

4. Upload the HTML File
- Open your new bucket

- Click Upload

- Add "your-file-name".html
* S3 is case-sensitive. The file name has to be lower case with ".html" at the end.

5. Enable Static Website Hosting
- Go to the Properties tab

- Scroll to Static website hosting

- Click Edit

- Choose Enable

- Set Index document: "your-file-name".html

- Save changes

6. Make Content Public via Bucket Policy
- Go to Permissions > Bucket policy

- Paste the following (replace your-unique-bucket-name):

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
- Save policy

7. Access the Website
- Go back to Properties > Static Website Hosting

- Copy the Endpoint URL

- Visit the URL in your browser (e.g., http://your-bucket-name.s3-website-us-east-1.amazonaws.com)

🔧 Optional Fix: Display the Page Properly
To make the page render as a full HTML webpage (not raw code), just remove the comment line at the top of your index.html.

Here’s a clean version to use:

html
Copy
Edit
<!DOCTYPE html>
<html>
<head>
  <title>Hello from S3</title>
</head>
<body>
  <h1>My First AWS S3 Website!</h1>
</body>
</html>
Save that as a new index.html on your computer.

Go back to your S3 bucket → Upload → choose the new file.

Overwrite the existing one (or delete the old one first).

Refresh your browser — you should see a clean, centered heading.
