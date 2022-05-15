## Initial setup

- create the fly app
- create a data volume, map it in `fly.toml`
- deploy
- ssh to instance, createsuperuser

Something like this:

```
fly launch
fly volumes create bookmarkslol_data --region sea
fly deploy
fly ssh console
    > cd /etc/linkding; python manage.py createsuperuser
```
