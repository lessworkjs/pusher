# lesswork-pusher
This is a pusher provider for the `lesswork-framework`.

# Installation
```bash 
npm i --save lesswork-pusher
```

Register the provider and alias in your `config/app.js` file.

```js
const providers = [
  ...
  'lesswork-pusher/Providers/PusherProvider',
];

const aliases = {
  ...
  Pusher: 'Lesswork/Pusher',
};
```

Create `config/pusher.js`
```js
module.exports = {
  appId: env('PUSHER_APP_ID'),
  key: env('PUSHER_APP_KEY'),
  secret: env('PUSHER_APP_SECRET'),
  cluster: env('PUSHER_APP_CLUSTER')
};
```

Define the `env` settings above in your `env.js`
```js
const env = {
  ...
  PUSHER_APP_ID: '',
  PUSHER_APP_KEY: '',
  PUSHER_APP_SECRET: '',
  PUSHER_APP_CLUSTER: '',
};
```


# Usage
See [pusher](https://www.npmjs.com/package/pusher) for full usage information.

```js
const Pusher = use('Pusher');

Pusher.trigger('channel-1', 'test_event', { message: "hello world" });
```