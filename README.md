# DigitalStartup_Csp
Content Security Policy Whitelist Module for Magento 2.3.5+. As described in the [Official Magento Documentation](https://devdocs.magento.com/guides/v2.3/extension-dev-guide/security/content-security-policies.html#report-uri-configuration).

## Before you use this module
* This project is not kept up-to-date and may contain mistakes. Treat this as a learning tool.
* This module is supported by the following Digital Startup Tutorial ([Removing Content Security Policy Errors](https://digitalstartup.co.uk/t/removing-content-security-policy-errors-magento-2-3-5-and-above/1554)) which will shed more light on its use.
* This module will not work unless you follow the instructions below

## How to use this module
Before you can use this module on your own Magento 2 store, you have to make changes to the following 2 files:

#### 1. config.xml
1. Add a URL for `report_uri` if you are reporting to another solution. (You probably aren't. This is optional so you can leave it blank)
2. Change `report_only` from `1` (report only) to `0` (restrict mode). (This is optional so change when you are happy that your whitelist is working correctly.)

#### 2. csp_whitelist.xml
This is a very generic starting point. You must both **Add** and **Remove** any URLs that are applicable to your own Magento 2 store. **Remember: This is a "firewall". Therefore, only creates rules for URLs that you have verified as safe**. Ensure that you use a unique "id" (e.g. the URL) for each entry within its group.

## Installation via FTP
1. Upload via FTP to `app/code/`
2. Enable Module: `bin/magento module:enable DigitalStartup_Csp`
3. Update Magento Schema: `bin/magento setup:upgrade`
3. Compile if in Production: `bin/magento setup:di:compile`
5. Clear Cache: `bin/magento cache:clean`
