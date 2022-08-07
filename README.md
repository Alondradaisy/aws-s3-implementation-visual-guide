# Storing, Retrieving & Implementing Objects using AWS S3


This is intended to be a visual guide for one use case I implemented for a project using Amazon S3. Essentially what this service offers is a simple cloud object storage that can read, retrieve, store and display data from anywhere, as well as import it into projects with a live 'Object URL'.

### You can think of S3 as a virtual cloud drive where you can create folders (buckets) to store data files (objects) and specify what kind of objects they are by adding tags (metadata).

For this use case, I built a simple e-commerce store and used Amazon S3 to create buckets and store objects in them. The data I uploaded into the bucket is referred to as an object and its metadata is a way to specify what kind of object it is. For my specific use case, I had to enable public access (**which is by default blocked to the public**), since the objects I stored are meant to be visible on the e-commerce application as product data. I also had to create a policy within my bucket using JSON syntax to grant resource-based public permissions to the bucket data.

**Here we go: Storing, Retrieving & Implementing Objects using AWS S3**

Assuming you have an AWS account, you will need to sign in as an IAM user. 

_If you do not yet have an account,click the link below to create one._

## [Create an AWS account here](https://aws.amazon.com/)

Once you have successfully created an account, the first location will be the AWS Managment Console where you'll see the range of services offered. 

![AWS Console](../../../Desktop/aws%20S3%20process/AWS-console.png)

## Navigate to S3 under AWS Services 

![](../../../Desktop/aws%20S3%20process/Storage%20S3%20service.png)
_Click on the Services icon in the top left corner or search S3 via the search bar_

## Create Bucket
![Create Bucket](../../../Desktop/aws%20S3%20process/Create%20Bucket.png) 
- name the bucket

![Select Region](../../../Desktop/aws%20S3%20process/Create%20Name,%20Select%20Region.png)
- select region
- click 'Create Bucket'

![Click 'Create Bucket'](../../../Desktop/aws%20S3%20process/Click%20'Create%20Bucket'.png)

Click 'Upload' to upload objects into the bucket

![Upload files to bucket](../../../Desktop/aws%20S3%20process/Upload%20files%20to%20bucket.png)
- click upload to add files to folder
  
**Remember:** folder = bucket | files = objects

![Add/upload Files](../../../Desktop/aws%20S3%20process/Add%20Files.png)
- local machine files will pop up
- select a file to upload to the bucket
-  click on bucket name under 'Destination'
- once the file is populated to said bucket, click 'Upload'

![Click 'Upload'](../../../Desktop/aws%20S3%20process/Once%20uploaded,%20click%20'Upload'.png)

## Set Permissions
- you should be at the base of the bucket in 'Objects' with the added file(s)
- navigate to and click on 'Permissions'
  
 ![Set Permissions](../../../Desktop/aws%20S3%20process/click%20'permissions'%20to%20unblock%20access.png) 

- Click 'Edit' under 'Block Public Access'

- Uncheck 'Block _all_ public access' (AWS blocks public access by default)

![Uncheck to unblock](../../../Desktop/aws%20S3%20process/Uncheck%20'Block%20all%20public%20access'.png)

- then hit 'Save changes'
- a confirm action text box will pop up, type in 'confirm' to unblock

![Type in confirm](../../../Desktop/aws%20S3%20process/Confirm%20the%20unblock.png)

- hit 'Confirm'
- you have successfully enabled public access 
_(remember, AWS by default blocks all public access to stored data, unless you edit the bucket policy to do so otherwise)_

_*You can decide if your specific use case does/doesn't need public access to the buckets._

## Edit Bucket Policy

- within 'Permissions' scroll down to 'Bucket Policy' and click "edit

![Edit bucket policy](../../../Desktop/aws%20S3%20process/Edit%20'Bucket%20Policy'.png)

- using JSON syntax, copy and paste the following
- match the bucket name in "Resource" to your specific bucket name

![Input value for key "Resouce" to your bucket name](../../../Desktop/aws%20S3%20process/Match%20this%20JSON%20with%20your%20bucket%20name.png)
_Keep in mind that my specific use case requires public access, so '*' makes it accessible to everyone. Again, you can decide if this is your case or not._

- make certain that you add '"Principle": "*"' in the object
- then hit 'Save Changes'

![Successfully edited policy](../../../Desktop/aws%20S3%20process/Successfuly%20edited%20policy.png)
_Notification that you have successfully permitted Public Access_

## Locate and implement Object URL(s)
- navigate back to 'Objects'

![Navigate back to Objects](../../../Desktop/aws%20S3%20process/Navigate%20back%20to%20'Objects',%20click%20on%20file.png)

- Click on the object 'Name'
- within 'Properties', locate 'Object URL'

![Locate 'Object URL'](../../../Desktop/aws%20S3%20process/Locate%20'Object%20URL'.png)

- Click on the link and it will serve up the live URL that displays the object uploaded to the bucket

![Object URL data](../../../Desktop/aws%20S3%20process/Access%20live%20object%20URL%20for%20uploaded%20file.png)
_Seattle Public Library - This is an object I stored in a bucket to demonstrate._

- copy & paste the URL for development purposes

## ET VOILA!

[Visual guide featured on AWS in Plain English] (https://medium.com/aws-in-plain-english/storing-retrieving-implementing-objects-using-aws-s3-e2b206e98623) 

