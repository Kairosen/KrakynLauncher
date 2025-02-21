# Microsoft Authentication

Authenticating with Microsoft is fully supported by Krakyn Launcher.

## Acquiring an Entra Client ID

1. Navigate to https://portal.azure.com
2. In the search bar, search for **Microsoft Entra ID**.
3. In Microsoft Entra ID, go to **App Registrations** on the left pane (Under *Manage*).
4. Click **New Registration**.
    - Set **Name** to be your launcher's name.
    - Set **Supported account types** to *Accounts in any organizational directory (Any Microsoft Entra ID tenant - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox)*
    - Leave **Redirect URI** blank.
    - Register the application.
5. You should be on the application's management page. If not, Navigate back to **App Registrations**. Select the application you just registered.
	@@ -18,7 +18,7 @@ Authenticating with Microsoft is fully supported by Helios Launcher.
    - Select **Mobile and desktop applications**.
    - Choose `https://login.microsoftonline.com/common/oauth2/nativeclient` as the **Redirect URI**.
    - Select **Configure** to finish adding the platform.
8. Go to **Certificates & secrets**.
    - Select **Client secrets**.
    - Click **New client secret**.
    - Set a description.
	@@ -28,11 +28,11 @@ Authenticating with Microsoft is fully supported by Helios Launcher.
9. Copy **Application (client) ID**.


## Adding the Entra Client ID to Krakyn Launcher.

In `app/assets/js/ipcconstants.js` you'll find **`AZURE_CLIENT_ID`**. Set it to your application's id.

Note: Entra Client ID is NOT a secret value and **can** be stored in git. Reference: https://stackoverflow.com/questions/57306964/are-azure-active-directorys-tenantid-and-clientid-considered-secrets

Then relaunch your app, and login. You'll be greeted with an error message, because the app isn't whitelisted yet. Microsoft needs some activity on the app before whitelisting it. __Trying to log in before requesting whitelist is mandatory.__

	@@ -49,4 +49,4 @@ You can now authenticate with Microsoft through the launcher.

References:
- https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app
- https://help.minecraft.net/hc/en-us/articles/16254801392141