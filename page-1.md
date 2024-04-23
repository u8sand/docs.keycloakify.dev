---
description: Enable loading in the blink of an eye of login pages with --external-assets
---

# ⚡ Performance optimization

{% hint style="warning" %}
This only applies if your theme is integrated with a React app. &#x20;

If your Keycloak theme is a standalone react project you can ignore this section.&#x20;
{% endhint %}

By default when your users reach the login pages all scripts, images and stylesheet are downloaded from the Keycloak server.\
If you are specifically building a theme to integrate with an app or a website that allows users to browse unauthenticated before logging in, you will get a significant performance boost if you jump through those hoops:

* Provide the url of your app in the `homepage` field of package.json. [ex](https://github.com/garronej/keycloakify-demo-app/blob/7847cc70ef374ab26a6cc7953461cf25603e9a6d/package.json#L2) or in a `public/CNAME` file. [ex](https://github.com/garronej/keycloakify-demo-app/blob/main/public/CNAME).
* Build the theme using `npx build-keycloak-theme --external-assets` [ex](https://github.com/garronej/keycloakify-demo-app/blob/7847cc70ef374ab26a6cc7953461cf25603e9a6d/.github/workflows/ci.yaml#L21)
* Enable [long-term assets caching](https://create-react-app.dev/docs/production-build/#static-file-caching) on the server hosting your app. [This is how you would do it with Ngnix](https://github.com/garronej/keycloakify-demo-app/blob/f08e02e1bd0c67b3cc8d49c03d4dd6d7916f457b/nginx.conf#L17-L29).
* Make sure not to build your app and the keycloak theme separately (run `yarn keycloak` only once in your CI) and remember to update the Keycloak theme every time you update your app.
* Be mindful that if your app is down your login pages are down as well.

Checkout a complete setup [here](https://github.com/garronej/keycloakify-demo-app#about-keycloakify)
