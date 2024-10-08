Simple and hacky project that will automatically like all songs in all of the liked albums in your Spotify profile.

A couple things that will be needed. You will currently have to generate your own Spotify application at https://developer.spotify.com/

You will need a folder in your home directory named `.spotify-song-liker` with a file inside of this folder named `application.properties`

In this file you will initially need the following:

`com.dwdking.spotify.credentials.clientId=<your generated client id>`
`com.dwdking.spotify.credentials.clientSecret=<your generated client secret>`

The client id and client secret will be the values from your generated application registered at developer.spotify.com

Once this is done running `./gradlew bootRun` (best in Git Bash) will launch the app authorization page and allow you to authorize the app against your Spotify account.

Upon an error on the authorization page, try replacing its URL with the following:
https://accounts.spotify.com/authorize?client_id=1967637946eb445aa9f8fc530f741af1&redirect_uri=http://localhost:8080/spotifyCallback&response_type=code&scope=user-library-read+user-library-modify
For the list of scopes, see ApplicationStartup.java

Once it has been authorized an authorization code, access token, and refresh token will be stored to the application.properties file automatically.

You can then hit the endpoint http://localhost:8080/likeAllAlbumSongs, which will like all songs from all the albums you have already liked.

Goodluck!
