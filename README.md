# Start-your-first-deep-learning-project-with-AWS-DeepLens



## Scenario
In this tutorial, we will guide you through creating and deploying your first deep learning model with AWS DeepLens. You will first register your device on AWS console. And create a deep learning project with pre-trained template, then deploy and view the project output directly from the device.


## Prerequisites
>The workshop’s region will be in ‘N.Virginia’

>An AWS DeepLens device is necessary for this tutorial. You can buy AWS DeepLens here: https://www.amazon.com/dp/B075Y3CK37


## Lab tutorial
### Register your AWS DeepLens Device
1.1.  On the **service menu**, click **AWS DeepLens**.

1.2. For the first time to start with this console, the get started page would be shown, click **Register Device**; otherwise, click the hamburger icon on the left side, choose **Devices**, then click **Register Device**. 

! [image 1.png](../image 1.png)

1.3. Step 1, Configure your AWS account: 
* In *Name your device*, give a specific name to your device (e.g. MyDeepLens).
* In *Permissions*, click **Create roles**, make sure you have a green check of IAM roles for DeepLens.
* In *Certificate*, click **Download certificate**.

1.4. Click **Next**.

1.5. Step 2, Connect to your device:
* Plug in and power on your device.
* Verify middle LED is blinking.
* Connect your computer to the DeepLens Wi-Fi network, it should be look like **AMDC-NNNN**.
* The DeepLens Wi-Fi full SSID and password are presented at the bottom of device.
* After the Wi-Fi has connected, you will be disconnected from your home or office Wi-Fi network and the internet.

1.6. Click **Next**, navigate to 192.168.0.1 to complete the setup process.

1.7. In Device Setup, Step 1, Connect to network:
* In *Wi-Fi network ID*, select the network that you want to connect.
* In *Wi-Fi password*, insert the network password.

1.8. Click **Next**.

1.9. In Device Setup, Step 2, Upload certificate: Click **Browse**, and choose the certificate file that you have downloaded previously.

1.10. Click **Next**.

1.11. In Device Setup, Step 3, Configure device access:
* In *Create device password*, set your specific password for your device and make sure the password meet the minimum requirements. (Please do not forget it!!!)
* In *SSH server*, choose **enabled**, to allow direct login without using AWS console via the SSH server on your device.
* In *Additional configuration*, choose **enabled**, for automatic device updates.

1.12. Click **Review**.

1.13. Step 3, Configure your device: Review the information, then click **Finished**.

1.14. Now, you can find your registered device on the AWS DeepLens console devices.



### Create a Deep Learning Project

2.1. Go to **AWS DeepLens** console.

2.2. Click hamburger icon, and choose **Projects**.

2.3. Click **Create new project**.

2.4. Step 1, Choose project type:
* In Project type, choose **Use a project template**.
* In Project template, choose **Object Detection**.

2.5. Click **Next**.

2.6. Step 2, Specify project details: In Project information, you can specify your project name and description, or just leave them as default.

2.7. Click **Create**.

### Deploy the Deep Learning Project

3.1. In Project console, choose the project that you just create, then click **Deploy to device**.

3.2. Step 1, Target device: In Target device, choose the device that you want to deploy the project to.

3.3. Click **Review**. 

3.4. Step 2, Review and deploy: Review the function and the model of the project.

3.5. Click **Deploy**.

3.6. Wait until the deployment display green and show succeeded.

! [image 2.png](../image 2.png)

### View Project Output through MQTT client

4.1. *Copy* the topic of DeepLens, it should be look like **$aws/things/deeplens_xxxxxxxxxxx/infer**.

4.2. Go to **AWS IoT** console.

4.3. Select **Test** on the left side.

4.4. *Paste* the topic into the Subscription topic input field.

! [image 3.png](../image 3.png)

4.5. Click **Subscribe to topic**.

4.6. Then the project output should be able to view, if you do not see any message, move your DeepLens device to let it look at something that could be detected in this object detection model.

### View Project Output through browser

5.1. In Select a browser to import the streaming certificate, expand the choices, and choose the browser that you used.

5.2. Click **View Stream**.

5.3. Select the Certificate folder which you've downloaded during the register device process.

5.4. Insert the password of your device which is set up during the register process.

5.5. Then the project output would be presented on the browser.


## Conclusion

Congratulations! You now have learned how to:
* Register your DeepLens device
* Create DeepLens project
* Deploy the project to DeepLens device

## Next Level
Using Lambda function to extend a deep learning project with AWS DeepLens

