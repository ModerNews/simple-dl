![image](https://github.com/user-attachments/assets/6f954808-cde6-4bab-bfb5-769763bbcffe)# simple-dl

Simple-dl is a project aiming to create a *simple* web-based front end solution for the [youtube-dl](https://github.com/ytdl-org/youtube-dl) CLI.

While there are some projects that fill-in the same niche, like:
- [YoutubeDL Material](https://github.com/Tzahi12345/YoutubeDL-Material)
- [AllTube](https://github.com/Rudloff/alltube)

They either not fullfilling all the needs, have missing features, or are in other ways lackluster.

## Design
>[!NOTE]
>Those are only design mock-ups. All functionalities are still subject to change.

### Color Scheme
- #121212 - Gray for dark background behind the page
- #1e1e1e - Gray for background in cards/containers
- #FF3E00 - Orange as a main accent color
- #EF4444 - Red as error/cancel/destructive action accent
- #21C55D - Green as success/confirmation accent

### Common components
#### Action Buttons
Action buttons are small, circular buttons present on video cards, they are in the following variants:

![image](https://github.com/user-attachments/assets/b1ccd6ed-3b07-4f00-ba1d-ec385bb767dd)

The buttons represent action as following:
- `Add` - adds item into a queue
- `Cancel` - generic cancel action, seen in few places
- `Processing` - Orange spinner indicating download actively processing
- `Waiting` - Indicates item waiting in the queue for download
- `Fail` - Indicates failed download
- `Fail - Retry` - A confirmation prompt for retrying failed download
- `Ready` - Indicates video ready to be downloaded to personal device
- `Downloaded` - Indicates download was initiated by browser (does not represent success in the browser flow)

#### Settings button
Slightly bigger than action button, in fixed place, opens settings pop-up

![image](https://github.com/user-attachments/assets/3132c1e1-a7d4-461b-a744-c52174ab1705)

#### Format dropdown
Simple shared dropdown, allowing user to select from list of pre-defined formats 

![image](https://github.com/user-attachments/assets/0b63b14f-8df3-43c6-a6a1-9031a648405a)

### Mobile
Whole application is designed to fit in a single dynamically changing page

![image](https://github.com/user-attachments/assets/67a190cb-79c8-408e-a2b0-83967c5c3b39)

Three main views - selection, download processing and download completed.

![image](https://github.com/user-attachments/assets/caeb6c1f-e3cd-45de-b230-83f6540d61a0)

User can choose the download format globally, pasting more then one link, separated by new-line indicators will result in creating multiple entries at once, action buttons on the right allow for removing entry from the list, which results in entry being replaced by a notification toast:

![image](https://github.com/user-attachments/assets/f122d7e7-b214-4972-9c89-727bbf3e2f19)

That fades away over time.

Starting download process causes additional input fields to disappear, and action buttons take on new roles. Additionaly a status bar slides out:
23
![image](https://github.com/user-attachments/assets/d7295683-01de-4578-989a-98135f5094b2)

Action buttons now double as status indicators:
- Gray with the hourglass means awaiting download to the server
- Orange with spinner means actively downloading
- Green means download is successfull, and you can now download to your personal device by tapping the button
- Red means failure in the download, tapping on the button will reveal a red retry indicator. Pressing it again will re-add the video at the end of the queue, resulting in the indicator being replaced with `waiting`.

Status component can be extended, to show the live console output from youtube-dl that's running in background on the server.
![image](https://github.com/user-attachments/assets/51220cb2-3309-4eec-902d-d1ad43793d83)

![image](https://github.com/user-attachments/assets/a402a4c6-9455-4c4d-bd13-6d5b41b6f8d6)

After all downloads are completed bottom button is replaced with a download all prompt (additional to a single downloads that are available via the status buttons on the right of the video links).

Pressing the download all prompt will result in opening a filename selection pop-up with pregenerated name
![image](https://github.com/user-attachments/assets/5dd1917d-efed-4c88-b7ac-1e0206512b6b)
Upon tapping the text field you should be prompted with system file browser prompt

Clearing the queue after downloads is a two-step process
![image](https://github.com/user-attachments/assets/be5c6892-ed19-4a54-b1fc-a60fb8da4172)

First tap on the clear all button will result in removing all the successfull downloads, only the second time the app will remove everything.

All destructive (and unreversible) actions are hold-to-confirm to prevent user from accidentally tapping on the button, as shown below:
![image](https://github.com/user-attachments/assets/c6779646-f45a-4966-af53-7ed86f45deda)

### Full Design Sheets
#### Mobile
![image](https://github.com/user-attachments/assets/d1eba86e-bf75-4925-a951-685e6d1648e4)

#### Tablet
![image](https://github.com/user-attachments/assets/7bb353ad-3353-45f3-b571-306a6eec16f6)
![image](https://github.com/user-attachments/assets/0d6a66e0-7070-4389-8b04-15ba35ef28fb)
