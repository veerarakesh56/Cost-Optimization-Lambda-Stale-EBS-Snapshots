# AWS Cloud Cost Optimization - Eliminating Unused/Stale Resources

![Cost-Optimization-Lambda](https://github.com/user-attachments/assets/64a48d6f-6206-4d35-bc28-57f1e09c0ecb)

## Detecting and Deleting Obsolete/Stale EBS Snapshots

This example illustrates how to create a Lambda function that identifies and removes EBS snapshots that are no longer linked to any active EC2 instances, resulting in cost savings.

### Description:

The Lambda function retrieves a list of all EBS snapshots owned by the current account and a list of active EC2 instances (including those that are running and stopped). It then iterates through each snapshot, checking if the associated volume (if present) is not attached to any active instance. If a snapshot is found to be unused, it is deleted, thereby optimizing storage costs.

