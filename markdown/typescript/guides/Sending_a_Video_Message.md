# Sending a Message
```html
<html>
<head>
  <title>Sending a Message</title>
</head>
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  await client.connect();
  var conference = await client.join('myroom');
  conference.onvideomessage = (e) => {
    e.message.play();
  };
  var clip = await client.record();//client.record('cam', 'mic')
  conference.videoMessage(clip);
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbODE0MzYyMDU4LDY2NjcxNTgwMV19
-->