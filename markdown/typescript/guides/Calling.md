# Calling

This guide is for a LiveSwitch

## 1. Initialize

Create an HTML page with a reference to the LiveSwitch SDK:

```html
<html>
<head>
  <title>Calling</title>
</head>
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  // ...
</script>
</body>
</html>
```

... or use an existing page you have handy. Either way works.

## 2. Connect

Create a `Client` using a temporary token we have [generated](https://docs.liveswitch.io/topics/generating-tokens) for you (valid for the next 24 hours):

```javascript
var token = '... temporary token generated automatically ...';
var client = new Client();
await client.connect();
```

The connect token includes  the initial channel you want to join (`user_id` in this case), gateway URL, your application ID, user ID, device ID and  and  initial channel you want to join - case*optionally* region.
`Client.connect()` registers with the gateway and joins a channel, `user_id` , on which gateway communicates with this client.

Note that clients can also [join and leave channels](https://docs.liveswitch.io/topics/joining-and-leaving-channels) any time after registering.

## 3. Call

Let's make a call to a user *remote_user* (alternatively, you may call a SIP number: use *sip:+17785657676@sip.fm.com* instead of *remote_user*).
Client contains convenience methods to create Calls, Conferences and Broadcasts. All three are Sessions, and have identical properties and methods, but differ in the way they are initiated. In a *Call* paradigm, peer A sends an invite to peer B. Peer B answers the call and both parties join the session auto-created for that call. Other peers can also join that call.

```javascript
var call = await client.call("+18883796686");
```
*Call()* creates a new. Here we will call a user *remote_user*. Alternatively, you channel just for this call and sends an invite to the *remote_user* to join that session.
Noew subscribe to events associated with this call. One of them allows you to know when peer has answered the call or left the session: call a sip number, where instead of user id, you would specify a SIP number (e.g. "+17786555533@sip.fm.com").

```javascript
await call.accepted();
```
*response* contains the status of the call invite. It can be fm.easy.CallStatus.Answered, fm.easy.CallStatus.Rejected, fm.easy.CallStatus.Error

## 4. When a Call is Answered
 If call is answered, you need to access your camera and microphone feed, as well as to play remote media:
_Your web browser may prompt for permissions to access the local microphone and camera._
```javascript
call.stream();
call.play();
```

The `stream` function is [highly customizable](https://docs.liveswitch.io/topics/stream-parameters).  
## 5. Test

Your page should now look like this:

```html
<html>
<head>
  <title>Calling</title>
</head>
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/fm.liveswitch@latest/fm.liveswitch.js"></script>
<script type="text/javascript">
  var client = new Client(new BasicTokenGenerator("user_id", "device_id", "app_id", "secret"));
  await client.connect();
  var call = await client.call("+18883796686"); 
  await call.accepted();
  call.stream();
  call.play();
</script>
</body>
</html>
```

Mute your speakers to avoid feedback, and then open this page in two browser tabs to create a live video call!

- [Run in Limeweave](https://)
- [Run in CodePen](https://)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MjE4NzkzMTMsMjQxNDAwNTg0LDE0Nj
kwMTQ0NDgsMTI0ODY2MjIyLDE3ODkxNjA0MDQsMTU4MzE1MDIy
NywtMjExMDUxODgzMyw3NTI3MTcxMTMsMjM4NTIyNzI3LDE3MT
U2NDYyOSwxOTAxOTIxNjQ0LC05MTQ1NjM0ODYsMTYyMzcwODYx
NCwtMjg0NjI3MzA2LDg0MDIyMjM5NywxNjMzNDY4MzkwLC0xNz
cwMjEzMDUwLDY0NjY1MDY0Myw4OTEwMTU4MSwtMTg5NDg1MzE3
N119
-->