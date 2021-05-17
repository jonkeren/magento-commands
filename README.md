Here are some Magento 2.x CLI commands I use once in a while. Using this as my personal notepad, so to speak; might be useful for someone.

### List all installed modules/extensions including version:
`n98-magerun2 dev:module:list`

### Disable captcha frontend + backend via cli
```php bin/magento config:set customer/captcha/enable 0
php bin/magento config:set admin/captcha/enable 0```

