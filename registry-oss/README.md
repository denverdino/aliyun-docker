# registry-oss
================
This image is built from official registry:0.9.1 with [Aliyun OSS driver](https://github.com/chris-jin/docker-registry-alioss).


Usage
-------------------

Assuming you have docker installed on your machine:

    docker build --rm=true -t registry-oss:0.9.1 . #to build the image from this dockerfile
    docker run -e OSS_HOST=<your_oss_host> -e OSS_BUCKET=<your_ali_oss_bucket> -e OSS_KEY=<your_access_key_id> -e OSS_SECRET=<your_access_key_secret> -p 5000:5000 -d registry-oss:0.9.1
    

References
-------------------
* [https://github.com/chris-jin/docker-registry-alioss](https://github.com/chris-jin/docker-registry-alioss)


Contributors
-------------------
* Li Yi (denverdino@gmail.com)

