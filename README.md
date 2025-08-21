# GeminiCLI_Slash_Talk
Enable your microphone on Windows WSL Ubuntu with this and the corresponding MCP 

## Important Note:
This has all been setup on Windows 11 with WSL2 Ubuntu using pyAudio. 

MacOS and Windows native support are not tested. Likely need to adjust the MCP and not this code for those other OS's.

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

This command seemed to work best for me: 

/talk:start device_index=0 rate=16000 chunk=1024 energy_gate=15 min_talk_ms=250 end_sil_ms=800 pre_roll_ms=250 blocking=false 

/talk:start alone doenst seem to do much. 

You can use /talk:device to find your device index.

Blocking=true will block Gemini CLI until you stop talking.

Blocking=false will allow you to keep using Gemini CLI while it listens in the background.

### Keep the conversation going
It is a mixed mode. Meaning you can use your keyboard and microphone. Ask a question with your mic, get an answer, then type a follow up question using your keyboard. Or vice versa.

### Road map 
I would like to add turns flag to the /talk:start command so you can have a multi-turn conversation using your mic. Like a real conversation. TBD