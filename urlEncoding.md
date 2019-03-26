### While testing Azure's AD B2C... ###

I got this error.

![](https://raw.githubusercontent.com/marlonsingleton/manualRedirectUrlParse/master/bad_redirect_uri.jpg)


Since I was using a local app via Visual Studio, I thought other might run into this as well.<br>
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

### Let's Parse the Highlighted Portion ###

"%3A" is URL Encoding for ":"</br>
"%2f"  is URL Encoding for "/"


So, the redirect_uri here is <b><a>https://login.microsoftonline.com/te/marlonb2c.onmicrosoft.com/oauth2/authresp</a></b> 
(My redirect_uri is no longer valid, just in case you were wondering.)




<a href="https://www.w3schools.com/tags/ref_urlencode.asp">HTML URL Encoding Reference</a>
