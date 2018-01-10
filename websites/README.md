# Developing Websites

## Static Sites

Use Jekyll...and host on Github Pages.

## Wordpress

- As a WordPress Network Admin to create a new site and fill out the
  'owner' information
- Ask to have a domain added (in Route 53; if a `.clir.org` domain, also
  added to the Windows DC). Delcor can do this if no one is around.
- On the newly created site, click on **Admin -> Tools -> Domain Mapping**
  and add the FQDN under "Add new domain" (e.g. test.clir.org)

### TODO
- If you need SSL, we can generate these:

```
$ sudo letsencrypt -d newdomain.clir.org
```

Choose if you want **Easy** (add TLS, but don't force all traffic) or
**Secure** (all traffice on TLS).

# TLS for Websites

TLS for websites is provided on server through [EFF Certbot](https://certbot.eff.org/)
(what drives the [Let's Encrypt project](https://letsencrypt.org/)).
The package is updated via `apt` on the server and included in
server self-updates.


