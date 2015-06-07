FROM registry:0.9.1
MAINTAINER Li Yi <denverdino@gmail.com>
# Packaged dependencies
RUN apt-get update && apt-get install -y wget unzip 

# Get ali-oss api 
RUN mkdir -p /ali_oss/api && cd /ali_oss/api \
    && wget http://aliyunecs.oss-cn-hangzhou.aliyuncs.com/OSS_Python_API_20140509.zip \
    && unzip OSS_Python_API_20140509.zip && sudo python setup.py install

# Get docker-registry-driver-alioss
RUN cd /ali_oss \
    && wget -r -np -nd --no-check-certificate https://github.com/chris-jin/docker-registry-driver-alioss/archive/master.zip \
    && unzip master.zip && cd docker-registry-driver-alioss-master/ && sudo python setup.py install && rm -rf /ali_oss

# Add ali oss config
ADD config_sample.yml /docker-registry/config/config_sample.yml
ENV SETTINGS_FLAVOR oss
ENV OSS_HOST your_oss_host
ENV OSS_BUCKET your_oss_bucket
ENV OSS_KEY your_access_key_id
ENV OSS_SECRET your_access_key_secret
CMD exec docker-registry
