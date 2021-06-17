# Task-18

ARTH - Task 18 👨🏻‍💻

Task Description📄

🔅 *Create an AWS EC2 instance*

🔅 *Configure the instance with Apache Webserver.*

🔅 *Download php application name "WordPress".*

🔅 *As wordpress stores data at the backend in MySQL Database server. Therefore, you need to setup a MySQL server using AWS RDS service using Free Tier.*

🔅 *Provide the endpoint/connection string to the WordPress application to make it work.*

# Solution

---
Create an AWS EC2 instance:
---
- IMAGE NAME: AMI LINUX 2
- INSTANCE TYPE: t2.micro

![image](https://user-images.githubusercontent.com/69779873/122474009-3beddb80-cfe0-11eb-8177-d9b548bb41ea.png)

---
Configure the instance with Apache Webserver:
---

- Install httpd for Apache Webserver: yum install httpd -y

![image](https://user-images.githubusercontent.com/69779873/122474326-b0c11580-cfe0-11eb-8287-9423e093faea.png)

![image](https://user-images.githubusercontent.com/69779873/122474355-b880ba00-cfe0-11eb-9d15-0aee014fa2a3.png)


- Edit httpd configuration /etc/httpd/conf/httpd.conf as given below: 
	AllowOverride     ALL
- restart httpd service: systemctl restart httpd

![image](https://user-images.githubusercontent.com/69779873/122474439-d9490f80-cfe0-11eb-8154-cb0d08c30694.png)

---
Download php application name "WordPress"
---

- Install WordPress: wget https://wordpress.org/latest.tar.gz
- Extract: tar -xzf latest.tar.gz
- And move to /var/www/html/ dir

![image](https://user-images.githubusercontent.com/69779873/122474534-fda4ec00-cfe0-11eb-9fa8-f9d008a7c804.png)

![image](https://user-images.githubusercontent.com/69779873/122474552-05649080-cfe1-11eb-9b3a-bd2c7a94fc27.png)

- Install PHP and MySQL:
	- PHP -> amazon-linux-extras install php7.2 –y
	- MySQL -> yum install mysql –y

![image](https://user-images.githubusercontent.com/69779873/122474605-18776080-cfe1-11eb-8cf5-a04ab6184499.png)

![image](https://user-images.githubusercontent.com/69779873/122474617-1c0ae780-cfe1-11eb-8b68-58266f758119.png)

- And now restart httpd service, so that configuration of Wordpress can be set-up: yum restart httpd

---
As WordPress stores data at the backend in MySQL Database server. Therefore, you need to setup a MySQL server using AWS RDS service using Free Tier:
---

- Create RDS:

![image](https://user-images.githubusercontent.com/69779873/122474823-5c6a6580-cfe1-11eb-985f-00d108eab92f.png)

![image](https://user-images.githubusercontent.com/69779873/122474843-612f1980-cfe1-11eb-987f-4f56f50cab05.png)

![image](https://user-images.githubusercontent.com/69779873/122474860-68eebe00-cfe1-11eb-9f29-f5f3ce9640f6.png)

![image](https://user-images.githubusercontent.com/69779873/122474871-6c824500-cfe1-11eb-8b87-cd1f7f86160a.png)

![image](https://user-images.githubusercontent.com/69779873/122474882-71df8f80-cfe1-11eb-83bb-94f3b580f5a4.png)

![image](https://user-images.githubusercontent.com/69779873/122474893-75731680-cfe1-11eb-9c16-7f3eab665326.png)

![image](https://user-images.githubusercontent.com/69779873/122474917-7dcb5180-cfe1-11eb-9d18-1d773fdbb8fe.png)

![image](https://user-images.githubusercontent.com/69779873/122474935-8459c900-cfe1-11eb-812e-f31cfbc4feec.png)

- Now, Login in MySQL using Endpoint of RDS.

![image](https://user-images.githubusercontent.com/69779873/122474959-8e7bc780-cfe1-11eb-87d3-110feb92ab35.png)

- Create a DB:
		Create database <giveName>;
  
![image](https://user-images.githubusercontent.com/69779873/122474997-a05d6a80-cfe1-11eb-812f-b5ce6dc87e07.png)
  
![image](https://user-images.githubusercontent.com/69779873/122475019-af441d00-cfe1-11eb-8946-7739f1e83381.png)

- Now, all setup related to RDS has been done and now we have to use WordPress Application and WordPress will use this db.
  
![image](https://user-images.githubusercontent.com/69779873/122475074-bf5bfc80-cfe1-11eb-83ee-2494e0eac233.png)

![image](https://user-images.githubusercontent.com/69779873/122475087-c4b94700-cfe1-11eb-9392-66825c0eb11e.png)

![image](https://user-images.githubusercontent.com/69779873/122475106-ca169180-cfe1-11eb-83e0-8e5362f067a2.png)
  




  


