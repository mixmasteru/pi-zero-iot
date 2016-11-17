# pi-zero-iot
AWS Iot connection from Raspberry Pi Zero

## setup AWS
* create IAM user for IoT 
* setup AWS IoT device

## setup pi
* install jessie lite on pi
* setup Wifi
* ssh login to pi

```
sudo apt-get install git
sudo apt-get install python-pip
sudo pip install AWSIoTPythonSDK
sudo pip install awscli
git clone https://github.com/aws/aws-iot-device-sdk-python.git
```
* setup AWS cret - aws configure
* download root cert - wget https://www.symantec.com/content/en/us/enterprise/verisign/roots/VeriSign-Class%203-Public-Primary-Certification-Authority-G5.pem (rename for better handling)
* download cert for IoT thing
* download private key for IoT thing
* change topic in basicPubSub.py

## run test
via websockets:
```
python basicPubSub.py -r aws_root.pem -e xxxxxxxxxxxx.iot.zone.amazonaws.com -c xxxxxxx-certificate.pem.crt -k xxxxxxx-private.pem.key -w
```
