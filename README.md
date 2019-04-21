# Azure AD B2C (Example)

If you get this error. You can parse the uri manually.

![](https://raw.githubusercontent.com/marlonsingleton/manualRedirectUrlParse/master/bad_redirect_uri.jpg)
<br>
<br>

### Here's The Fix! ###

Open your browser's Developer Tools and review the body class="error" for output similar to below 

<script type="text/javascript">fs.config</br>
({"failureRedirect":"http://www.linkedin.com/",
"uniEscape":true,"xhrHeaders":</br>
{"X-FS-Origin-Request":</br>
"/oauth/v2/authorization?client_id=866usx44p4m5sf&</br> 
<b>redirect_uri=https%3a%2f%2flogin.microsoftonline.com%2fte%2fmarlonb2c.onmicrosoft.com%2foauth2%2fauthresp</b></br>
&response_type=code&scope=r_emailaddress+r_liteprofile&state=StateProperties%3deyJTSUQiOiJ4LW1zLWNwaW0tcmM6MTUwNmUwZDEtN2NiOC00M2MwLWJkNWQtMGMwMmVjMTU0NWZkIiwiVElEIjoiNzBkODEyNWEtNzM2NC00YTA1LTg3MjctYmYwODg4ODRlMDRhIn0",
"X-FS-Page-Id":"oauth-authorization"}});</script>
<br>
<br>

### Parse the Highlighted Portion ###

"%3A" is URL Encoding for ":"</br>
"%2f"  is URL Encoding for "/"


The link should now resemble something like this <b><a>https://login.microsoftonline.com/te/marlonb2c.onmicrosoft.com/oauth2/authresp</a></b> 
(Sorry, access to my link has expired, but yours should work just fine.)




<a href="https://www.w3schools.com/tags/ref_urlencode.asp">HTML URL Encoding Reference</a>

