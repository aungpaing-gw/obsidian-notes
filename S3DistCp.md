S3DistCp is the primary data transfer utility used in EMR. 
It is an extension of the opensource Apache DistCp and is optimized to work with S3.
S3DistCp can be used to transfer data from S3 to HDFS, between S3 buckets or from HDFS to S3.
S3DistCp can compress files on the fly, aggregate many smaller files into fewer large files based on patterns to save on performance and cost, and even upload files larger than 1TB by doing multipart uploads.