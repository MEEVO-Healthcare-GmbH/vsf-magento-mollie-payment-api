# VSF API 1.x Integration Mollie (Magento 2)
Vue Storefront API extension for Magento 2 and Mollie payment provider

# Purpose
This VSF API extension connects the VSF 1.x Frontend with the Mollie Magento 2 Module.

# Prerequisites
- Magento 2.4.x (https://github.com/magento/magento2)
- Mollie Magento Module (https://github.com/mollie/magento2)
- VSF API (https://github.com/vuestorefront/vue-storefront-api)
- VSF 1.x (https://github.com/vuestorefront/vue-storefront-1)

# Installation Guide
Follow these steps to install this API extenstion to the Vue Storefront API. 

**Requirements for Vue Storefront API**

Clone this git repository from within your vue-storefront-api root folder

```shell
git clone git@github.com:MEEVO-Healthcare-GmbH/vsf-magento-mollie-payment-api.git src/api/extensions/vsf-magento-mollie-payment-api
```

**Run yarn to install dependencies**

# Register the Vue Storefront API extension
Add the API extension to the registered extensions to `local/config.json`

```
...
"registeredExtensions": [
  ...,
  "vsf-magento-mollie-payment-api"
]
```

1. Add the config properties to `local/config.json`

```
...
"extensions": {
  ...
  "mollie": {
    "payment_token_guest_url": "/V1/guest-carts/{{cartId}}/mollie/payment-token",
    "payment_token_mine_url": "/V1/carts/mine/mollie/payment-token",
    "transaction_start_url": "/V1/mollie/transaction/start",
    "secret": "__SECRET_CHANGE_ME__"
  }   
}

```
# Configure the Mollie Magento 2 Module
Under **Stores > Settings > Configuration > Mollie > Advanced** please configure your PWA integration URL and enable "Use webhooks" to use your custom webhook url **{{your_vsf_base_url}}/api/ext/vsf-magento-mollie-payment-api/webhook**.

# Support
This extension is built to support the Mollie Payment Service for Vue Storefront 1.x.
Use at your own responsibility in your project. This extension is tested on Vue Storefront API 1.12.5.
If you need any assistance or want to do feature requests you can create an issue in this Github repository.

# License
This extension is completely free and released under the MIT License.
