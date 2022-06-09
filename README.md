# VSF API 1.x Integration Mollie (Magento 2)
Vue Storefront API extension for Magento 2 and Mollie payment provider

# Purpose
Due to inactivity of https://github.com/Lakefields/vsf-payment-service-api this integration does neither support VSF 1.12 nor Magento 2 Mollie Module > 2.x.

This VSF API extension connects VSF 1.12.x with the 2.x Mollie Magento 2 Module.

# Prerequisites
- Magento 2.4.x (https://github.com/magento/magento2)
- Mollie Magento Module 2.x (https://github.com/mollie/magento2)
- VSF API 1.12.x (https://github.com/vuestorefront/vue-storefront-api)
- VSF 1.12.x (https://github.com/vuestorefront/vue-storefront-1)

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
    "get_order_url": "/V1/mollie/get-order/{{hash}}"
  }   
}

```
# Configure the Mollie Magento 2 Module
Under **Stores > Settings > Configuration > Mollie > Advanced** please configure your PWA integration URL.
![image](https://user-images.githubusercontent.com/32599710/172823392-2b3cc15e-e2ad-40d3-9941-ba3b80be2165.png)

Enable "Use webhooks" to use your custom webhook url **{{your_vsf_base_url}}/api/ext/vsf-magento-mollie-payment-api/webhook**.
![image](https://user-images.githubusercontent.com/32599710/172822765-5436afe6-abb0-4b33-b6c2-296e7b930553.png)

# Support
This extension is built to support the Mollie Payment Service for Vue Storefront 1.x.
Use at your own responsibility in your project. This extension is tested on Vue Storefront API 1.12.5.
If you need any assistance or want to do feature requests you can create an issue in this Github repository.

# License
Inspired by https://github.com/Lakefields/vsf-payment-service-api

This extension is completely free and released under the MIT License.
