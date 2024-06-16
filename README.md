# Website-on-Amazon-S3
Hosted a website on S3 bucket with help of Route 53.

Overview

This project demonstrates how to host a static website on Amazon S3, leveraging the scalability, security, and reliability of AWS. The project includes steps for configuring an S3 bucket for static hosting, uploading website files, and configuring necessary permissions and settings.

![image](https://github.com/Pranoom18/Website-on-Amazon-S3/assets/94820532/09ad34b0-7047-4576-b32c-c28ab3ac4353)


Table of Contents

Features
Prerequisites
Setup Instructions
Create S3 Bucket
Configure Bucket for Static Hosting
Upload Website Files
Set Permissions
Usage
Project Structure
Contributing
License
Contact

Features

Static Website Hosting: Host a static website using Amazon S3.
Scalable and Reliable: Leverage AWS infrastructure for high availability.
Secure Access: Configure bucket policies for secure access.
Custom Domain Support: Use custom domains with AWS Route 53.

Prerequisites

An AWS account.
AWS CLI installed and configured on your machine.
Basic knowledge of S3 and static websites.

Setup Instructions

Create S3 Bucket
Log in to AWS Management Console.
Navigate to S3 service.
Create a new bucket:
Choose a globally unique name for your bucket.
Select your preferred region.

![image](https://github.com/Pranoom18/Website-on-Amazon-S3/assets/94820532/adc4fc07-e14b-4ec1-bec2-e2fff2d8d3b6)


Configure bucket settings:

Uncheck "Block all public access" to allow public access (we will set specific permissions later).
Configure Bucket for Static Hosting
Go to the Properties tab of your bucket.
Enable Static Website Hosting:
Click on "Edit" in the "Static website hosting" section.
Select "Use this bucket to host a website".
Enter the index document (e.g., index.html).
Enter the error document (e.g., error.html).

Upload Website Files

Navigate to the Objects tab of your bucket.
Upload files:
Click on "Upload".
Add the files of your website (e.g., index.html, style.css, etc.).
Click "Upload" to transfer files to the S3 bucket.

Set Permissions

Go to the Permissions tab of your bucket.
Bucket Policy:
Click on "Edit" in the "Bucket policy" section.
Add the following policy to allow public read access:
json

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::your-bucket-name/*"
        }
    ]
}
Replace your-bucket-name with the name of your S3 bucket.

Usage

Access Your Website:

Open the S3 bucket URL in your browser. The URL will be in the format: http://your-bucket-name.s3-website-region.amazonaws.com
Example: http://mywebsite.s3-website-us-east-1.amazonaws.com
Custom Domain (Optional):

Use AWS Route 53 to configure a custom domain name.
Create an alias record pointing to your S3 bucket website endpoint.

Project Structure

index.html: Main HTML file for the website.
style.css: CSS file for styling the website.
scripts.js: JavaScript file for website functionality.
images/: Directory for image assets.
README.md: Project documentation file.

![image](https://github.com/Pranoom18/Website-on-Amazon-S3/assets/94820532/6f28dc17-de07-40a2-b680-3b4520dc6714)

Contributing

We welcome contributions to enhance the project. To contribute, please follow these steps:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Make your changes and commit them (git commit -am 'Add new feature').
Push to the branch (git push origin feature-branch).
Create a new Pull Request.

License

This project is licensed under the MIT License. See the LICENSE file for more details
