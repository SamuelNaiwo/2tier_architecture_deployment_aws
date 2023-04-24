# Local Files To EC2 & Deploy App

1. Launch a new instance. If you have an AMI set up already, then launch it through that.

2. Name your instance to help you remember what the instance is for.

    ![Alt text](local2ec2/20.%20Launch%20Instance.png)

3. Select your instance type and key pair. If you don't have a key pair, you can create a new one.

    ![Alt text](local2ec2/23.%20Instance%20type%20amd%20key%20pair.png)

4. Under network settings, select an existing security group. If you don't have one, you can create a security group.

    ![Alt text](local2ec2/24.%20Security%20group.png)

5. Uder the advance details tab, scroll down to user data and enter your provisioning shell script to automate tasks.

6. Now launch your new instance and you will see this if launched correctly.

    ![Alt text](local2ec2/25.%20Launch%20instance%20success.png)

7. Select your instance you just launced and click connect.

    ![Alt text](local2ec2/26.%20Connect%20instance%20to%20terminal.png)

8. Copy your ssh key

    ![Alt text](local2ec2/copy%20ssh%20key.png)

9. Open your terminal/bash window and change directory into your `.ssh` folder where your `.pem` file is stored.

10. Paste your ssh key into the terminal window and press enter. Type y to confirm.

11. Run the command `sudo apt update -y` to download any updates for your instane.

12. Run the command `sudo apt upgrade -y` to install the updates you just downloaded onto the instance.

13. Run the command `sudo apt install nginx -y` to install nginx.

14. Open another terminal and change directory into `.ssh` folder where your pem file is stored.

15. Run the command below to secure copy your app folder onto your instance.

    ```
    scp -i "tech221.pem" -r /Users/samuelnaiwo/Documents/tech221/virtualisation/app ubuntu@ec2-34-251-148-61.eu-west-1.compute.amazonaws.com:/home/ubuntu/
    ```