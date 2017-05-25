# Insentia Exam Deployment

## Project
Create a solution that crawls for articles from a news website, cleanses the response, stores in a mongo database then makes it available to search via an API.

## Tech Stack
- MongoDB
- Django
- Django Rest Framework
- Nginx
- Scrapy
- AWS
- Docker
- Celery
- RabbitMQ

## Brief Overview
The website of 'bbc' and 'theguardian' is being scraped every 10 minutes powered by **Scrapy** periodically via **Celery** running on a **RabbitMQ** broker and saved to a third-party **MongoDB** hosted by **compose.io**. The API is built via **Django** with the support of **Django REST Framework** using **Gunicorn** as a WSGI and **Nginx** as a Web Server. The actual server is hosted by an **EC2 t2.micro** instance since it's still within **AWS's free-tier** and containerized by **Docker**.

## Instruction
Please do a get request to **http://ec2-54-169-41-252.ap-southeast-1.compute.amazonaws.com/api/v1/news/** and do some GET parameters to do the searches.

Currently the available searches are **title**, **tags**, **summary**, **text**. e.g. **http://ec2-54-169-41-252.ap-southeast-1.compute.amazonaws.com/api/v1/news/?tags=UK**