# AWS Openweathermap API ETL

<img width="553" alt="image" src="https://github.com/user-attachments/assets/d425a300-da55-4aeb-80c5-8eb30ef34948" />


Real Time Stock Market Data Pipeline 
AWS Cloud Data Engineering Project |Data Pipeline using Python, Airflow, S3

I want to share my latest Data Engineering project where I put my skills to the test by working with an AWS cloud using Python and load into S3

🔬𝗣𝗿𝗼𝗷𝗲𝗰𝘁 𝗢𝘃𝗲𝗿𝘃𝗶𝗲𝘄: End-to-end data engineering on AWS. Where I ingested data from file to S3 using Python. Also used IAM and VPC for data governance. More information can be found in the GitHub repository.

💾 𝗗𝗮𝘁𝗮 𝗦𝗼𝘂𝗿𝗰𝗲: https://openweathermap.org/api

🎯 𝗣𝗿𝗼𝗷𝗲𝗰𝘁 𝗚𝗼𝗮𝗹𝘀:

• Store data in S3.
• Run Airflow on EC2
• Use python to load from file to s3
• Implement IAM and VPC for governance.

 🔧The tools that are covered in this project are:

1. Amazon S3
2. Amazon EC2
3. Amazon IAM
4. Amazon VPC
5. Python
6. Airflow


## 1. Run EC2 to Install Airflow

<img width="950" alt="image" src="https://github.com/user-attachments/assets/306103bb-fe98-45e8-b2a2-9e8c1cc2e01f" />
<img width="952" alt="image" src="https://github.com/user-attachments/assets/c8c8f051-3f45-4b43-af18-3dcfe0f5d362" />
go to the instances > click security goup > add inbound rule > custom TCP, 8080, anywhere

## 2. Connect to EC2 and install required dependancies

sudo apt update
sudo apt install python3-pip

sudo apt update
sudo apt install -y software-properties-common

sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update

sudo apt install -y python3.10 python3.10-venv

python3 -m venv airflow_venv
source airflow_venv/bin/activate
pip install apache-airflow
pip install pandas
pip install s3fs

pip install apache-airflow-providers-amazon
airflow standalone
copy the password

Open airflow

copy the ip address from instances and add :8080 etc 18.235.101.34:8080
username: admin, password from the terminal just now

## 3. Create openweather account to get the API key

<img width="905" alt="image" src="https://github.com/user-attachments/assets/e4f575bb-ad64-42ef-889f-c64f329f8229" />

to call weather API
https://api.openweathermap.org/data/3.0/onecall?lat={lat}&lon={lon}&exclude={part}&appid={API key}

## 4. Create API connection in Airfow

Open airflow admin > connection

<img width="943" alt="image" src="https://github.com/user-attachments/assets/1bc759b2-16b2-42d9-a687-8448337cc87f" />

#% 5. Create s3 bucket to receive the data 

<img width="893" alt="image" src="https://github.com/user-attachments/assets/4eed4289-4a66-4e1d-9935-78f76c234fe1" />

## 6. Retrieve access key and store in somewhere (delete after project finish)

click on username (right top side) > security credentials > create access key > download it 

go to ec2 instance and run this command

sudo apt  install awscli
aws configure
aws sts get-session-token

## 7. Connect SSH to visual code, now we going to write DAG (for connect to SSH remote can followe this link: )

right click on bottom left > connect to Host (Remote-SSH) > choose the .config u created > create folder "DAG" under airflow > create "weather_dag.py" under DAG folder

<img width="926" alt="image" src="https://github.com/user-attachments/assets/b7fe2d98-5bb4-461d-8145-319ab3c007b8" />







