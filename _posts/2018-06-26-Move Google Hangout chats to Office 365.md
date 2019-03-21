---
layout: post
#title: Move Google Hangout chats to Office 365

---
I was recently working with a customer who was using G-Suite for collaboration. When we spoke about migration of their existing G-Suite data to Office 365, they informed that they have some critical data on Hangout Chats which the want to move to Office 365 as well. I checked and found that there are no native or 3rd party tools which can do Hangout Chat data migration. Since this was "showstopper" for them, I looked for options and found that we can move the Hangout chat data to Office 365 with some manual effort and few riders discussed below.

### Option 1: Move to Inbox and using mailbox migration tool. 

By default, chats don’t get migrated to Office 365 but on Google we have an option of selecting all the chats and “Move to Inbox”. 
![](/images/G_Suite_Move to Inbox.jpg)
Once this is done, mailbox migration process can move the chats as “Individual Emails” to Inbox. Although we can get the Hangout Chats to Office 365 mailbox but following are few observations which may not be acceptable to customers.
-Sequence of conversation is not maintained.
-Image/Files shared on hangouts are not reflecting in Office 365.
-Information about second party involved in conversation is NOT captured.
-Timestamping changes in Office 365 as all messages show same time (time of migration).
-Each message in Office 365 is just single line. "Enter" event is generating a new message in Office 365. 

![](/images/G_Suite_Post_Migration.jpg)

### Option 2: Using “[Google Takeout]( https://takeout.google.com/)” and “[Json to CSV](https://github.com/mratkovic/hangouts_json_to_csv)”

In this method, I exported Hangout chats using Google Takeout into json format and then used Json to CSV converter and then somehow import this CSV to user mailbox.
I tested the other workaround using “[Google Takeout]( https://takeout.google.com/)” that we discussed yesterday, and good part is that:
1)	Sequence of conversation is maintained.
2)	We get a URL for accessing Image/Files shared on hangouts.
3)	Information about second party involved in conversation is captured.
4)	Timestamping is maintained.

But in this case a different CSV gets generated for each user interaction for e.g. a separate CSV will get generated for interaction between user A and user B and user A and user C. (Attached is sample file) which will result in lot of administrative activity to manage these CSV’s and associate with user’s profile 