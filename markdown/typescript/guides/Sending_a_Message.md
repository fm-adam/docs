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
  conference.onmessage = (e) => {
    alert(e.message);
  };
  conference.message('a message');
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA3NDg2NzM4MywxOTAyNzMxNDAwLDYyOT
k0NjQxMV19
-->