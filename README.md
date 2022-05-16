## A bookmarks service for me and my friends

The plan: host a personal bookmarks service, for me and some friends. Just getting this off the ground, but idea will be to use [linkding](https://github.com/sissbruecker/linkding) for bookmarks creation. linkding doesn't do public browsing by design (sissbruecker/linkding#70), but I want some sort of public/shared browsing, so I'll build something on top of the API.

Want access? If we know each other a bit, if you'd consider me a friend or at least friendly, drop me an email. 

## Deployment notes

Running on Fly.

### Initial setup

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

