
# Cancelling an Invite
```html
<html>
<head>
  <title>Cancelling an Invite</title>
</head>
<body>
<button id="cancel">Cancel</button>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  var client = new Client();
  await client.connect();
  var conference = await client.join('myroom');
  conference.stream();
  conference.play();
  var invite = await conference.invite('+18883796686');
  cancel.onclick = () => {
    invite.cancel();
  };
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NTEzNDk2NSwtMTM0Mjk3OTE0Ml19
-->