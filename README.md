# Bot Studio

Bot Studio is a lightweight web-app dedicated to turning bot creation (for Discord only, at the moment) into an entirely visual, zero coding process. Written in Express and Node.js. The generated code for Discord uses Discord.js.

## Installation

Installation details will be available on first release.

## Components

### Controls
Controls are the building blocks of a bot generated by Bot Studio. It is the programmed response by the bot to an Event or Message. Controls are categorized into four: Simple Controls, Functions, Extended Controls, and Dedicated Controls.

#### Simple Controls
Simple Controls are designed for Message oriented I/O. Simple controls take in the **Global Bot Prefix** and a ``command``. The bot can then be programmed to respond by sending a reply or a direct message to the User, or through a list of available Functions.

### Functions
Functions are preprogrammed actions that can only reside within a Simple or Extended Control. For example, reacting to a message requires a Simple or Extended Control that determines which Message should be reacted to.

#### Extended Controls
Extended Controls are the same as Simple Controls but allows for additional procedural programming. Uses JavaScript.

#### Dedicated Controls
Special Controls that take an input and executes a pre-defined process. Dedicated Controls cannot be modified but may return Events that can be handled by other Controls. For example, Bot Studio includes Dedicated Controls for playing a song from YouTube into a channel within a Guild.

### Variables

#### Global Variables
Global variables that may be referenced by the bot on any Control.
##### Required Variables
Global Bot Prefix - The prefix that the bot will use for Commands.  
Bot Token - The secret token for accessing the bot (This may be left blank for privacy and inserted by the author later on outside Bot Studio.)

#### Control Variables
Local variables that can only be accessed by the Control that created it.

### Templates
Templates allow the author to waste less time in recreating the same complex over and over again. This is useful for dynamic embeds and generating image cards.

## List of Available Controls

### (Simple) Command
Receives a message then executes the Controls within it.  
**Required Parameters**: String ``Command``  
**Returns?** No  
**Available in**: Discord

### (Function) Message
Messages the Channel within the current context.  
**Required Parameters**: String ``Message``  
**Returns?** No  
**Available in**: Discord

### (Function) Direct Message
Creates a Direct Message channel with the User that triggered the Simple or Extended Control.  
**Required Parameters**: String ``Message``  
**Returns?** No  
**Available in**: Discord

### (Function) Create Embed
**Required Parameters**: EmbedTemplate ``TemplateName``  
**Returns?** Yes  
**Return Type**: Int ``ErrorCode``  
**Available in**: Discord

### (Function) React
**Required Parameters**: Int ``Unicode`` (Emoticons are automatically converted into its Unicode equivalent)  
**Returns?** Yes  
**Return Type**: Int ``ErrorCode``  
**Available in**: Discord

### (Function) Play Sound
**Required Parameters**: String ``Path``, String ``Channel``  
**Return Type**: Int ``CurrentTime``  
**Available in**: Discord

### (Dedicated) YouTube Playback
**Required Parameters**: String ``Query``, String ``Channel``  
**Returns?** Yes  
**Return Type**: Int ``ErrorCode``  
**Available in**: Discord

### (Dedicated) Firebase Realtime Database Update
**Required Parameters**: String ``Path``, JSON ``Data``  
**Returns?** Yes  
**Return Type**: Int ``ErrorCode``  
**Available in**: Discord

### (Dedicated) Local Database Update
**Required Parameters**: String ``Path``, Data (may be any data type that can be written to a file), String ``Extension``  
**Returns?** Yes  
**Return Type**: Int ``ErrorCode``  
**Available in**: Discord
