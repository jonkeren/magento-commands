Here are some Magento 2.x CLI commands I use once in a while. Using this as my personal notepad, so to speak; might be useful for someone.

### List all installed modules/extensions including version:
`n98-magerun2 dev:module:list`

### Magento 2 list all modules:
`php bin/magento module:status`

### Magento 2 set Varnish to flush with Magento FPC flush:
`php bin/magento setup:config:set --http-cache-hosts=127.0.0.1`

### Check on CLI if Varnish is flushed when clicking button in Admin:
`varnishlog -g request -q 'ReqMethod eq "PURGE"'`

### List Varnish URLs with most Cache Misses
This will create a list of the URLs that caused the most cache misses the last hour.
`varnishtop -p 3600 -i BereqURL`

### Magento 2 Disable captcha frontend + backend via cli
```
php bin/magento config:set customer/captcha/enable 0
php bin/magento config:set admin/captcha/enable 0
```

### Magento 2 change user passwd in phpmyadmin
`UPDATE admin_user SET password = SHA2('[passwd]', 256) WHERE username='[username]';`

### Magento 2 unlock admin user
`php bin/magento admin:user:unlock [username]`

### Magento 2 reindex
`php bin/magento indexer:reindex`

### Magento 2 clean cache
```
php bin/magento c:c
php bin/magento cache:flush
```

### Magento 2 make new admin user on cli
`php bin/magento admin:user:create --admin-user="USERNAME" --admin-password="PASS" --admin-email="EMAIL" --admin-firstname="FIRSTNAME" --admin-lastname="LASTNAME"`

### Magento 1 reindex all
```
cd [MAGENTO_ROOT]/shell/
php indexer.php --status  
php indexer.php --reindexall
```
### Magento 2 set base URL's
```
php bin/magento config:set --scope=website --scope-code=base -- web/unsecure/base_url "http://www.website.com/"
php bin/magento config:set --scope=website --scope-code=base -- web/secure/base_url "http://www.website.com/"
```

### magento 2 set base media URL
```
magerun2 config:store:set web/unsecure/base_media_url https://www.SITE.nl:8443/media/
magerun2 config:store:set web/secure/base_media_url https://www.SITE.nl:8443/media/
```

### Magento 2 set Admin session lifetime
```
php bin/magento config:set admin/security/session_lifetime 31536000
```

### Magento 2 find cacheable="false" blocks in templates
```
cd app/design/frontend/ && grep --recursive -l 'cacheable="false"' * && cd ../../..;
cd app/code && grep --recursive -l 'cacheable="false"' * && cd ../..;
cd vendor && grep --recursive -l 'cacheable="false"' * && cd ..;
```
