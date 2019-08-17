A custom module for [astrodistribution.com](https://www.astrodistribution.com).

## How to install
```
bin/magento maintenance:enable
rm -rf composer.lock
composer clear-cache
composer require astrodistribution/core:*
bin/magento setup:upgrade
rm -rf var/di var/generation generated/code
bin/magento setup:di:compile
rm -rf pub/static/*
bin/magento setup:static-content:deploy \
	--area adminhtml \
	--theme Magento/backend \
	-f en_US en_GB
bin/magento setup:static-content:deploy \
	--area frontend \
	--theme Smartwave/porto \
	-f en_US en_GB
bin/magento maintenance:disable
bin/magento cache:enable
```

## How to upgrade
```
bin/magento maintenance:enable
composer remove astrodistribution/core
rm -rf composer.lock
composer clear-cache
composer require astrodistribution/core:*
bin/magento setup:upgrade
rm -rf var/di var/generation generated/code
bin/magento setup:di:compile
rm -rf pub/static/*
bin/magento setup:static-content:deploy \
	--area adminhtml \
	--theme Magento/backend \
	-f en_US en_GB
bin/magento setup:static-content:deploy \
	--area frontend \
	--theme Smartwave/porto \
	-f en_US en_GB
bin/magento maintenance:disable
bin/magento cache:enable
```

If you have problems with these commands, please check the [detailed instruction](https://mage2.pro/t/263).