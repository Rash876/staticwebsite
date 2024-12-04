# staticwebsite
This project is to host basic static website using Amazon S3.

1. You need to first create a basic HTML website that includes image files specifically in the ".jpg" format within a folder on your PC. 
2. Log into AWS, after which you must navigate to Amazon S3 clicking on "Create bucket" to create new bucket.
3. Ensure that you enter an appropriate name for the bucket that you are creating such aws-new-bucket. AWS provides the guidelines for bucket name.
4. Untick the "Block all public access" checkbox in addition to ticking the acknowledge just below the previous checkbox, then hit "Create bucket" to create the new bucket.
5. Now, you will now need to upload your website which you do by first selecting the bucket you have just created then proceeding to hit "Upload" which lead to another page where you hit "Add files" that lead to File manager pop-up window. Select the website you created along with the images file that is associated then hit "Open" to close pop-up window.
6. Proceed to hit "Upload" at the bottom of the page then hit "Close" after files are successfully upload.
7. Now, we need to add some more details to host the website. Proceed to the "Properties" section for your bucket and enable static hosting setting.
8. Proceed to the "Permissions" section and then hit "Edit" for "Bucket policy". Proceed  to hit add new statement then edit the file to include below code then hit "Save Changes".
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Statement1",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::static-website-876/*"
        }
    ]
}

9. Now, you can go to "Properties" section for the bucket you created and copy the website address located at the bottom for Static hosting and paste the link which will lead you to your static website that is now hosted via Amazon S3.
