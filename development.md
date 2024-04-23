---
description: Test and debug your theme
---

# 🧪 Development

### Seeing the results live

When building your page you want to see the results of your edits live.

To achieve that with Keycloakify simply edit:

```diff
 import { getKcContext } from "keycloakify";

 const { kcContext } = getKcContext({
+    "mockPageId": "login.ftl"
 });
```

[See the `getKcContext()` call in the `keycloakify-demo-app` project](https://github.com/garronej/keycloakify-demo-app/blob/6a78e1b6513cffa44b1f0e6f8a36d263a39b972b/src/index.tsx#L18-L19).

[See the getKcContext() call in the `keycloakify-demo-app#look_and_feel` project](https://github.com/garronej/keycloakify-demo-app/blob/f8b2ac1734c826646fc0c97e1c4633ae392e72c6/src/KcApp/kcContext.ts#L22-L23).

then if you run `yarn start` you will see your login page display. **Don't forget to remove mockPageId before releasing** 😉.

{% hint style="success" %}
The page is loaded with a default mock context.

To customize the mock kcContext please refer to [this example](https://github.com/garronej/keycloakify-demo-app/blob/a316ea0046976e6d435a33e896cb9e3d1873c124/src/KcApp/kcContext.ts#L28-L78).
{% endhint %}

### Testing in a real Keycloak instance

Once you are done developing you want to test in an actual Keycloak instance to see if everything is working as expected.

Please refer to the instructions printed on the console when running `yarn keycloak` in your project. &#x20;

{% embed url="https://user-images.githubusercontent.com/6702424/176266833-61b9c734-b16f-4822-9409-374bf9a387e0.mp4" %}
The instructions for starting a test container are displayed when you build the theme.
{% endembed %}
