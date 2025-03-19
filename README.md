<img src="https://avatars1.githubusercontent.com/u/54474115?s=460&v=4" width="100" alt="" data-canonical-src="https://avatars1.githubusercontent.com/u/54474115?s=460&v=4">  &nbsp;&nbsp;
<img src="https://gamemonetize.com/images/html5-logo.png" width="100" alt="" data-canonical-src="https://gamemonetize.com/images/html5-logo.png">

# GameMonetize.com-SDK
<p>This repository contains the GameMonetize.com SDK for HTML5 games. This allows you to display advertisements in the games published within the GameMonetize.com network. https://GameMonetize.com</p>
<p>We offer also SDK for all Web3 Gaming Frameworks: Unity, Construct 3 (v2), Construct 2, Cocos2D and HTML5</p>

# STEP 1:
# HTML5 SDK - Implementation
<p>Add following rows into your index.html file (head section or body section). Fill gameId and use SDK events when you need it (mute audio, pause game and after that resume game logic).</p>
<p>This code will initialize GameMonetize.com HTML5 SDK</p>

<pre><code><script type="text/javascript">
   window.SDK_OPTIONS = {
      gameId: "your_game_id_here",
      onEvent: function (a) {
         switch (a.name) {
            case "SDK_GAME_PAUSE":
               // pause game logic / mute audio
               break;
            case "SDK_GAME_START":
               // advertisement done, resume game logic and unmute audio
               break;
            case "SDK_READY":
               // when sdk is ready
               break;
         }
      }
   };
(function (a, b, c) {
   var d = a.getElementsByTagName(b)[0];
   a.getElementById(c) || (a = a.createElement(b), a.id = c, a.src = "https://api.gamemonetize.com/sdk.js", d.parentNode.insertBefore(a, d))
})(document, "script", "gamemonetize-sdk"); 
</script></code></pre>

# MANDATORY SETTINGS:
1. Make sure to add your game hash (GameId), which you can retrieve from your GameMonetize.com control panel.
2. Invoke a method to pause AND mute your game within the SDK_GAME_PAUSE event. Will be called every time a video advertisement is ready to play. It is important that the game is muted, as background audio through video advertisements is forbidden.
3. Invoke a method to resume your game within the SDK_GAME_START event. Will be called every time a video advertisement is done playing.

# STEP 2:
# Invoke an advertisement
Now you must call sdk.showBanner() at the appropriate time in your game to show ads.

<pre><code>if (typeof sdk !== 'undefined' && sdk.showBanner !== 'undefined') {
sdk.showBanner();
}
</code></pre>

# STEP 3:
Now you can upload the game (Root folder of .ZIP file must include index.html and game files)
Go to Game Management > My games > Select you game > Drop file to upload.

# STEP 4:
Verify SDK by click on button "Verify Game". This shows you that you have correctly done integration and ready to publish.

# STEP 5:
Submit game - click on button REQUEST ACTIVATION

# FAQ
<h2>How to upload a game files?</h2>
<p><b>Answer</b>: When your game is ready to upload, you need to compress all game files to .ZIP file - Root folder of .ZIP file must include index.html and game files</p>
<h2><b>Implementation self-hosted games.</b></h2>
<p>In the case where a developer wants to self-host their game, please contact us on at: info@gamemonetize.com</p>

# Support:
If you have any technical questions or comments, please email us at:
info@gamemonetize.com

Or simply check documentation on:
https://gamemonetize.com/sdk
