# GeminiCLI_Slash_Talk
Enable your microphone on Windows WSL Ubuntu with this and the corresponding MCP 

## Important Note:
This has all been setup on Windows 11 with WSL2 Ubuntu using pyAudio as well as MacOS.

Windows native support are not tested. Likely need to adjust the MCP and not this code for those other OS's.

## You will need this MCP: 
https://github.com/automateyournetwork/Talk_MCP_for_Gemini_CLI

### Add the Settings to your settings.json
```json
{
  "mcpServers": {
    "talk": {
      "command": "/home/<homedir>/Talk_MCP_for_Gemini_CLI/talkmcp/bin/python",
      "args": [
        "/home/<homedir>/Talk_MCP_for_Gemini_CLI/talk.py"
      ]
    }
  }
}
```

### Move the commands folder or the subfodler talk into your .gemini folder 

This will add the /talk commands to Gemini CLI

### You are all set 

I suggest you check the commands with /talk:help

Then discover your mic with /talk:discover

If you want to pick your text to speech voice use /talk:voices

Then start a conversation with /talk:start

You can use flags like:

 --device_index to select your mic if you have multiple mics.
 --language to select your language. Default is auto detect.
 --voice to select your voice. Default is auto select.

Again check the talk commands with /talk:help

### Keep the conversation going
It is a mixed mode. Meaning you can use your keyboard and microphone. Ask a question with your mic, get an answer, then type a follow up question using your keyboard. Or vice versa.

### Road map 
I would like to add turns flag to the /talk:start command so you can have a multi-turn conversation using your mic. Like a real conversation. TBD

### TTS Audio playback 
In the folder you launched Gemini CLI from:
- export PLAY_CMD='ffplay -autoexit -nodisp -loglevel quiet'
- export OPENAI_API_KEY='yourkeyhere'

Now Gemini CLI will play the TTS audio response automatically.