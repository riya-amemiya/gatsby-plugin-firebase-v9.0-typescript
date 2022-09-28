# gatsby-plugin-firebase-v9.0-typescript

Gatsby add Firebase JS SDK 9

## Installation

use npm:

```bash
npm install firebase gatsby-plugin-firebase-v9.0-typescript --save
```

or use yarn:

```bash
yarn add firebase gatsby-plugin-firebase-v9.0-typescript -D
```

## Usage

### Register gatsby plugin

In `gatsby-config.js`:

```javascript
module.exports = {
  plugins: [
    ...otherPlugins,
    {
      resolve: 'gatsby-plugin-firebase-v9.0-typescript',
      options: {
        credentials: {
          apiKey: '<YOUR_FIREBASE_API_KEY>',
          authDomain: '<YOUR_FIREBASE_AUTH_DOMAIN>',
          databaseURL: '<YOUR_FIREBASE_DATABASE_URL>',
          projectId: '<YOUR_FIREBASE_PROJECT_ID>',
          storageBucket: '<YOUR_FIREBASE_STORAGE_BUCKET>',
          messagingSenderId: '<YOUR_FIREBASE_MESSAGING_SENDER_ID>',
          appId: '<YOUR_FIREBASE_APP_ID>',
          measurementId: '<YOUR_FIREBASE_MEASUREMENT_ID>'
        }
      }
    }
  ]
}
```

### Use Firebase

Use Firebase like how you would use in a React project.

```javascript
import app from 'gatsby-plugin-firebase-v9.0-typescript'
import {getAuth} from 'firebase/auth'
import {getStorage} from 'firebase/storage'
const auth = getAuth(app)
const storage = getStorage(app)
```

For more usages, please refer to the [Firebase documentation](https://firebase.google.com/docs).

### License

Unlicense
