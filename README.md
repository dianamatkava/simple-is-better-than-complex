# About
Nov 2021  
This project was created following the [Simple is better than complex](https://simpleisbetterthancomplex.com/) lessons

+ additional tutorials from this resource

* Django (basic), Django Unit Test, Celery, Shell, Docker, JavaScript
* Crop Images, adding multiple users, upload multiple files
* Reset password, SendEmail, crispyForm, allauth
* reCAPTCHA, PDF and CSV export, history log


# Build the project

## Environment  
Create a `.env.dev` file at the project root with the following variables:

```dotenv
SECRET_KEY=your_secret_key
DB_NAME=your_db_name
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_HOST=your_db_host
DB_PORT=your_db_port
EMAIL_HOST_USER=your_email_user
EMAIL_HOST_PASSWORD=your_email_password
GOOGLE_RECAPTCHA_SECRET_KEY=your_recaptcha_secret
RECAPTCHA_PRIVATE_KEY=your_recaptcha_private_key
RECAPTCHA_PUBLIC_KEY=your_recaptcha_public_key
```  

## Using Docker Compose (development)
```bash
# build docker image
docker-compose -f docker-compose.dev.yml build

# start services
docker-compose -f docker-compose.dev.yml up -d

# stop services
docker-compose -f docker-compose.dev.yml down
```  
(Remove `-d` to see logs. Use `sudo` if necessary.)

---

# Celery

To run a worker:
```bash
celery -A myproject worker -l info
```
To run Flower monitoring:
```bash
celery flower --port=5555
```