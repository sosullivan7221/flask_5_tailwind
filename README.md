# flask_5_tailwind
Deploying flask app with video stored on a CDN, formatted with tailwind. Created using Microsoft Azure.

## App

The app contains a video of a cat meowing. This video was obtained from a YouTube video. Here is the link to the deployed app: https://flasktailwind.azurewebsites.net/

##  CDN Config

1. Create a storage account on Microsoft Azure.
2. Create a container within the storage account, and place your video file within it.
3. Create an Azure CDN within the storage account. It will provide you with an endpoint, which will be used to access the storage account.
4. Attach the endpoint of the video to the end of the CDN endpoint (this is the part of the video url after the .net)
5. Place the new endpoint url within your html file as the source for your video tag. Format the tag to fit your web app.

## Azure Deployment

1. Install Azure CLI into your IDE 
2. Login into Azure using az login --use-device-code
3. Create a resource group inside of your Azure account which will be used to create the Web App
4. Create the web app using az webapp up --resource-group (groupname) --name (app-name) --runtime (PYTHON:3.9) --sku (B1), replacing bracketed terms with the corresponding resource group, app name, python version, and sku 
5. Use the link provided on the App Service page to open your web page. Use the log stream to troubleshoot if you have an app failure.

## Notes

-Looking at the screenshots, it seems that the CDN usage significantly reduced the loading time of the video. The screenshots look different from the final app, as they were taken before the formatting was changed. However, the content is still the same. The screenshots were taken from the local deployment of the Flask app, however, we can still expect to see a similar difference in response times on the deployed version of the app.
