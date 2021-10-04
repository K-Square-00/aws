# Amazon S3 Overview

1. Create a bucket in Amazon S3
2. Add an object to a bucket
3. Manage access permissions on an object and a bucket
4. Access and trasnfer files between EC2 and S3 Bucket
5. Create a bucket policy
6. Use bucket versioning

# Useful Command
cd ~

pwd

aws s3 ls s3://<bucketname>

aws s3 cp <filename> s3://<bucketname>

aws s3 cp s3://<bucketname> <filename>


# Sample Policy
{
    "Version": "2012-10-17",
    "Id": "Policy1604428844058",
    "Statement": [
        {
            "Sid": "Stmt1604428821481",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::285058481724:role/EC2InstanceProfileRole"
            },
            "Action": [
                "s3:GetObject",
                "s3:PutObject"
            ],
            "Resource": "arn:aws:s3:::reportbucket987987/*"
        },
        {
            "Sid": "Stmt1604428842806",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::reportbucket987987/*"
        }
    ]
}


Additional resources
Amazon S3 at http://aws.amazon.com/s3
Amazon S3 training at https://www.aws.training/LearningLibrary?&search=Amazon%20Simple%20Storage%20Service&tab=view_all
Editing Object Permissions at http://docs.aws.amazon.com/AmazonS3/latest/UG/EditingPermissionsonanObject.html
Amazon S3 bucket naming rules at https://docs.aws.amazon.com/AmazonS3/latest/dev//BucketRestrictions.html#bucketnamingrules
Amazon S3 block public access at https://docs.aws.amazon.com/AmazonS3/latest/user-guide/block-public-access.html
Amazon Resource Names (ARNs) and AWS Service Namespaces documentation at https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
AWS JSON Policy Elements documentation at https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_principal.html
Actions, Resources, and Condition Keys for Amazon S3 at https://docs.aws.amazon.com/IAM/latest/UserGuide/list_amazons3.html
Amazon S3 Versioning at https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html
Undelete objects in Amazon S3 at https://docs.aws.amazon.com/AmazonS3/latest/user-guide/undelete-objects.html
Deleting object versions in Amazon S3 at https://docs.aws.amazon.com/AmazonS3/latest/dev/DeletingObjectVersions.html
Amazon S3 Versioning cost considerations at https://aws.amazon.com/s3/faqs/
AWS Systems Manager Session Manager at https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html
For more information about AWS Training and Certification, see https://aws.amazon.com/training/.

