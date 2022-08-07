# Storing, Retrieving & Implementing Objects using AWS S3

This is intended to be a visual guide for one use case I implemented using Amazon S3. Essentially what this service offers is a simple cloud object storage that can read, retrieve, store and display data from anywhere, as well as import it into projects with a live 'Object URL'.

![Object URL data](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Access+live+object+URL+for+uploaded+file.png)
_Seattle Public Library image - stored data in bucket_

### You can think of S3 as a virtual cloud drive where you can create folders (buckets) to store data files (objects) and specify what kind of objects they are by adding tags (metadata).

For this use case, I built a simple e-commerce store and used Amazon S3 to create buckets and store objects in them. The data I uploaded into the bucket is referred to as an object and its metadata is a way to specify what kind of object it is. For my specific use case, I had to enable public access (**which is by default blocked to the public**), since the objects I stored are meant to be visible on the e-commerce application as product data. I also had to create a policy within my bucket using JSON syntax to grant resource-based public permissions to the bucket data.

**Here we go: Storing, Retrieving & Implementing Objects using AWS S3**

Assuming you have an AWS account, you will need to sign in as an IAM user. 

_If you do not yet have an account,click the link below to create one._

## [Create an AWS account here](https://aws.amazon.com/)

Once you have successfully created an account, the first location will be the AWS Managment Console where you'll see the range of services offered. 

![AWS Console](https://s3-visual-guide.s3.us-west-1.amazonaws.com/AWS-console.png)

## Navigate to S3 under AWS Services 

![](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Storage+S3+service.png)
_Click on the Services icon in the top left corner or search S3 via the search bar_

## Create Bucket
![Create Bucket](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Create+Bucket.png) 
- name the bucket

![Select Region](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Create+Name%2C+Select+Region.png)
- select region
- click 'Create Bucket'

![Click 'Create Bucket'](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Click+'Create+Bucket'.png)

Click 'Upload' to upload objects into the bucket

![Upload files to bucket](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Upload+files+to+bucket.png)
- click upload to add files to folder
  
**Remember:** folder = bucket | files = objects

![Add/upload Files](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Add+Files.png)
- local machine files will pop up
- select a file to upload to the bucket
-  click on bucket name under 'Destination'
- once the file is populated to said bucket, click 'Upload'

![Click 'Upload'](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Once+uploaded%2C+click+'Upload'.png)

## Set Permissions
- you should be at the base of the bucket in 'Objects' with the added file(s)
- navigate to and click on 'Permissions'
  
 ![Set Permissions](https://s3-visual-guide.s3.us-west-1.amazonaws.com/click+'permissions'+to+unblock+access.png) 

- Click 'Edit' under 'Block Public Access'

- Uncheck 'Block _all_ public access' (AWS blocks public access by default)

![Uncheck to unblock](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Uncheck+'Block+all+public+access'.png)

- then hit 'Save changes'
- a confirm action text box will pop up, type in 'confirm' to unblock

![Type in confirm](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Confirm+the+unblock.png)

- hit 'Confirm'
- you have successfully enabled public access 
_(remember, AWS by default blocks all public access to stored data, unless you edit the bucket policy to do so otherwise)_

_*You can decide if your specific use case does/doesn't need public access to the buckets._

## Edit Bucket Policy

- within 'Permissions' scroll down to 'Bucket Policy' and click "edit

![Edit bucket policy](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Edit+'Bucket+Policy'.png)

- using JSON syntax, copy and paste the following
- match the bucket name in "Resource" to your specific bucket name

![Input value for key "Resouce" to your bucket name](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Match+this+JSON+with+your+bucket+name.png)
_Keep in mind that my specific use case requires public access, so '*' makes it accessible to everyone. Again, you can decide if this is your case or not._

- make certain that you add '"Principle": "*"' in the object
- then hit 'Save Changes'

![Successfully edited policy](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Successfuly+edited+policy.png)
_Notification that you have successfully permitted Public Access_

## Locate and implement Object URL(s)
- navigate back to 'Objects'

![Navigate back to Objects](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Navigate+back+to+'Objects'%2C+click+on+file.png)

- Click on the object 'Name'
- within 'Properties', locate 'Object URL'

![Locate 'Object URL'](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Locate+'Object+URL'.png)

- Click on the link and it will serve up the live URL that displays the object uploaded to the bucket

![Object URL data](https://s3-visual-guide.s3.us-west-1.amazonaws.com/Access+live+object+URL+for+uploaded+file.png)
_Seattle Public Library - This is an object I stored in a bucket to demonstrate._

- copy & paste the URL for development purposes

## ET VOILA!

[Visual guide featured on AWS in Plain English] (https://medium.com/aws-in-plain-english/storing-retrieving-implementing-objects-using-aws-s3-e2b206e98623) 

