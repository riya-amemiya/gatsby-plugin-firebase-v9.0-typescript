# gatsby-plugin-firebase-v9.0-typescript

Gatsby add Firebase JS SDK 9

## Installation

use npm:

```bash
npm install firebase gatsby-plugin-firebase-v9.0 --save
```

or use yarn:

```bash
yarn add firebase gatsby-plugin-firebase-v9.0 -D
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
import React, { useEffect, useState } from 'react'
import app from 'gatsby-plugin-firebase-v9.0'
import { getDatabase, ref, onValue } from 'firebase/database'

const Component = ({ postID }) => {
  const [dataVaule, setValue] = useState('')
  useEffect(() => {
    const database = getDatabase(app)
    const dataRef = ref(db, 'data/' + postID + '/dataValue')
    onValue(dataRef, snapshot => {
      const data = snapshot.val()
      setValue(data)
    })
  }, [postID])
  return
  ;<div>{dataVaule ? dataVaule : ``}</div>
}

export default Component
```

For more usages, please refer to the [Firebase documentation](https://firebase.google.com/docs).

### License

MIT
