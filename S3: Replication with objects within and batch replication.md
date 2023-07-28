# Replicate Existing Objects in your Amazon S3 Buckets with Amazon S3 Batch Replication

¿How to replicate objects already existing in your buckets within the same AWS Region or across different AWS Regions with Amazon Simple Storage Service (Amazon S3) Batch Replication.?

## Objetivos

- Configure S3 Replication on your Amazon S3 bucket
  - Create two S3 buckets
  - Create an S3 Replication rule on your S3 bucket
  - Choose a destination S3 bucket
  - Choose or create IAM roles for replication
  - Specify the encryption type (optional)
  - Choose the destination S3 storage class
  - Enable additional replication options (optional)
- ` `Configure S3 Batch Replication for existing objects in your Amazon S3 bucket in the following ways:
  - Create an S3 Batch Replication job when you create a new replication configuration on your bucket or when you add a new destination to your existing replication configuration
  - Create an S3 Batch Replication job from the S3 Batch Operations home page (recommended)
  - Create an S3 Batch Replication job from existing replication configuration page


|Tiempo de realización|Servicios utilizados|Requisitos previos|
| :-: | :-: | :-: |
|40 minutos|Amazon S3|Ninguno|


### Step 1: Create an Amazon S3 bucket
1\.1 — Sign in to the Amazon S3 console

From the AWS console services search bar, enter S3. Under the services search results section, select S3.

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.001.png)

1\.2 — Create an S3 bucket 

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.002.png)

1\.3

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.003.png)

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.004.png)

1\.4

Make sure to enable Bucket Versioning for the destination S3 bucket as well. 

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.005.png)

### Step 2: Create an S3 Replication on your S3 bucket

2\.1 – 

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.006.png)

2\.2.-

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.007.png)

2\.3.-

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.008.png)

2\.4.-

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.009.png)

2\.5.-

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.010.png)

2\.6.- 

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.011.png)

2\.7.-

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.012.png)

2\.8 

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.013.png)

2\.10.-

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.014.png)

### Step 3: Replicate existing objects while creating a new replication configuration

On the Create Batch Operations job page, you can review S3 Batch Operations Job

settings such as job run options, scope of S3 completion reports, and permissions.

3\.1.-

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.015.png)


3\.2


![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.016.png)

3\.3 For additional security, encrypt the manifest file using Amazon S3 managed keys (SSE-S3) or with AWS Key Management Service key (SS3-KMS).


3\.4.- 

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.017.png)

3\.5 Select the Job ID of your new job to review the job configuration. You can also track the status of the Batch Replication job.


### Step 4: Replicate existing objects with existing replication configuration

4\.1.-

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.018.png)

4\.2.-

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.019.png)

4\.3

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.020.png)

4\.4 (Optional) If you chose to save the Batch Operations manifest, encrypt your manifest file using Amazon S3 managed keys (SSE-S3) or using the AWS Key Management Service key (SSE-KMS) for additional security and access control.

4\.5 Choose Next to go to the Choose operation page.

4\.6 If you chose Create manifest using S3 Replication Configuration on the previous page

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.021.png)

4\.7 Configure additional options

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.022.png)

4\.9 Choose a valid Batch Operations IAM role to grant Amazon S3 permissions to perform actions on your behalf.

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.023.png)

4\.10 Add Job tags

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.024.png)

4\.11.- When your job is ready, choose Create job.  

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.025.png)

4\.12 After the Batch Replication job is created, Batch Operations processes the manifest. If successful, it will change the job status to Awaiting your confirmation to run.

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.026.png)

### Step 5: Create Batch Replication job from S3 Replication configuration page

5\.1.-

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.027.png)

5\.2.- 

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.028.png)

5\.3.-

![](resources/simpleStorage4/Aspose.Words.86e31782-3492-4c2b-aead-96f6c1032174.029.png)

5\.4 On the replication configuration home page for your source bucket


### Step 6: Monitor the progress of an S3 Batch Replication job

After a Batch Replication job is created and run, it progresses through a series of statuses. You can track the progress of a Batch Replication job by referring to these statuses on the Batch Operations home page.

### Step 7: Clean up resources