# <a name="_a9k7kceuydso"></a>Launch AWS EMR Cluster
## <a name="_liqm59wlqcss"></a>Objectives
- Launch an EMR (Elastic MapReduce) cluster to efficiently process and analyze large-scale datasets using distributed computing frameworks like Apache Hadoop and Apache Spark.
- Create an EMR cluster to support scalable data analytics, enabling the rapid processing of vast amounts of data.
## <a name="_r4lga3emmz5p"></a>Presentation
![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.001.png)

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.002.png)
## <a name="_kbxuio8ez7bm"></a>Lab Setup


|Time of performing|Required AWS services |
| :-: | :-: |
|20 minutes|VPC, EMR, S3, EC2, IAM|
## <a name="_shwckmyqvsac"></a>Steps
1. Create EC2 Key Pair	
1. ` `Navigate to EMR cluster.	
1. Create Cluster.	
1. Custom Cluster	
1. Cluster Configuration	
1. Cluster scaling manually	
1. Browse for VPC	
1. Browse for Subnet	
1. Manually terminate cluster	
1. Cluster Logs settings	
1. Ec2 Key Pair	10
1. Amazon EMR Service Role	
1. Create an instance profile	
1. Check out the whole cluster configuration
1. Cluster process of being created
## <a name="_b64b6e988p3n"></a>Step 1. Create EC2 Key Pair
- In the AWS Console navigate to the EC2 service.
- In the left panel, select the item titled **Key Pairs**.
- Select the item Create Key Pair.
- Give your key pair a name and choose .pem 
- Download it.

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.003.png)

## <a name="_alnizteecegx"></a>Step 2. Navigate to EMR cluster.
## <a name="_rky2ezzg30qh"></a>Step 3. Create Cluster.
![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.004.png)

## <a name="_u38pr4is3f2g"></a>Step 4. Custom Cluster

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.005.png)

For the section titled *Software Configuration* select the following options.


|**Option**|**Configuration**|
| :-: | :-: |
|Release|emr-6.11.0|
|Software|\*Hadoop, Hive, Tez, Pig, Spark, Livy and JupyterHub, JupyterEnterpriseGateway|
|Multi-master support|Leave as deafult|
|AWS Glue Data Catalog Settings|Select 1. Use for Hive table metadata, 2. Use for Spark table metadata|
|Amazon Linux Release|Leave as deafult|

## <a name="_c776zggbrxui"></a>Step 5. Cluster Configuration 
Select the following options.


|**Option**|**Configuration**|
| :-: | :-: |
|Instance group configuration|Leave as default|
|Primary|Leave as default|
|Core|Leave as default|
|Task|Leave as default|

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.006.png)

## <a name="_az57xg3ennhy"></a>Step 6. Cluster scaling manually
![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.007.png)

## <a name="_pqjg5tl59sa4"></a>Step 7. Browse for VPC 
And choose:

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.008.png)

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.009.png)
## <a name="_5jq6w9jikqo8"></a>Step 8. Browse for Subnet 
And choose:

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.010.png)

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.011.png)

## <a name="_y75ht5lukaj9"></a>Step 9. Manually terminate cluster

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.012.png)

## <a name="_wat2gz249d0t"></a>Step 10. Cluster Logs settings
Click on browse. Choose the bucket:

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.013.png)

## <a name="_l3gvtf8rni9a"></a>Step 11. Ec2 Key Pair 
Choose the key pair that we previously created.

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.014.png)

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.015.png)

## <a name="_f27pmfkihcf3"></a>Step 12. Amazon EMR Service Role


![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.016.png)

## <a name="_786bxtonfn9p"></a>Step 13. Create an instance profile

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.017.png)

## <a name="_jmen50kw3nq3"></a>Step 14. Check out the whole cluster configuration
In the right side check out the whole configuration. Finally, press on **Create cluster.**

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.018.png)

## <a name="_oep22d3ax7dj"></a>Step 15. Cluster process of being created. 

This can take a few minutes to complete. The cluster will be in waiting state once it completes.

![](resources/LunchClusterEMR/Aspose.Words.cf3488bd-a039-46c4-9761-f33c11d172c4.019.png)

## <a name="_imnozvozfdwn"></a>References
[Launch a cluster quickly](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-launch-with-quick-options.html)

[Tutorial: Getting started with Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-gs.html)

[Best practices for cluster configuration](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-instances-guidelines.html)
