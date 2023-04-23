<p align="center">
<img src="https://dashboard.vetacloud.com/assets/vC-png-2.a21a37aa.png"></img>
</p>

# vetaCloud v0.1 S3 Integration 

How to use

To upload files to S3 via vetacloud, you need to create an S3 Bucket where you files would be stored in. To learn more on how to do it, please read [this.](https://docs.aws.amazon.com/AmazonS3/latest/userguide/creating-bucket.html) 

<br>

# Getting started

After you have created yoour bucket, proceed to this page and fill in your details.
<img width="1429" alt="Screen Shot 2023-04-24 at 12 25 25 AM" src="https://user-images.githubusercontent.com/63419117/233872007-13c9e957-302d-4cff-b312-0743a89ce0f3.png">


Note: We do not return the file's S3 path. We return the file's vetaCloud path however, your file can be found on your S3 bucket.

# Webhook
The webhook for every upload is in the response's data and here is an example:
```javasciptt
"status": 200,
"success": "true",
"message": "Successfully Uploaded",
"file": {
    "name": "p-cDcXTD3qxwrSB_8S2c2vjKYNLXgY45lpGkTUaiU6.mp4",
    "mimetype": "video/mp4",
    "destination": "https://cloud.vetacloud.com/uploads/VTCD_PUBLIC_112429bf443ffd71076d7ef756381c/react/p-cDcXTD3qxwrSB_8S2c2vjKYNLXgY45lpGkTUaiU6.mp4",
    "size": 1.414305,
    "qrroute": "https://cloud.vetacloud.com/qrCodes/99f28fdaaa3e99ae73e1f03f64dcb2b471823c956b4f2467d1abd72e1821.png"
}
```

### ```Successful file upload```
A successful file upload webhook is what we have above.
QR Route is generated for all users but the code is generated for only Advanced and Premium users. QR Route is the route of a QR Code which holds the link to the file. 

 ```
 The size is in Megabyte. We believe this simplifies accountability for users.
 
 ### ```Unsuccessful file upload```
 There are so many types of errors that could be returned if a file isn't successfully uploaded but below is an example.
 
 ```javascript
 { status: 400, success: 'false', message: 'File too large' }
 ```
