# Muting & Unmuting
```html
<html>
<head>
  <title>Muting & Unmuting</title>
</head>
<body>
<button id="mute">Mute</button>
<button id="unmute">Unmute</button>'
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  await client.connect();
  client.oncall = (call) => {
    call.accept();
    var me = call.stream();
    var peers = call.play();
    mute.onclick = () => {
      me.mute('https://bit.ly/2OVsLi0');
    };
    unmute.onclick = () => {
      me.unmute();  
    };
  };
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjgxOTcxOTc2LC0yMjIwNTk0NTUsNzAxNT
k3NjI4LC0yNzk5ODIwODJdfQ==
-->