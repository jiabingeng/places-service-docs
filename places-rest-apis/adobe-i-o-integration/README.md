# Adobe I/O integration

## User access

Verify with your organization's System administrator that the following items have been completed:

1. Places Core Service appears in your organization's admin console. 
2. You have been added to the organization. 
3. You have been added as a User and as a Developer to Places Core Service in your organization.

   For more information, see [Adding a user to Launch and Places](https://github.com/jiabingeng/places-service-docs/tree/e47316971909cd6d031393b5c11ca1ac058263f4/adding-a-user-to-launch-and-places/README.md).

## Adobe I/O Integration for Location Services

Each request to the Places REST API requires the following items:

* An organization ID
* An API key
* A bearer token

An integration with Adobe I/O provides these items and a way to request the bearer token by using a JSON Web Token \(JWT\).

### Create a Places integration

#### Generate a public and private key pair

To create a Places integration, you need a public and a private key pair. These pairs can be purchased, or you can generate your own self-signed keys.

To generate your own self-signed keys:

1. Open a terminal window and navigate to your user folder.
2. In a terminal window, copy and paste each of the following lines and press **Enter** after pasting each line:

   ```text
      mkdir keys
      cd keys
      openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout places_integration_test_private.key -out    places_integration_test_public.crt
   ```

   **Tip**: We recommend that you name your keys for easy reference and store them in a folder. If you create multiple integrations, you can easily identify and manage which keys belong to which integration.

3. Type the information that is requested by OpenSSL:

   ```text
   Country Name (2 letter code:  // Example: US
   State or Province Name (full name):  // Example: California
   Locality Name (eg, city):  // Example: San Jose
   Organization Name (eg, company):  // Example: Adobe
   Organizational Unit Name (eg, section):  // Example: Engineering
   Common Name (eg, fully qualified host name):  // Example: adobe.com
   Email Address:  // Example:  joe.poi@adobe.com
   ```

   For more information about OpenSSL, see [OpenSSL](https://www.openssl.org/).   
   **Important**: The information that you provide is incorporated into the keys.

4. Navigate to the directory where the `.key` and `.crt` files are located. For example, on macOS, go to **Macintosh HD** &gt; **users** &gt; \(**your user name**\) &gt; **keys**.

The following video guides you through the process of generating the key pair:

![](../../.gitbook/assets/places_integration_video.gif)

#### Create a Places integration in the Adobe I/O console

To create a Places integration:

1. Go to [https://console.adobe.io/](https://console.adobe.io/) and sign in with your Adobe ID.
2. In the **Quick Start** section, click **Create integration**.
3. Select **Access an API** \(default selection\) and click **Continue**.
4. If you have access to more than one Experience Cloud organization, select the organization from the drop-down list on the top right.
5. Under **Experience Cloud**, select **Places** as the Adobe service to which you want to integrate with and click **Continue** near the bottom of the page.
6. Select **New integration** and click **Continue**.
7. On the _Create a new integration_ screen, enter a name and description.
8. Drag and drop your `xxxx_public.crt` file, created above, to the **Public keys certificates** drop zone.
9. Select a product profile. If you are unsure of which profile to select, contact your system administrator.
10. At the bottom of the page, click **Create integration**.
11. After a few seconds, in the _Integration created_ screen, verify that the following message appears:

    `Your integration has been created.`

12. Click **Continue to integration details**.
13. The integration details page appears with the name of the integration at the top.  The **Overview** tab is shown by default and displays the API key, your organization ID, the technical account ID, and other details about your integrations.

#### Record the organization ID and the API key

1. On the integration details page, click the **Services** tab and confirm that **Places** is displayed under **Configured Services**.
2. On the **Overview** tab, locate and record the API Key \(Client ID\) and the Organization ID.

   These IDs will be needed for each Places Rest API request.

![](../../.gitbook/assets/places_orgid_api-key.png)

#### Generate a JWT token

On the integration details page, click the **JWT** tab so that you can test your integration by generating a JWT and providing the exchange URL.

To generate a JWT token:

1. In a text editor, open your `private.key` file that you created above.
2. On the **JWT** tab, copy the contents of the key and paste it in the **Paste private key** field. 
3. Click **Generate JWT**.
4. In the **Sample CURL command** section, click **Copy** and paste the contents in your command prompt or terminal window.
5. Run the command by pressing **Enter** on your keyboard.
6. Locate the `"token_type": "bearer"` and the `"access_token"` value.    The value of the bearer access token is what you will use in your Places API requests.  

**Important**: Adobe access tokens are valid **only** for 24 hours, so save the sample CURL command \(step 5\). If the access token is no longer valid, you need to regenerate the token.

## Additional resources

* For more information about JWTs, see [Introduction to JSON Web Tokens](https://jwt.io/introduction/).
* To understand API key integration, generating a JWT, and public key certificates, see [Adobe I/O Authentication Overview](https://www.adobe.io/apis/cloudplatform/console/authentication/gettingstarted.html).

**Important:** If you cannot log in to the Adobe I/O console, or if Places is not an option in the _Create Integrations_ screen in the Adobe I/O console, confirm the user access steps at the beginning of this page have been completed.

