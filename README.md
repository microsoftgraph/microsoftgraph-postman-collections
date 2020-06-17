# Microsoft Graph Postman Collections

The Microsoft Graph Postman Collections is a community contributed open source repo to provide both the collection and the environment variable files to import into Postman.

The collection allows you to test common Microsoft Graph APIs from within Postman. Support currently covers user delegated authorization flows for: Applications (beta), Batch, Events, Files, Groups, Insights, Mail, Notebooks, Extensions, People, Planner, Security, SharePoint, Subscriptions, Tasks, Teams and Users.

![Image of Postman](https://github.com/microsoftgraph/microsoftgraph-postman-collections/blob/master/images/postman.png?raw=true)

The most up-to-date experience to explore the APIs will always be [Microsoft Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer) in a web browser. This project has been created based on requests from the community. Remember the best place to understand the workings of these APIs is to read our [Microsoft Graph API documentation](https://docs.microsoft.com/en-us/graph/).

## Setup

[![Image of Postman](https://github.com/microsoftgraph/microsoftgraph-postman-collections/blob/master/images/video.png?raw=true)](https://www.youtube.com/watch?v=4tg-OBdv_8o)

To setup the Postman collections follow these steps:

**1.** Download and register for [Postman](https://www.getpostman.com/). Note: Make sure to install the latest version).

**2.** Click **File | Import ...**.

**3.** Select **Import From Link**.

**4.** Paste the following two URLs and click Import after each.

`https://raw.githubusercontent.com/microsoftgraph/microsoftgraph-postman-collections/master/Microsoft%20Graph.postman_collection.json`

`https://raw.githubusercontent.com/microsoftgraph/microsoftgraph-postman-collections/master/Microsoft%20Graph.postman_environment.json`

You should now see the **Microsoft Graph** collection on the left had side Collections pane.

**5.** Click on the **No environment** drop down in top right hand corner.

**6.** Select **Microsoft Graph environment**.

**7.** Click the **eye** icon to the the right and then click **Edit**.

**8.** Enter in to the **current** (not **initial**) variables your Microsoft Identity Application: **ClientID**, **ClientSecret** ad **TenantID**. 

For more information on how to create a Application and to admin consent the app-only flow please read the [30 days of graph blog post series](https://developer.microsoft.com/en-us/graph/blogs/30daysmsgraph-day-13-postman-to-make-microsoft-graph-calls/).

**9.** Select **Update**. Close the **Manage Environments** dialog. In the **MicrosoftGraph | Application** collection on left hand side. Click on the **Get App-only Access Token**. Then click **Send** button on right hand side.

**10.** Expand the **Application | Users** folder and click on **Get Users**. Then Click the **Send** button.

You are now up and running with Microsoft Graph collections.

**NOTE:** that if you wish to run other APIs in the collection, you will need to consent the required permissions for your application.

## Setting up on behalf of delegated access
The simplest way of doing this is providing a **UserName** and **UserPassword** in the environment settings and use **On Behalf of a User | Get User Access Token** instead. **IMPORTANT:** It is not recommended to use production user accounts as this information is stored directly in Postman. This is also not a recommended approach for obtaining access tokens in production and should only be used for testing purposes.

For those those that do not want to store user names and passwords in environment variables in postman that get synced to your postman cloud account. You can use the native Postman **Get New Access Token** capability to obtain a token without leaving postman.

**1.** Select **On behalf of a User | Get Access Token using Postman**.

**2.** Click on the Authorization tab (besides Params).

**3.** Click get access token button.

**4.** Fill out the following boxes with your real tenant and application values. Note that you cannot use the environment variables here, it has to be the actual values. These can be found by clicking **EndPoints** in the application blade in portal.azure.com.

- Callback URL: https://app.getpostman.com/oauth2/callback

- Auth URL: https://login.microsoftonline.com/**TENANTID**/oauth2/v2.0/authorize

- Access Token URL: https://login.microsoftonline.com/**TENANTID**/oauth2/v2.0/token

- Client ID: **CLIENTID**

- Client Secret: **CLIENTSECRET**

- Scope: https://graph.microsoft.com/.default

- State: **RANDOMSTRING**

 
**5.** Click Request Token and you should see a UI prompt to sign in and consent permissions.

**6.** Then take the entire Access Token and open up your environment variables and paste it into the UserAccessToken.

Now all your requests will work.

## Contribute

You can contribute to this project by forking the repo and following the setup steps to import those files. When you've made your contributions in Postman editor, use the *File | Export* to overwrite the file in your forked branch. Then simply submit the forked branch as a PR back to this repo.
