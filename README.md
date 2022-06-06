# POC-2 (Configure a Static website using S3)
### Create an S3 bucket.
### Upload some static files which contain a sample website.
### Configure S3 as a host to serve those files as a site.

**Step1 : Create an S3 Bucket** 

![image](https://user-images.githubusercontent.com/67600604/172104017-9147465d-e2b0-4bce-a180-d75eaa7f19ae.png)

To host the website, a prerequisite is to have a domain and for this, we have to pick a name. In our case, we pick a name from freenom.com and you have to name your bucket as of your domain name

Here, i have created a bucket named as shruti2.tk as I had the domain as shruti2.tk

**Step2 : Upload some static files which contain a sample website** - Upload the html file named as index.html in your bucket and all Related image and stuff in the named folder.

Note - While uploading make sure to enable the public access mode

**Step 3 : Configure S3 as a host to serve those files as a site** - Go into the Properties -> static web hosting -> Enable

Next, go into the bucket permissions -> Bucket policy -> put the code of Grant Read Only Permission to anonymous user into the bucket policy 

![image](https://user-images.githubusercontent.com/67600604/172104172-45546fec-72fd-4f67-90e3-45f9a73ec244.png)

**Step3 :**  Open the Route53 Services of AWS -> DNS Management -> Create a hosted Zone of same as the domain name

Now, we will request for the certificate from ACM, go to the console and search for ACM and request a public SSL/TLS certifificate and to validate it, create a record of the certificate in route 53, and it will get issued.

![image](https://user-images.githubusercontent.com/67600604/172104940-6ebdb262-4f8b-44f7-ae5a-8015a203f1da.png)

After that, go to the Cloudfront and paste the s3 link in the domain name and enable the option "Redirect to https from http" and in the CNAME, add your domain name, where you want it to get verified.

![image](https://user-images.githubusercontent.com/67600604/172104991-44462f63-93cb-47f7-9224-f5a833710d4e.png)

and now wait for few minutes and search for your URL in the browser


Finally check your URL on browser , it is showing the lock(e.g. shruti2.tk)

![image](https://user-images.githubusercontent.com/67600604/172104903-b66c006b-cda0-481a-816a-cfb128818c4c.png)

![image](https://user-images.githubusercontent.com/67600604/172105634-316fa580-f496-432c-97e1-689104c0239d.png)

Certificate is issued by amazon

