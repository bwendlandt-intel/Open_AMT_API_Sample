# Resources for the Open AMT Cloud Toolkit Workshop

This repository contains any extra resources needed to participate in the Open AMT Cloud Toolkit Workshop.

Key Files Included:
- RPC Binary/Executable
    - These binaries are for testing purposes and other non-production uses. Instructions on compiling these binaries yourself can be found [here](https://open-amt-cloud-toolkit.github.io/docs/1.3/General/buildRPC/).
- sample_blank.htm File for Demonstrating APIs

In this workshop, we will demo APIs using the *sample_blank.htm* example template. For basic examples on constructing API calls using other tools or technologies, see below.

<br>

## Other REST API Call Examples

### Node.js

View our [REST API Call tutorial](https://open-amt-cloud-toolkit.github.io/docs/1.3/Tutorials/apiTutorial/). Includes a walkthrough and example code for how to get an Authorization Token and then make a call to get all devices of the MPS server.

<br>

### cURL

Find additional information on curl in [their documentation](https://curl.se/docs/manpage.html).

Example Authorize
```
curl -k -X POST -H "Content-Type: application/json" -d "{\"username\": \"standalone\", \"password\": \"G@ppm0ym\"}" https://localhost/mps/login/api/v1/authorize
```

Example Get Devices
```
curl -k -H "Authorization: Bearer <Your-JWT-Token>" -X GET https://localhost/mps/api/v1/devices
```

<br>

### Postman

The following steps will show how to construct the Authorize API call via Postman:

1. Select New in the top-left corner or 'Create a Request' via the Launchpad.

2. Change 'Get' to 'Post' via the drop-down.

3. Enter the [Authorize API URL](https://app.swaggerhub.com/apis-docs/rbheopenamt/mps/1.3.0#/Auth/post_api_v1_authorize).

    ```
    https://localhost/mps/login/api/v1/authorize
    ```

4. In the 'Body' tab, select 'raw' and then 'JSON' from the drop down.

5. Provide the body according to Authorize API docs.

    ```
    {
        "username": "standalone",
        "password": "G@ppm0ym"
    }
    ```

6. Click Send.

    Example Input

    ![input](./assets/postman_auth_input.PNG)

    Example Output

    ![input](./assets/postman_auth_output.PNG)

    **Troubleshooting Note:** If there is an authorization error, ensure SSL certificate verification is set to **OFF** in the Settings menu.