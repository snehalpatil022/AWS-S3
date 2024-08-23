# AWS-S3
**Create a bucket in Amazon S3**

In the AWS Management Console, search for S3

![S3 bucket image](https://github.com/user-attachments/assets/2756562f-c2e8-4341-afeb-9cd966cdd645)


Choose Create bucket

AWS Region : select the Region closest to you.
For Bucket name, enter net-website-project-name. Make sure to replace name with your name.

** An S3 bucket name is globally unique, and all AWS accounts share the namespace. After you create a bucket, no other AWS account in the entire world can use your bucket's name unless you delete the bucket.**

For Object Ownership, choose ACL enabled.

![step1 2](https://github.com/user-attachments/assets/e5cf074c-efcc-4a56-9105-030abee990e1)

**💡 Ooo what are ACLs (Access Control Lists)?
An ACL = a set of rules that decides who can get access to a resource. Enabling ACLs in this S3 setup lets you control who can access and do things with the objects (i.e. website files) you upload into your bucket. With ACLs, different AWS accounts can own and control different files in your bucket. The warning that pops up suggests that it's simpler to use something called "bucket policies". While they let you control access for the entire bucket (e.g. making the entire bucket and its objects public), bucket policies don't give you fine grained control over individual objects in your bucket.
Bottom line, if you know that the entire bucket contains no sensitive information, you can use a bucket policy. But if there's even one object in the bucket that you want to keep private, use ACLs.
In this exercise, we're enabling ACLs to show you how they work**

Choose Bucket owner perferred.
For Block Public Access settings for this bucket, clear the check box for Block all public access.

**💡 A yellow banner has popped up! This banner is telling us that the bucket and its objects might become public if we untick the checkbox. This is what we want to host a public website!**

Check the box that says “I acknowledge that the current settings might result in this bucket and the objects within becoming public.” 

![step1 3](https://github.com/user-attachments/assets/a0d74c14-c509-4336-b9a3-70c169a64d73)

For Bucket Versioning, choose Enable.

**NOTE: Once you turn on (enable) bucket versioning, you can't turn it off. We'll show you why we've enabled this as a last step in this exercise**

Choose Create bucket.

![step1 4](https://github.com/user-attachments/assets/ec665334-28f1-4580-b7d7-3c0b8a34ef79)

*** Upload website content to your bucket*** 

Time to get your website's files in your bucket!

In the Buckets section, choose the name of your new bucket.
Upload these files into your bucket (right click on each link, and select):
                       *index.html
                       *Create a zip file

**💡 What is HTML?
HTML (HyperText Markup Language) is used to create and design web pages. It's your way of telling the website where you want to display your text, images, videos and more. Think of HTML as the blueprint that shapes what you see when you visit a website.**                  

Unzip the zip file you've downloaded.
Return to the Amazon S3 console with your bucket page open. Choose the Objects tab.

Choose Upload
.
Choose Add files
.
Choose index.html
.
Choose Add folder
.
Choose the unzipped folder - NOT the zip file itself!
You might get a popup that tells you that all files in that folder will be uploaded.

Choose Upload.

S3 will get to work right away!

![step2 1](https://github.com/user-attachments/assets/0e8a2a0b-0e2b-4df0-bbfd-35dec6f7a57d)


Your files should upload in a few minutes! Choose Close when you see the green Upload succeeded banner.      

![step2 2](https://github.com/user-attachments/assets/a1b2b802-ab1d-4c75-9e75-95b99d213546)



            



