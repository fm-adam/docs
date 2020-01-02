# Sending a File
```html
<html>
<head>
  <title>Sending a File</title>
</head>
<body>
<button id="sendFile">Send File...<\button>
<input id="fileInput" type="file" name="name" style="display: none;" />
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  await client.connect();
  var conference = await client.join('myroom');
  conference.onfile = (e) => {
    alert('Received a file from: ', e.getSender());
  };
  sendFile.onclick = () => {
    document.getElementById('file-input').click();
  };
  fileInput.onchange = (e) => {
    var file = e.target.files[0];
    conference.sendFile(file);
  };
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk5Nzk5MTM0Miw2NDY2MDA5MzcsMTU1NT
g4Mjc4OSwtODk5MTQzNDkwLDE5NTkyNTYzMTgsMTI1MDc1Nzky
OF19
-->