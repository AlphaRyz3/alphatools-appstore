# VibraVid

VibraVid downloads movies, series and anime requested through Seerr, Sonarr and Radarr, then hands the files back to your library.

## Before you install

- **Port and subdomain:** choose them in the install form and change them later in the app settings. Allowed hosts and CSRF origins follow them. Inside the container, VibraVid always listens on port 8000.
- **Library:** the host path `/media/Media` is mounted at the same path inside the container.
- **Configuration:** `config.toml` and `login.toml` live in `data/conf`, so credentials stay out of the install form.
- **Proxy:** scraping and downloads can go through a proxy on the Runtipi network, such as the Gluetun app at `http://gluetun:8888`.

## Sonarr and Radarr webhooks

Apps on the Runtipi network can reach VibraVid by name, whatever host port you pick:

```
http://vibravid:8000/api/arr/webhook/sonarr/
http://vibravid:8000/api/arr/webhook/radarr/
```

## Updating

An update restarts the container and interrupts running downloads, so wait until the queue is empty. Check the [release notes](https://github.com/AstraeLabs/VibraVid/releases) first: configuration changes can ship in any release, including patches.
