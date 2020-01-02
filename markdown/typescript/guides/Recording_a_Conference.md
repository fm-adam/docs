# Recording a Conference
```html
<html>
<head>
  <title>Recording a Conference</title>
</head>
<body>
<button id="startRecording">Start Recording</button>
<button id="stopRecording">Stop Recording</button>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  await client.connect();
  var conference = await client.join('myroom');
  conference.stream();
  conference.play();
  startRecording.onclick = () => {
    await conference.startRecording();//client vs server?
  };
  stopRecording.onclick = () => {
    await conference.stopRecording();//client vs server?
  };
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTE0ODM4OTUzLC0xOTc1NTE0NDk0LC0xMz
AxMjQ0OTM3LDE2ODQyMDkwNV19
-->