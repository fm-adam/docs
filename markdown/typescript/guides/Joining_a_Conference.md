
# Joining a Conference
```html
<html>
<head>
  <title>Joining a Conference</title>
</head>
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  await client.connect();
  var conference = await client.join('myroom');
  conference.stream();
  conference.play();
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNDYyMDE0NzksMTEzNzYxMTgxMCwtNz
M0NTg2MDYwLC0xMzg0MTE5OTMxLDE0NDYyNDExMDYsLTM5NTUw
MDA4Ml19
-->