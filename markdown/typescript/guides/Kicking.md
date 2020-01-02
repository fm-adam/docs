# Kicking
```html
<html>
<head>
  <title>Kicking</title>
</head>
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  await client.connect();
  var conference = await client.join('myroom');
  conference.stream();
  conference.play();
  var participants = conference.getParticipants();
  if(conference.getParticipants().length > 1) {
    conference.kick(participants[1].id, "You have been kicked.");
  }
  conference.onkick = (e) => {
    alert(e.message);
  };
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MzUyODIzNzcsNDU1MTIyODg4LDMyOD
M4MDUyMiwxMjQ1ODA2ODA0LDczMDk5ODExNl19
-->