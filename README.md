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

**💡 What does website hosting mean?
Website hosting is what makes your website public on the internet.
Even if you perfect an HTML file, no one else can see it when it's stored as a local file on your computer! Website hosting = storing your HTML file (and the other files for your website) on a web server, so it's accessible online.
By configuring your S3 bucket for hosting, we're telling this bucket: "please create a URL that will take anyone to a page that displays the HTML file I just uploaded** 


Make sure you're back in your bucket's page. If you're not sure, choose buckets on the left hand side navigation bar, and then choose the bucket you created for this project.
Choose the Properties tab.
Scroll allllllllll the way down to the Static website hosting panel.
Choose Edit.
Configure the following settings:
Static web hosting: Choose Enable.
Hosting type: Choose Host a static website.
Index document: Enter index.html

![step3 1](https://github.com/user-attachments/assets/0e164921-130e-4ab0-a7c3-4c51d7665c15)

Choose Save changes.
In the Static website hosting panel under bucket website endpoint, click on the URL.
An error! 👀

![high-step3 1](https://github.com/user-attachments/assets/cdbf7a58-c651-4c5d-85bd-f08a8e0e3b59)

**💡 Why did I get this error?
Objects (in this case, the HTML and images files you uploaded) are private by default. This default setting helps keep your account's data secure.
The error message you're seeing is telling you that your static website is being hosted by S3, but the actual HTML/image files you've uploaded are still private. It's kind of like having a bucket on display, so everyone can see the bucket - but the contents are covered up, preventing anyone from seeing what's inside.
To solve this error, we need to set the permission of the objects to public - this is why we enabled ACLs in Task 1**

Use ACLs to make objects in your S3 bucket public

Let's make the uploaded objects publicly accessible so users can view your website.

Keep the error message tab open and switch back to the Amazon S3 console tab.
Would you still remember how to view your S3 bucket's objects? Try finding your bucket's Objects page and making your objects public using ACLs.

.... feeling a little stuck?

No worries! If you're stuck, head to the Objects tab.
Select the checkboxes next to your index.html file and the folder of website assets.
In the Actions dropdown, choose Make public using ACL.

![high-step4 1](https://github.com/user-attachments/assets/b038c735-e6ee-414a-91ec-6549c9295831)

Choose Make public.
Once the green banner pops up, choose Close.

![high-step4 2](https://github.com/user-attachments/assets/f19e4b97-ab5a-4f41-9986-747d0209e4aa)

Return to the web browser tab that has the 403 Forbidden message.
Refresh the tab.

![high-step4 3](https://github.com/user-attachments/assets/dd9983c9-2f6f-4f76-a670-291aa8f3a9cb)



            

**Delete your resources**

Make sure you delete all your resources to avoid getting charged. This is a super important task for every single project you set up.

We challenge you to try to give this a go yourself 💪 Do you think you can delete the resources you've created today? Don't forget to take screenshots of your work before they're gone!

If you're feeling stuck (we've all been there!), here's a little guide:

To delete an S3 object, head back to your browser tab with the AWS Management Console.
Select the Objects tab.
Select the checkboxes next to the three objects in your bucket, and choose Delete.
Type delete to confirm.
Select Delete objects.

![high-delete1](https://github.com/user-attachments/assets/8de3f253-e0a3-4ad9-8254-02222aaf9ecf)

Did you run into an error with deleting index.html?

Head back to the Permissions tab and select Delete in the Bucket policy panel.
Delete index.html again!
Now, head back to the Buckets page (it's on the left-hand navigation panel).
Select your bucket, and choose Delete.
Type your bucket's name to confirm the deletion, and then click Delete bucket.

![high-delete2](https://github.com/user-attachments/assets/f86a6f23-d1b6-410f-a2d4-3babb75c87bf)



