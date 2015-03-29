# Block referrer spam websites on NGINX

CONF file that can be included in the nginx conf and block referrer spam websites.

## How to implement it
1. In your nginx folder (I have mine in `/etc/nginx/`) create a folder `globals` if it doesn't exists already. Copy the `referrer-spam.conf` there.
2. In your `sites-available` folder (for me it's in `/etc/nginx/sites-available/` open the configuration of the site and into `server` block add this line: `include global/referrer-spam.conf;`, note that it shouldn't be an absolute path, and you don't need to add `../` at the begining! :)
3. Restart nginx: `service nginx restart`
4. 

## Testing
Wanna test if this really works. Do it with this command:
```
curl --referer <referrer_website> <your_website>
curl --referer http://buttons-for-website.com http://www.rokson.co
```

## Contribution
Anyone is more than welcome to add new referrer spam websites to this list. The only thing I'd like you to do when making a PR is to not make this code any more wider, keep it within the current width if you add any more domains.

Thank you! :)
