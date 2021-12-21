# Shopify Local

A testing and example project set up for local Shopify theme development. This aims to serve as some loose instructions and as an example for your own local Shopify local theme setup.

## Commands

This project uses gulp to handle start the theme-kit watch along with building the scss.

- ```npm install```
- ```gulp watch```

## Lighthouse CI Github Action

> https://shopify.dev/themes/tools/lighthouse-ci

This repo uses the lighthouse ci github action to run automatic performance and accessibility tests on push.

To get this setup you need to create a custom app in your Shopify dashboard and then store the API key and a few other variables in your github secrets page. You will need these: app_id, app_password, store, password and lhci_github_app_token. Find out more about this with the link above.

The performance and accessiblitly pass metrics can be edited in the ```./.github/workflows/lighthouse-ci.yml``` file. They are the key values to edit are both ```lhci_min_score_performance``` and ```lhci_min_score_accessibility```. 


## How to build this from scratch!

- Create a Shopify account - if this is soley for development you can create one using partners.shopify.com.
- Add the base theme you would like to use.
- Go to the Shopify Apps tab and install and setup the app: https://apps.shopify.com/theme-kit-access. This will allow you to manage credentials for multiple developers for using theme kit with your Shopify.
- Create a new project directory that you would like to work from. 
- Install theme kit here: https://shopify.dev/themes/tools/theme-kit/getting-started#macos.
- Once install run ```theme get --list --password=[your-password] --store="[your-store.myshopify.com]"``` to get the list of all themes install on Shopify instance.
- Grab the ID of the theme you want to work on, cd into your new project directory that you created earlier and run ```theme get --password=[your-password] --store="[your-store.myshopify.com]" --themeid=[your-theme-id]``` where the theme ID is listed from the previouse command.
- If you dont want to use gulp you can run ```theme watch --allow-live```. This will monitor the directory and automatically update the Shopify live theme with any changes.

> If you want to set up the project with Gulp (like this one). Refer to the gulpfile.js in this repo. We use the ```@shopify/themekit``` repo to use theme-kit in node.