# electron-twitter-oauth

Authenticate your user with OAuth on Twitter in your Electron.js application. It will open a new `BrowserWindow` on Twitter authentication page, ask to authenticate then send you back the `access tokens` in the callback.

Note: This code is extracted and adapted to be reused from the Twitter auth part of the awesome [surfbirdapp/surfbird](https://github.com/surfbirdapp/surfbird) application.

## Usage

``` bash
npm add --save electron-twitter-oauth
# or
yarn add electron-twitter-oauth
```

Then create a new Twitter application on [https://apps.twitter.com/app/new](https://apps.twitter.com/app/new) and get the `Consumer Key` and `Consumer Secret` to be used as shown below.


``` js
import {TwitterOAuth} from 'electron-twitter-oauth';

const twitterAuthWindow = new TwitterOAuth({
  callbackURL,
  consumerKey,
  consumerSecret
});

twitterAuthWindow.authenticate((err, token) => {
  if (err) {
    return console.log(err, err.stack);
  }

  console.log('Got the token data', token.accessTokenKey, token.accessTokenSecret, token.id_str);
});
```

## License

MIT Copyright (c) 2017 Christophe Hamerling <christophe.hamerling@gmail.com>
