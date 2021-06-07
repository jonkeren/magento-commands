Here are some Magento 2.x CLI commands I use once in a while. Using this as my personal notepad, so to speak; might be useful for someone.

### List all installed modules/extensions including version:
`n98-magerun2 dev:module:list`

### Magento 2 list all modules:
`php bin/magento module:status`

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
`php bin/magento admin:user:create --admin-user="[username]" --admin-password="[pass]" --admin-email="[email]" --admin-firstname="[firstname]" --admin-lastname="[lastname]`

### Magento 1 reindex all
```
cd [MAGENTO_ROOT]/shell/
php indexer.php --status  
php indexer.php --reindexall
```




