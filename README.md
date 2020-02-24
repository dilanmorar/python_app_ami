# Python app ami

This project was made in the aim of creating an ami containing the python app code and all the dependencies required to run the app. This is so that an instance can be created in aws and using the ami created will be able to run the python app.

## Creating an image

To create an image, when in the python_app_ami folder, in the command line type:
```
packer build python_app_cookbook/packer.json
```

## Running the app

Launch an instance in aws using the ami created, the name of the ami is specified in the packer.json folder

When instance has been created enter the machine using the key(key_name.pem) specified in packer.json and the ip address(xxx.xxx.xxx.xxx) generated. In the command line type:
```
ssh -i ~/location/of/key/key_name.pem ubuntu@xxx.xxx.xxx.xxx
```
Enter the app directory:
```
cd IT_Jobs_Watch_Data
```
Run the app:
```
python3 main.py
```
To find the contents of the app after completion go to the Downloads folder:
```
cd /home/vagrant/Downloads
```

## Cookbook

This cookbook was made by wrapping a previous cookbook https://github.com/dilanmorar/python_ami. The previous cookbook creates an ami which has all the dependencies required for the python app to run and also has jenkins installed. On jenkins a build was created to test the python app in which it passed so we know the python app will run. When creating an ami this cookbook also copies the python code (IT_Jobs_Watch_Data) as well as the dependencies so everything for the app to run is in this ami.
