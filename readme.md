![Add Subtitles to Twitch TV using OBS](https://www.pubnub.com/wp-content/uploads/2018/07/add-subtitles-to-twitch-tv-obs.png)

# Twitch TV Subtitles

You are a **live streamer** using OBS ( Open Broadcaster Software ) and you are
open to experimental ways to **increase followers** on your stream.
And you don't want to spend money, because reasons and
the internet should be free!

##  Installation Guide: OBS Subtitles for Twitch TV

> **Start here:** https://www.pubnub.com/developers/twitch-tv-obs-subtitles/

Follow the easy 60 second installation.
To install Subtitles in OBS for Twitch, start by visiting the URL above.

![Step 1](https://i.imgur.com/ScIDnJc.gif)
![Step 2](https://i.imgur.com/MFhOheM.png)
![Step 3](https://i.imgur.com/s0vvMlC.gif)

## Running Twitch.TV Subtitles from Local Files on your Hard Drive

If you've downloaded this repository, made changes and want 
them to be available in your OBS, you need to follow these instructions.
Due to security, you need to run an HTTP Server for OBS to access your local files.
You'll do this by opening a terminal window and running a Simple HTTP server.
Attempting to run Twitch Subtitles without an HTTP server will result in a 
non-working page with *"Start talking."* permanently stuck on the viewport.

#### 1.) Download and Install Python: https://www.python.org/downloads/

#### 2.) After you've installed Python, open your terminal and start the 
Python Simple HTTP Server in the same director as the Twitch.TV Subtitles:

> Windows: Press `WinKey+R` type `cmd` and press "Enter" to open a Command Prompt

> Mac: Press `Command+Space` type `terminal` and press "Enter".

Navigate to the Twitch TV Subtitles directory using `cd` command.

```shell
cd twitch-tv-obs-subtitles
python -m SimpleHTTPServer 8080
```

> If the `cd` command fails, you need to know where the folder is located.
> You must `cd` to the folder `twitch-tv-obs-subtitles`.
> It may be in your `Downloads` folder: `cd Downloads/twitch-tv-obs-subtitles`.
> If you are still having trouble, you may try the **`Alternate`** lower in this document.

#### 3.) Copy the URL from Step 2 on the [Subtitles Twitch.TV Page](https://www.pubnub.com/developers/twitch-tv-obs-subtitles/)

The URL will look similar to this:

```shell
https://stephenlb.github.io/twitch-tv-obs-subtitles/subtitles.html?subkey=sub-c-79b0a26a-80a9-11e8-8f4a-96bbd71e7d14&pubkey=pub-c-fd9b97a4-7b78-4ae1-a21e-3614f2b6debe&channel=1552687539739502028833&style=background%3Ablack%3Bfont-weight%3A600%3Btext-transform%3Auppercase%3Btext-shadow%3Anone%3Bpadding%3A10px%3B
```

> **Keep [Subtitles Twitch.TV Page](https://www.pubnub.com/developers/twitch-tv-obs-subtitles/) open.**
> This page will capture your voice and transmit it to your local computer.

#### 4.) Modify the copied URL from Step 3 by replacing

**`https://stephenlb.github.io/twitch-tv-obs-subtitles/subtitles.html`** with

**`http://0.0.0.0:8080/subtitles.html`**.

Your final URL will look like:
```shell
http://0.0.0.0:8080/subtitles.html?subkey=sub-c-79b0a26a-80a9-11e8-8f4a-96bbd71e7d14&pubkey=pub-c-fd9b97a4-7b78-4ae1-a21e-3614f2b6debe&channel=1552687539739502028833&style=background%3Ablack%3Bfont-weight%3A600%3Btext-transform%3Auppercase%3Btext-shadow%3Anone%3Bpadding%3A10px%3B
```

#### 5.) Past the Final URL into OBS.
Note that your final URL will differ from the one shown above.

That's it!  
If you've made a mistake start over from the beginning 
it won't hurt to repeat any of the steps.
However you may run into issues.
That's why we've included a second option that may work better for you.

## Alternate: Running Twitch.TV Subtitles from Local Files on your Hard Drive

> While this method is easier, it is not the preferred method.
This method introduces an opportunity for someone else to take
over your subtitles mid-stream.
It is unlikely that someone will know how to do this,
however it is easy for a hacker.
If you want to avoid a hacker taking over your subtitles,
use the secure method:
[Secure Method](#running-twitchtv-subtitles-from-local-files-on-your-hard-drive).

> Also if you're using [Subtitles Twitch.TV Page](https://www.pubnub.com/developers/twitch-tv-obs-subtitles/)
directly off the PubNub website, then your are secured automatically.

#### 1.) Edit the file `js/username.js`.
It will look like this:

```js
function username() {
    return ""; // <-- Fill in your username
               // example: return "ninja";
}
```

And type in your Twitch Username like this:

```js
function username() {
    return "MY_TWITCH_ID_HERE"; // <-- Fill in your username
               // example: return "ninja";
}
```

#### 2.) Copy the URL from Step 2 on the [Subtitles Twitch.TV Page](https://www.pubnub.com/developers/twitch-tv-obs-subtitles/)

It will look similar to this:

```shell
https://stephenlb.github.io/twitch-tv-obs-subtitles/subtitles.html?channel=1552687539739502028833&subkey=sub-c-79b0a26a-80a9-11e8-8f4a-96bbd71e7d14&pubkey=pub-c-fd9b97a4-7b78-4ae1-a21e-3614f2b6debe&style=background%3Ablack%3Bfont-weight%3A600%3Btext-transform%3Auppercase%3Btext-shadow%3Anone%3Bpadding%3A10px%3B
```

#### 3.) Modify the copied URL from Step 2 by replacing

**`channel=1552687539739502028833`**  with

**`channel=MY_TWITCH_ID_HERE`**.

#### 4.) Point your Chrome Browser to: 

```shell
https://stephenlb.github.io/twitch-tv-obs-subtitles/subtitles.html?channel=MY_TWITCH_ID_HERE&subkey=sub-c-79b0a26a-80a9-11e8-8f4a-96bbd71e7d14&pubkey=pub-c-fd9b97a4-7b78-4ae1-a21e-3614f2b6debe&style=background%3Ablack%3Bfont-weight%3A600%3Btext-transform%3Auppercase%3Btext-shadow%3Anone%3Bpadding%3A10px%3B
```

> Warning! Make sure only **one Twitch.TV Subtile Page** is open.
If they are others, they will block your local page.

#### 5.) Add a new browser source in OBS.

#### 6.) Check `Local file` in OBS Browser config window.

#### 7.) Click `Browse` button and select `subtitles.html`
found in your folder `twitch-tv-obs-subtitles`.

That's it!
Easy right?

## What is an OBS Browser Source?

Browser Sources can be added to your scenes of your streaming software and
enable you to use web based content such as Flash and JavaScript applications,
websites and so on and even customize them via CSS. Since this kind of content
is usually not written in the same coding languages as your streaming
application, a translator is needed to make it possible for both to
communicate with each other.

## Build Website Landingpage

You will not need to do this as it is only a tool used for building the
landing page on the PubNub Website.
This will build `./build/dashboard.html` and copy source to your clipboard.
You can see a live version of the
[Twitch TV OBS Subtitles Browser Source](https://www.pubnub.com/developers/twitch-tv-obs-subtitles/) page.

```
./copy
```

## See more voice app projects

We have built several more apps using the 
[Spoken NPM Package](https://www.npmjs.com/package/spoken).
Check them out below.

### Build an 80's Chatbot with an NPM Package

How to build a
[voice-controlled intelligent chatbot](https://www.pubnub.com/blog/build-an-80s-chatbot-with-an-npm-package/)
who comprehends human speech and responses accordingly and naturally!

### Add Voice Contorl to your OBS Twitch and YouTube Live Streams

Learn how we [built an OBS
Plugin that adds Subtitles to your
Live Stream](https://www.pubnub.com/developers/twitch-tv-obs-subtitles/).

Add Subtitles to your Twitch stream! Easy OBS integration.
Plugins should be easy to make! And for OBS, this is true. Hurray!
The best way by far, my opinion, is using OBS Browser Sources.
