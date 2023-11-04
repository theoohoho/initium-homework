
# Initium Homework

Initium Homework for interview

## Run Locally with Docker

1. Clone the project

2. Build server and related service images

    ```bash
      docker compose -y local.yml build
    ```

3. Start the server

    ```bash
      docker compose -y local.yml up -d
    ```

4. Go to login page `localhost:8000`

5. Go to admin page `localhost:8000/admin`

6. Shutdonw the server

    ```bash
      docker compose -y local.yml down
    ```

### Setup user

- Create a **normal user account**
  1. Go to Sign Up and fill out the form.
  2. Go to terminal console to see a email verification message.
  3. Copy the link into browser.
  4. User's email should be verified and ready to go.

- Create a **superuser account**

      $ python manage.py createsuperuser


## Run Locally with HTTPS

1. Generate SSL certificate

    Refer this [link](https://letsencrypt.org/docs/certificates-for-localhost/)

2. Take certificate and key and put it in `./certs` folder

3. Go to `./.envs/.local/.django` and update `VIRTUAL_HOST` to your hostname

    ```bash
    VIRTUAL_HOST=my-hostname
    ```

4. Go to `config/settings/local.py` Add your hostname in `ALLOWED_HOSTS`

    ```python
    ALLOWED_HOSTS = ["localhost", "0.0.0.0", "127.0.0.1", "my-hostname"]
    ```

