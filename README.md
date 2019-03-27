# Microsoft Graph Postman Collections

The Microsoft Graph Postman Collections is a community contributed open source repo to provide both the collection and the environment variable files to import into Postman.

The collection allows you to test common Microsoft Graph APIs from within Postman. 

The most up-to-date experience to explore the APIs will always be Microsoft Graph Explorer in a web browser. This project has been created based on requests from the community.

## Setup

To setup the Postman collections follow these steps:

1. Download and register for [Postman](https://www.getpostman.com/).

2. Click *File | Import ...*.

3. Select "Import From Link".

4. Paste the following two URLs and click Import after each.

    - `https://raw.githubusercontent.com/microsoftgraph/microsoftgraph-postman-collections/master/Microsoft%20Graph%20v1.0.postman_collection.json`

    - `https://raw.githubusercontent.com/microsoftgraph/microsoftgraph-postman-collections/master/Microsoft%20Graph%20v1.0.postman_environment.json`

You should now see the *Microsoft Graph v1.0* collection on the left had side Collections pane.

5. Click on the *No environment* drop down in top right hand corner.

6. Select *Microsoft Graph environment*.

7. Click the *eye* icon to the the right and then click *Edit*.

8. Enter your Microsoft Identity Application: **ClientID**, **ClientSecret** ad **TenantID**. (The *AccessToken* is not required at this time).

9. In the *MicrosoftGraph v1.0* collection on left hand side. Click on the **Get App-only Access Token**. Then click **Send** button on right hand side.

10. Expand the *Users* folder and click on *Get Users*. Then Click the **Send** button.

You are now up and running with Microsoft Graph v1.0 collections. NOTE: that if you wish to run other APIs in the collection, you will need to consent the required permissions for your application.

## Contribute

You can contribute to this project by forking the repo and following the setup steps to import those files. When you've made your contributions in Postman editor, use the *File | Export* to overwrite the file in your forked branch. Then simply submit the forked branch as a PR back to this repo.