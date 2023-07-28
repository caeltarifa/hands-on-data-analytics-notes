# <a name="_v1anzz1lyxhu"></a>SSH Into The AWS EMR Master Node Cluster
## <a name="_liqm59wlqcss"></a>Objectives
- Enable secure remote access: Establish SSH connectivity to the EMR master node, ensuring safe communication between the user's machine and the cluster.
- Simplify cluster administration: Access the EMR master node to efficiently handle administrative tasks, configurations, and cluster performance monitoring.
- Enable interactive data analysis: SSH into the master node to interact with the cluster environment, run queries, and access specialized tools for exploring and analyzing data.

## <a name="_kbxuio8ez7bm"></a>Lab Setup

|Time of performing|Required AWS services |
| :-: | :-: |
|20 minutes|EC2, EMR, IAM|
## <a name="_shwckmyqvsac"></a>Steps
1. Navigate to the EMR service and select your cluster from the list of available clusters.

2. In the "Summary" tab, scroll down to the "Security and access" section and select the security group shown for EMR managed group.

3. Select the security group for "ElasticMapReduce-master".

4. Select Edit inbound rules.

5. Select the Add Rule button.

6. Add the rules that allow SSH.

7. Select Save.

8. Navigate to your EC2 instances in the console.

9. Access to the master node on the Cluster.

10. Select the master node instance.

11. Press on Connect.

12. Fill up with the user spark and connect.

13. Load the virtual machine

## <a name="_e2qvs34doc1s"></a>Step 1. 
Navigate to the EMR service and select your cluster from the list of available clusters.
## <a name="_oguk7yjtu5gx"></a>Step 2. 
In the "Summary" tab, scroll down to the "Security and access" section and select the security group shown for EMR managed group.
![](resources/sshAccessEMR/Aspose.Words.29a65168-d1b2-40e2-8980-cfa2fa228082.001.png)
## <a name="_qt7uii6romgd"></a>Step 3. 
Select the security group for "ElasticMapReduce-master"
![](resources/sshAccessEMR/Aspose.Words.29a65168-d1b2-40e2-8980-cfa2fa228082.002.png)

## <a name="_sh2javfj3i83"></a>Step 4. Select Edit inbound rules
![](resources/sshAccessEMR/Aspose.Words.29a65168-d1b2-40e2-8980-cfa2fa228082.003.png)

## <a name="_3sbqqzdgoomi"></a>Step 5. Select the Add Rule button
![](resources/sshAccessEMR/Aspose.Words.29a65168-d1b2-40e2-8980-cfa2fa228082.004.png)
## <a name="_oylavgc0h2e"></a>Step 6. Add the rules that allow SSH.
![](resources/sshAccessEMR/Aspose.Words.29a65168-d1b2-40e2-8980-cfa2fa228082.005.png)

## <a name="_898ltevduqai"></a>Step 7. Select Save

![](resources/sshAccessEMR/Aspose.Words.29a65168-d1b2-40e2-8980-cfa2fa228082.006.png)

## <a name="_rh1sxhmspo4w"></a>Step 8. Navigate to your EC2 instances in the console.

## <a name="_k2atm7h833f"></a>Step 9. Access to the master node on the Cluster
![](resources/sshAccessEMR/Aspose.Words.29a65168-d1b2-40e2-8980-cfa2fa228082.007.png)
## <a name="_dg2yz8di8rt2"></a>Step 10. Select the master node instance.
## <a name="_rudwy2ej6s4x"></a>Step 11. Press on **Connect**
![](resources/sshAccessEMR/Aspose.Words.29a65168-d1b2-40e2-8980-cfa2fa228082.008.png)

## <a name="_sp36stvyf0zu"></a>Step 12. Fill up with the user **spark** and connect

![](resources/sshAccessEMR/Aspose.Words.29a65168-d1b2-40e2-8980-cfa2fa228082.009.png)

<a name="_qqai7t2ehzy"></a>Step 13. Once loading the virtual machine.
![](resources/sshAccessEMR/Aspose.Words.29a65168-d1b2-40e2-8980-cfa2fa228082.010.png)
---------------------------------------------------------------------

## <a name="_imnozvozfdwn"></a>References
[New: Using Amazon EC2 Instance Connect for SSH access to your EC2 Instances](https://aws.amazon.com/blogs/compute/new-using-amazon-ec2-instance-connect-for-ssh-access-to-your-ec2-instances/)

[Connect using EC2 Instance Connect](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-connect-methods.html)

[Connect to your Linux instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstances.html)




