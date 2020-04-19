FCM has 3 kind of notifications

1. Notification messages Json body will be only having notification tag FCM will automatically show notification in client app if app is in background. onMessageReceived() will be called both in foreground . In background, onMessageReceived() will not be called.

{
  "message":{
    "token":"bk3RNwTe3H0:CI2k_HHwgIpoDKCIZvvDMExUdFQ3P1...",
    "notification":{
      "title":"Portugal vs. Denmark",
      "body":"great match!"
    }
  }
}
2. Data messages Json body will be only having data tag Developer have to show notification. onMessageRecieved will be called both in foreground as well as in background. The json should only have data tag in it

 {
      "message":{
        "token":"bk3RNwTe3H0:CI2k_HHwgIpoDKCIZvvDMExUdFQ3P1...",
        "data":{
          "Nick" : "Mario",
          "body" : "great match!",
          "Room" : "PortugalVSDenmark"
        }
      }
    }
3. Notification and data messages

The json body will be having both notification and data tags. onMessageReceived() will be called only when app is in foreground. Notifications will be shown automatically shown if app is in background and onMessageReceived() will not be called.

{
  "message":{
    "token":"bk3RNwTe3H0:CI2k_HHwgIpoDKCIZvvDMExUdFQ3P1...",
    "notification":{
      "title":"Portugal vs. Denmark",
      "body":"great match!"
    },
    "data" : {
      "Nick" : "Mario",
      "Room" : "PortugalVSDenmark"
    }
  }
}
For more info please read https://firebase.google.com/docs/cloud-messaging/concept-options
