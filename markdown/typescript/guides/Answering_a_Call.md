# Answering a Call

```html
<html>
<head>
  <title>Answering a Call</title>
</head>
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  var client = new Client();
  await client.connect();
  client.oncall = (call) => {
    if (confirm('Accept call from ' + call.getCallerId())) {
      call.accept();
      call.stream();
      call.play();
    } else { 
      call.reject();
    }
  };
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExODk4MjQ2NzgsLTIxMjU4NjEwOTEsNj
U5NDEyOTQ3LC0yMDI5Nzk2MTEsLTEyODA2Mjg1MDYsLTc0MzE2
MDk0OCwxNTkzNjAwNTgyLDk0Mjc3NTMyOV19
-->