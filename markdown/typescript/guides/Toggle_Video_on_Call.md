
# Toggle Video on Call
```html
<html>
<head>
  <title>Toggle Video on a Call</title>
</head>
<body>
<button id="toggleVideo">Toggle Video</button>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  await client.connect();
  var call = await client.call("+18883796686"); 
  var me = call.me;
  await call.accepted();
  call.stream(); //also me
  var peers = call.play(); //same as call call.peers
  var videoEnabled = true;
  toggleVideo.onclick = () => {
    if(videoEnabled) {
      me.mute(cam);
      peers.mute(video);
      videoEnabled = false;
    } else {
      me.unmute(cam);
      peers.unmute(video);
      videoEnabled = true;
    }
  };
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk1NzI2NzA4MSwtMzU0NzAzMjk2LDE3OT
U4ODg0MTMsLTE3NTM1NTkzNTldfQ==
-->