
# Upgrade an Audio Call to an Audio-Video Call
```html
<html>
<head>
  <title>Upgrade an Audio Call to an Audio-Video Call</title>
</head>
<body>
<button id="enableVideo">Enable Video</button>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  await client.connect();
  var call = await client.call("+18883796686"); 
  await call.accepted();
  call.stream(mic);
  call.play(audio);
  enableVideo.onclick = () => {
    call.stream(cam);
    call.play(video);
  };
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbODI4NzQ2NTQzLC0xNzAyNDc2NDc4LDIwMD
k2NTUzOTEsLTc4OTIyODYzMV19
-->