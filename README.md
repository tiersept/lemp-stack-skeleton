# lemp-stack-skeleton
Roots based Wordpress skeleton

Filled with all the goodness to get yoself started locally and easy remote deploys.

## Versions

- ansible 2.2.1.0
- vagrant 1.9.7
- composer 1.6.3

## WP Plugin list
* roots/soil
* wpackagist-plugin/unique-headers
* wpackagist-plugin/post-types-order
* wpackagist-plugin/wp-smushit
* sybrew/the-seo-framework
* wpackagist-plugin/the-seo-framework-extension-manager
* wpackagist-plugin/svg-support
* wpackagist-plugin/contact-form-7
* wpackagist-plugin/advanced-custom-fields
* wpackagist-plugin/acf-theme-code
* wpackagist-plugin/custom-post-type-ui

## Setup Config files

Setup config files in trellis/group_vars/development/

### dir/group_vars
* /all/users   -> add user github ssh key

### dir/development
* /vault      -> generate passwords
* /sites      -> change name to PROJECTNAME.dev

### dir/production
* /vault      -> generate passwords & salt
* /sites      -> set site name, droplet ip & git repo //https://roots.io/salts.html

## Run Dev environment

Run in local /trellis

```
ansible-galaxy install -r requirements.yml
```

To run VM

```
vagrant up
```

In /site/web/app/themes/website.com/assets/manifest.json .  
Change to website name used in /development/sites

```
  "config": {
    "devUrl": "http://skeleton.dev"
  }
```

In /site/web/app/themes/website.com

```
npm install
bower install

gulp
gulp watch
gulp production
```
