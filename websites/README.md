# Developing Websites

## Static Sites

Use Jekyll...and host on Github Pages.


## Wordpress

- As a WordPress admin to create a new site
- Ask to have a domain added (in Route 53; if a `.clir.org` domain, also
  added to the Windows DC)
- Create a new Apache config (be sure the file extension is `.conf`).
  This uses *newdomain* as a placeholder; replace this with the actual
domain you're creating.

```
$ cd /etc/apache2/sites-available
$ sudo cp wordpress.clir.org.conf newdomain.clir.org.conf
$ sudo vim newdomain.clir.org.conf
```

In `vim` do `<esc> :%s/wordpress/newdomain/g <enter>` then `:x`.

The enable the site and reload the `apache2` deamon:

```
$ sudo a2ensite newdomain
$ sudo service apache2 reload
```

- If you need SSL, we can generate these:

```
$ sudo letsencrypt -d newdomain.clir.org
```

Choose if you want **Easy** (add TLS, but don't force all traffic) or
**Secure** (all traffice on TLS).

# TLS for Websites

TLS for websites is provided on server through [EFF Certbo](https://certbot.eff.org/)
(what drives the [Let's Encrypt project](https://letsencrypt.org/)).
The package is updated via `apt` on the server and included in
server self-updates.


