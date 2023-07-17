---
tags: [OAuth2.0, Api]
---
The higlighted fields need to be filledup for successful Postman setup.   
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/Postman-page1.png)  
Img 1  
   
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/Postman-page2.png)  
Img 2  
```
Callback URL: https://oauth.pstmn.io/v1/callback  
Auth URL: https://accounts.google.com/o/oauth2/v2/auth
Access Token URL: https://oauth2.googleapis.com/token  
Client ID: This is OAuth2 client ID from Google Cloud Console  
Client Secret: OAuth2 client secret  
Scope: https://www.googleapis.com/auth/calendar (For Google Calendar. All Google Api scopes can be found here 
```  
Google Api scopes: [https://developers.google.com/identity/protocols/oauth2/scopes](https://developers.google.com/identity/protocols/oauth2/scopes)  
### In [Google Console](https://console.cloud.google.com), there is a 3 step process:  
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/google-console.png)  
Img 3
  
Step 1: Create OAuth2 credentials  
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/OAuth2-credentials.png)  
Step 2: Enable API, for example: Google Docs 
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/Enable+Api.png)   
Step 3: Add Scope to OAuth Consent Screen  
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/Add+Scope.png)  