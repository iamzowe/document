# Integration Tutorial for WordPress

Welcome to the integration tutorial. In this section, we will show details how best to install the plugin.

> This tutorial applies to both `CPay Credit Card Payment Gateway` and `CPay Crypto Payment Gateway`


## Prerequisites
- WordPress (version 6.1.1+)
- WooCommerce Plugin
- Host, MerchantID and SecurityKey (from CPay)


## Installation
Before installing the plugin, please confirm whether to use plugin `CPay Crypto`, `CPay Credit Card`, or both.
- `CPay Credit Card` is for credit card payment => repository [CPay Credit Card](https://github.com/cpayfinance/cpay-credit-card-gateway-wp)
- `CPay Crypto` is for crypto payment => repository [CPay Crypto](https://github.com/cpayfinance/cpay-crypto-gateway-wp)

### By Git

1. Sign in the server of WorPress.

2. Enter directory of WordPress, by running command `cd /path/to/wordpress/wp-content/plugins/`.

3. Clone the repository from `GitHub`, by running command:
   - `git clone https://github.com/cpayfinance/cpay-credit-card-gateway-wp.git`
   - or `git clone https://github.com/cpayfinance/cpay-crypto-gateway-wp.git`

> See the figure below:  
> ![install-by-git](https://static.cpay.ltd/images/docs/install-by-git.png)


### or By Uploading

1. Download zip from the endpoint:
   - [https://github.com/cpayfinance/cpay-credit-card-gateway-wp/archive/refs/heads/main.zip](https://github.com/cpayfinance/cpay-credit-card-gateway-wp/archive/refs/heads/main.zip)
   - or [https://github.com/cpayfinance/cpay-crypto-gateway-wp/archive/refs/heads/main.zip](https://github.com/cpayfinance/cpay-crypto-gateway-wp/archive/refs/heads/main.zip)


2. Sign in administrator's dashboard of WordPress and upload the zip by following these steps:  
   go to `Plugins` => `Add New` => `Upload Plugin` => `Select Files` => `Install Now` => `Go to Plugin Installer`.

> See the figure below:  
> ![install-by-uploading](https://static.cpay.ltd/images/docs/install-by-uploading.png)


## Activation
1. Sign in administrator's dashboard of WordPress.

2. Activate it:  
   go to `Plugins` => `Installed Plugins` => `Inactive` => activate `CPay Crypto Payment Gateway`/`CPay Credit Card Payment Gateway`.
   

## Configuration
1. Sign in administrator's dashboard of WordPress.

2. Enable it:  
   go to `WooCommerce` => `Settings` => `Payments` => open `CPay Crypto Enabled`/`CPay Credit Card Enabled` => click `Save changes`.

> See the figure below:  
> ![enable-it](https://static.cpay.ltd/images/docs/enable-it.png)

3. Set configuration:  
   go to `WooCommerce` => `Settings` => `Payments` => `CPay Crypto`/`CPay Credit Card` => click `Manage` => click `Save changes`.

> See the figure below:  
> ![config-it](https://static.cpay.ltd/images/docs/config-it.png)
>> we will send the details of configuration to partner by email. The `CPay Host` lists [here](https://github.com/cpayfinance/document/blob/main/api-reference/api-host.md) too.

## Usage
After doing these steps above, users will be shown payment option of `CPay Crypto`/`CPay Credit Card` on the checkout page.

> See the figure below:  
> ![config-it](https://static.cpay.ltd/images/docs/checkout-page.png)

