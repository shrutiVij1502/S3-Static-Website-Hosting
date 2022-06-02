# POC-2 (Configure a Static website using S3)
### Create an S3 bucket.
### Upload some static files which contain a sample website.
### Configure S3 as a host to serve those files as a site.

**Step1 : Create an S3 Bucket** 

![image](https://user-images.githubusercontent.com/67600604/171572497-e6fb7bb7-52b8-47c1-8533-ead257cdcf1b.png)

to host the website, a prerequisite is to have a domain and for this, we have to pick a name. In our case, we pick a name from freenom.com and you have to name your bucket as of your domain name

Here, i have created a bucket named as www.shruti1.ga as i had the domain as shruti1.ga

**Step2 : Upload some static files which contain a sample website** - Upload the html file named as index.html in your bucket and all Related image and stuff in the named folder.

Note - While uploading make sure to enable the public access mode

**Step 3 : Configure S3 as a host to serve those files as a site** - Go into the Properties -> static web hosting -> Enable

Next, go into the bucket permissions -> Bucket policy -> put the code of Grant Read Only Permission to anonymous user into the bucket policy 

![image](https://user-images.githubusercontent.com/67600604/171576125-5de33b3d-93b7-488f-b904-ebb092af961d.png)

Open the Route53 Services of AWS -> DNS Management -> Create a hosted Zone of same as the domain name

Now, create the record set into the bucket -> Enable the Alias Mode -> set the Bucket name having your website File and Save.

Finally check your URL on browser (e.g. shruti1.ga or wwww.shruti1.ga)

![image](https://user-images.githubusercontent.com/67600604/171574154-978f258f-f06f-42de-880b-5472b7fab6d0.png)
