---
layout: post
#title: Add Bulk Guest users in Teams

---
In current situation (Lockuots due to COVID-19) most of our customers are moving to remote working and have startes using Microsoft Teams as the one common use case we come across is to invite users from other organizations as Guest users in their Teams for various reasons including .

### Option 1: Move to Inbox and using mailbox migration tool. 

By default, chats don’t get migrated to Office 365 but in G-Suite we have an option of selecting all the chats and move them to Inbox. 



![](/images/csv.jpg)

![](/images/Create Group1.jpg)

![](/images/Group details small.png)
![](/images/Group details.png)

![](/images/Invite Email.jpg)
![](/images/Get Link to Team.jpg)





Once this is done, mailbox migration process can move the chats as individual emails to Inbox. Although we can get the Hangout Chats to Office 365 mailbox but following are few observations which may not be acceptable to customers.

- Sequence of conversation is not maintained.
- Image/Files shared on hangouts are not reflecting in Office 365.
- Information about second party involved in conversation is NOT captured.
- Timestamping changes in Office 365 as all messages show same time (time of migration).
- Each message in Office 365 is just single line. "Enter" event is generating a new message in Office 365. 

![](/images/G_Suite_Post_Migration.jpg)

### Option 2: Using “[Google Takeout]( https://takeout.google.com/)” and “[JSON to CSV](https://github.com/mratkovic/hangouts_json_to_csv)”

In this method, I exported Hangout chats using Google Takeout into JSON format and then used JSON to CSV converter. Once CSV's are available, we can import them to either user mailbox or OneDrive or even in Microsoft Teams.

Although this option doesn't reflect the data directly in user mailbox for search and unique CSV gets generated for each user interaction resulting in lot of administrative overhead from migration perspective as administrator has to manage these CSV’s and associate with user’s profile but good part is that:

- Sequence of conversation is maintained.
- We get a URL for accessing Image/Files shared on hangouts.
- Information about second party involved in conversation is captured.
- Timestamp is maintained.

Although both approaches mentioned above have their Pro's and Con's but considering that people generally don’t have very critical data stored in chats, hopefully you will have to do this very rarely and that too for limited users. Also hope that 3rd party migration tool vendors look into this and create a tools for this.