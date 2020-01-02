
# Cancelling a Call
```html
<html>
<head>
  <title>Cancelling a Call</title>
</head>
<body>
<button id="cancel">Cancel</button>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  await client.connect();
  var call = await client.call("+18883796686");
  cancel.onclick = () => {
    call.cancel();
  };
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQxNTk4MTc4MSwxNjkwNjk5NDQyXX0=
-->