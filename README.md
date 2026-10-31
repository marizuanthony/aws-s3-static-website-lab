## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to use S3 to host a static website, we are doing this projects to properly document how aws and cloud service can store objects in the cloud and host website. (how does that work?)

### Tools and concepts

Services I used were Amazon S3,  Key concepts I learnt include bucket policies, uploading static website files,  index.html, Bucket endpoint URL, ACL and how they control access to our bucket objects.

### Time, challenges, and wins

This project took me approximately 35 mins. The most challenging part was resolving the 403 forbidden error. It was most rewarding to our website go live and be public to the world.

### ❤️ Thanks for doing this project!

I chose to do this project today because I wanted to document a project in a clear manner so i could be replicated by interested individuals..

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I will we will open up S3 and create a storage space to start storing website files

### How long it took to create the bucket

Creating an S3 bucket took me less than 5 mins. Whats important to note is that the process of creating an S3 bucket can be replicate quicker for a larger scale scenario using the Command Line Interface.

### Region selection

The region we picked for our S3 Bucket was Stockholm, because its the region that is closest to us. it is best practice to pick the region that is closest to you because it lowers time to retrieve your things (latency) and cost. This is best practice.

### Understanding bucket name uniqueness

S3 bucket names are globally unique! This means no two S3 buckets in the entire world can have the same name, they have to be completely unique regardless of the region or the account ID.

![How I Set Up an S3 Bucket](https://nextwork.ai/anthony-marizu/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_ba6d42ad)

## Upload Website Files to S3

### What I did in this step

In this step, I will upload the website files into our S3 bucket. This is important because our bucket is still empty, lets get files inside so we have a website to host

### Files I uploaded

I uploaded two files to my S3 bucket - they were an index.html file (this determines structure ie what goes inside your website) and a folder of images and assets (this will fill in the website with images and things to look at)

### How the files work together

Both files are necessary for this project as index.html determines the structure, but the structure alone does not illustrate the contents of the website ie if index.html says 'insert image here' it might not have the actual image to display, you need to supply that image seperately that why we have multiple files uploaded. The index.html file to direct what is inside the website page but also a bunch of assets like images that the website is trying to display.

![Upload Website Files to S3](https://nextwork.ai/anthony-marizu/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_a265af88)

## Static Website Hosting on S3

### What I did in this step

In this step, I will make our website available to the world. This is called static website hosting and its important because our website files will stay as just files and not turn into a website if we dont do this step.

### Understanding website hosting

Website hosting means you are making use of servers provisioned to make your website accessible to anyone on the internet

### How I enabled website hosting

To enable website hosting with my S3 bucket, I went into the properties tab in our bucket, enabled static website hosting and we also labeled index.html as our index document ie this is the document that we are trying to host.

### Access Control Lists (ACLs)

An ACL (Access Control List) configures permission settings inside a bucket. We enable ACL's so that we can control access for our website files later. There was a pop up mentioning that Aws recommends disabling ACLs but we will keep it enabled to learn how ACLs work and compare it with bucket policies later.

![Static Website Hosting on S3](https://nextwork.ai/anthony-marizu/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_c22c54c0)

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website is enabled, S3 produces a bucket endpoint URL, which is a URL that takes you and anyone on the internet to the website that you are hosting

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I saw a 403 forbidden error, the reason for this error is because objects in an S3 bucket are private by default even though we have switched off 'Block all public access' the website files themselves are still completely private, we need to manage their access settings seperately, they need to be public files to for the public to see the contents of our website.

![Bucket Endpoints](https://nextwork.ai/anthony-marizu/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_22ce4daf)

## Success!

### What I did in this step

In this step, I will go into the files that we have uploaded into our bucket and make them public too because this will enable the internet to access the contents of our website. Once that is done, our website is officially live.

### How I resolved the 403 error

To resolve this 403 Forbidden error, I updated the access setting of the files inside our bucket too. Using ACLs we made our bucket files public. Once we check our bucket endpoint we can see a webpage all loaded up. Great Work.

### ✅ What were the key services and concepts you learnt in this project?

Services I used were Amazon S3,  Key concepts I learnt include bucket policies, uploading static website files,  index.html, Bucket endpoint URL, ACL and how they control access to our bucket objects.

### ✅ How long did it take you to complete this project?

This project took me approximately 35 mins. The most challenging part was resolving the 403 forbidden error. It was most rewarding to our website go live and be public to the world.

### ❤️ Thanks for doing this project!

I chose to do this project today because I wanted to document a project in a clear manner so i could be replicated by interested individuals.

![Success!](https://nextwork.ai/anthony-marizu/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_5d4474f9)

## Bucket Policies

### What I did in this extension

In this project extension I'm about to use bucket policies to control access to our buckets files. I'm doing this so that we can stop people from deleting the objects inside the files

### Understanding bucket policies

An alternative to ACLs are bucket policies, which are rules that determine who is allowed or not allowed to do something. The benefit of using bucket policies is that you can have even greater control of the action that people are or are not allowed to do while ACLs are useful for controling public access to individual objects inside the bucket.

![Bucket Policies](https://nextwork.ai/anthony-marizu/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_sm2sm2sm)

### What my bucket policy does

My bucket policy is working properly, it denies everyone from deleting our index.html file in the bucket. I tested this by trying to delete the index.html file and saw a permission denied error "failed to delete". The bucket policy successfuly stop us from deleting objects
