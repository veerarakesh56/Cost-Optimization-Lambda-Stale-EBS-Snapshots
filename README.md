# AWS Cloud Cost Optimization - Eliminating Unused/Stale Resources

> ### Attribution — this is a follow-along, not an original project
>
> The Lambda function and this README come from the AWS cost-optimization module of
> **[iam-veeramalla/aws-devops-zero-to-hero](https://github.com/iam-veeramalla/aws-devops-zero-to-hero)**
> by Abhishek Veeramalla. Credit for the material is his.
>
> I worked through it to learn Boto3 against the EC2/EBS APIs and how to schedule a Lambda,
> and I keep the repo public as a record of that learning.
>
> My own engineering work is in **[warden](https://github.com/veerarakesh56/warden)** and
> **[helios](https://github.com/veerarakesh56/helios)**.


![Cost-Optimization-Lambda](https://github.com/user-attachments/assets/64a48d6f-6206-4d35-bc28-57f1e09c0ecb)

## Detecting and Deleting Obsolete/Stale EBS Snapshots

This example illustrates how to create a Lambda function that identifies and removes EBS snapshots that are no longer linked to any active EC2 instances, resulting in cost savings.

### Description:

The Lambda function retrieves a list of all EBS snapshots owned by the current account and a list of active EC2 instances (including those that are running and stopped). It then iterates through each snapshot, checking if the associated volume (if present) is not attached to any active instance. If a snapshot is found to be unused, it is deleted, thereby optimizing storage costs.

