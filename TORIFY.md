# How to hide this service

1. Install Tor

  `apt-get install tor`

2. Change hidden service port

  In `/etc/tor/torrc`, uncomment:

  ```
  HiddenServiceDir <some directory with non-root access>
  HiddenServicePort 80 127.0.0.1:<port> # NOT port 80
  ```

2.a) Start tor:
   `nohup tor &`

3. Add hostname (from your directory in 2) to `ALLOWED_HOSTS` in `settings.py`

  `cat <dir>/hostname`

4. Run server

  `python3 manage.py runserver <host>:<port>`

  Your host specifies the range of IP addresses or hostnames that your server can run on. You can use 0.0.0.0 to tell the server to accept requests destined for ALL IPs and domains, or set it to 127.0.0.1 to only accept requests originating from localhost.

5. Navigate to your hostname in Tor Browser to verify that the service works

## Additional Precautions
 - Don't use crappy passwords
 - Think about the ways people can attack your service. How can you stop those attacks?
    - This is a Django server, and you're running it in production. Make sure you take the necessary extra steps:
    - https://docs.djangoproject.com/en/2.1/howto/deployment/checklist/
 - Make sure your server is not running on the clearnet! If people can access your hidden service on the clearnet, it is definitive proof that you are the one running that hidden service.
