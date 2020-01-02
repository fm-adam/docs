# Hello, World

This guide is for **web applications** with **no framework**.

Let's connect people with LiveSwitch!

## 1. Initialize

Create an HTML page with a reference to the LiveSwitch SDK:

```html
<html>
<head>
  <title>Hello, World</title>
</head>
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  // ...
</script>
</body>
</html>
```

... or use an existing page you have handy. Either way works.

## 2. Register

Create a `Client` and call `register` using a temporary token we have [generated](https://docs.liveswitch.io/topics/generating-tokens) for you (valid for the next 24 hours):

```javascript
var token = '... temporary token generated automatically ...';
var client = new fm.liveswitch.Client();
client.register(token, (channels) => {
  channels.forEach((channel) => {
    // ...
  });
});
```

The register token includes your application ID and an _optional_ set of initial channels you want to join - `my_application_id` and `my_channel_id` in this case.

Note that clients can also [join and leave channels](https://docs.liveswitch.io/topics/joining-and-leaving-channels) any time after registering.

## 3. Stream

Call `stream` to start live-streaming yourself to the server:

```javascript
channel.stream();
```

_Your web browser may prompt for permissions to access the local microphone and camera._

The `stream` function is [highly customizable](https://docs.liveswitch.io/topics/stream-parameters).

## 4. Play

Call `playAll` to start playing all the live streams:

```javascript
channel.playAll();
```

The `play` and `playAll` functions are [highly customizable](https://docs.liveswitch.io/topics/play-parameters).

## 5. Test

Your page should now look like this:

```html
<html>
<head>
  <title>Hello, World</title>
</head>
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  client.register(token, (channels) => {
    channels.forEach((channel) => {
      channel.stream('camera', 'microphone');
      channel.playAll();
    });
  });
</script>
</body>
</html>
```

Mute your speakers to avoid feedback, and then open this page in two browser tabs to create a live video call!

- [Run in Limeweave](https://)
- [Run in CodePen](https://)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzMzgxNjcwNDQsMjAxNzE2NzUwMF19
-->