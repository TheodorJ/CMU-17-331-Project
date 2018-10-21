# How to hide this service

1. Install Tor

  `sudo apt-get install tor`

2. Change hidden service port

  In `/etc/tor/torrc`, uncomment:

  ```
  HiddenServiceDir <some directory with non-root access>
  HiddenServicePort 80 127.0.0.1:<port>
  ```

3. Add hostname to `ALLOWED_HOSTS` in `settings.py`

  `cat <dir>/hostname`

4. Run server

  `python3 manage.py runserver 0.0.0.0:<port>`

5. Navigate to your hostname in Tor Browser to verify that the service works

## Additional Precautions
