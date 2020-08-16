# How to use

## Spotify for Developers

* Create a [Spotify for Developers](https://developer.spotify.com/dashboard/applications) account
* Get Credentials
    * `Client ID`
    * `Client Secret`
* Go to **Edit Settings**
* Find **Redirect URIs**:
    * Add `http://localhost/callback/`

## Get the Refresh Token from spotify

* Navigate to the following URL:
  <br/>
  **Note**: copy your Client ID and paste in **{SPOTIFY_CLIENT_ID}** below.

```
https://accounts.spotify.com/authorize?client_id={PUT_YOUR_SPOTIFY_CLIENT_ID_HERE}&response_type=code&scope=user-read-currently-playing,user-read-recently-played&redirect_uri=http://localhost/callback/
```

* After logging in, get the {GET_THE_TOKEN} portion of: `http://localhost/callback/?code={GET_THE_TOKEN}`

* Create a string combining `{SPOTIFY_CLIENT_ID}:{SPOTIFY_CLIENT_SECRET}` (e.g. `5n7o4v5a3t7o5r2e3m1:5a8n7d3r4e2w5n8o2v3a7c5`) and encode into [Base64](https://www.base64encode.org/).

* Then run a [curl command](https://reqbin.com/curl):
```sh
curl -X POST -H "Content-Type: application/x-www-form-urlencoded" -H "Authorization: Basic {YOUR_BASE64}" -d "grant_type=authorization_code&redirect_uri=http://localhost/callback/&code={YOUR_TOKEN}" https://accounts.spotify.com/api/token
```

* Then save the Refresh token

## Configure Vercel Application
* Fork this [Spotify Status](https://github.com/sndrjhlncgr/Spotify-Status)

* Register on [Vercel](https://vercel.com/)

* Create project linked to your forked respository
  
  ![Vercel](https://i.ibb.co/sHhywHD/dasddas.jpg)

* Add Project Name and Environment Variables:
  - `SPOTIFY_REFRESH_TOKEN`
  - `SPOTIFY_CLIENT_ID`
  - `SPOTIFY_SECRET_ID`
  - `SPOTIFY_BAR_COLOR` 
     - `Hex Color Don't Include #`
        
  ![Vercel](https://i.ibb.co/vv5z4yP/Untitled.png)
  
 * DEPLOY!
