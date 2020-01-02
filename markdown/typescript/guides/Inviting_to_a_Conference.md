# Inviting to a Conference

```html
<html>
<head>
  <title>Inviting to a Conference</title>
</head>
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  var conference = await client.join("myroom");
  conference.stream();
  conference.play();
  var invite = conference.invite("+18883796686");
  await invite.accepted();
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjI5OTQwNjE3LDEyNzg1MTM0MDYsMTI3ND
YxMjA5NF19
-->