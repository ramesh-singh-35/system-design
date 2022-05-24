##NOTIFICATION SERVICE##

1. There are 3 types of notifications: mobile push notifications, email message and a sms message.
2. APN is a remote service provided by Apple to push notifications to IOS devices.
3. For Android devices FCN (Firebase Cloud Messaging) is used for push notifications.
4. For SMS messages we can use third party services such as Twilio.
5. For email messages we can again use third party services.
6. When user installs our app, we will store the user data in user table and device tokens to device 
table which can be mapped to user via user-id.
7.We need notification table also with user_id, notification_type, notification_status to check whether
   user has opted out of notifications or not.
8. We also need to save a notification template.
9. We don't want to lose data so notification will be saved in a notification logs.


