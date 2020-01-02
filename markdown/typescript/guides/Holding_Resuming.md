# Holding & Resuming

```html
<html>
<head>
  <title>Hold & Resume</title>
</head>
<body>
<button id="hold">Hold</button>
<button id="resume">Resume</button>'
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  await client.connect();
  client.oncall = (call) => {
    call.accept();
    call.stream();
    call.play();
    hold.onclick = () => {
      call.hold('https://www.youtube.com/watch?v=oHg5SJYRHA0');
    };
    resume.onclick = () => {
      call.resume();  
    };
  };
</script>
</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg4NzUzODI4OSwtNjI2MDM3NDMyLDE3Mz
EzMzAwOTFdfQ==
-->