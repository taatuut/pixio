# pixio
Online Pictionary with MongoDB integration. Play with friends remotely on mobile and laptop.

# Inspiration
Heavily inspired on https://developer.mongodb.com/how-to/creating-multiplayer-drawing-game-phaser

# Howto

## Application

Click above link and follow the tutorial until you created the index.html and game.js file up to the point where it says 'You did it!'.

## MongoDB Atlas

If you don't have a (free) MongoDB Atlas cluster running yet, goto https://www.mongodb.com/cloud and click [ Try MongoDB Cloud Now ] and signup. If you already have a running cluster, login to your cluster. In your Atlas cluster, create a mongo-draws database with a game collection.
Note: make sure to whitelist access to your cluster for the relevant IP addresses.

[img]

## Realm

To create a new Realm App, click the Realm link at the top of the page.

[img]

Then click [ Create a New App ] with the name mongo-draws and connect it to the cluster where you created the mongo-draws database just a moment ago.

[img]

Now the page for the newly created app opens. Enable anonymous authentication by clicking the Providers tab in the Users area of the Realm dashboard.

[img]

Set the switch to on and click [ Save ]

Anonymous access is now enabled, but must be deployed to take effect. Click [ Review & Deploy], in teh window that opens you can review the code changes, then click [ Deploy ]. You will see a message appear with timestamp saying 'Deployment was successful!'.

With the anonymous authentication effectively enabled, we can define the read and write rules of our documents.

Go to the Rules area, confirm that 'No template' is the selected item and click [ Configure Collection ]

[img]

Within the Rules area of the Realm dashboard, create two rules for the game collection. The first rule is for the document owner, give them read and write ability. For non-owners watching the game need read access. Make sure to specify that the owner_id of the document is to be mapped to the document owner, during the process of creating rules.

First do owner, then click [ + NEW ROLE ] and create non-owner role.

[images]

You will end up with somethign like this

[img]

Don't forget to save and deploy. MongoDB Atlas and Realm are now ready to be used in our game.

Now it is into the game.js and index.html files again for some more edits.

After that go back to the Realm applications overview to find your mongo-draws app there too.

[img]

If you go back in your app, you can copy the app id you need to put in the index.htmnl file replacing the REALM_APP_ID value in the new Game property "realmAppId".

When done, make sure to save all your efforts and deploy somewhere Hint: use Realm Hosting https://docs.mongodb.com/realm/hosting/ an option available in the app page too.

[img]

Enabling hosting gives you the possibility to upload content through the Realm UI or by usign the Realm CLI. It comes with a default index.html that we will oevrwrite when uploading our content. Hosting also gives you a custom name for your app (in my case it is https://mongo-draws-pzzoc.mongodbstitch.com/), and you can even hook up a domain name you own.

https://stitch-statichosting-prod.s3.amazonaws.com/5f05d33eb0446543ed7532cd/index.html

[img]

[img]

