# S3 with boto3
Managing an S3 bucket using Python boto3.  

## Useful methods
  
- [`create_bucket()`](#creating-a-bucket)
- [`upload_file()`](#uploading-a-file)
- [`download_file()`](#downloading-a-file)
- [`delete_object()`](#deleting-a-file)
- [`delete_bucket()`](#deleting-a-bucket)

## Creating a Bucket
Make sure you give yourself write access 
```py
import boto3

s3 = boto3.client('s3')

s3.create_bucket(
    Bucket='bucket-name',
    CreateBucketConfiguration={
        'LocationConstraint': 'eu-west-1'
    }
)
```

## Uploading a File
```py
import boto3

s3 = boto3.client('s3')

filename = 'file-name.txt'
bucket_name = 'bucket-name'

s3.upload_file(filename, bucket_name, filename)
```

## Downloading a File
```py
import boto3

s3 = boto3.resource('s3') # make a note of this line!
# printing the type returns <class 'boto3.resources.factory.s3.ServiceResource'>

bucket_name = 'bucket-name'
key = 'file-name.txt'

s3.Bucket(bucket_name).download_file(key, 'local_file_name.txt')
```

## Deleting a File
```py
import boto3

s3 = boto3.client('s3')

bucket_name = 'bucket-name'
key = 'file-name.txt'

s3.delete_object(Bucket=bucket_name, Key=key)
```

## Deleting a Bucket
```py
import boto3

s3 = boto3.client('s3')

bucket_name = 'bucket-name' # not needed, but nice to have to check for misspelling

s3.delete_bucket(Bucket=bucket_name)
```