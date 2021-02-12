# twitch-rpcbot

A Twitch.tv chat bot to play Rock-Paper-Scissors with chat!

### Why tho?
I was inspired to do this by the great streamer Synthali, who likes to do Rock-Paper-Scissors with his chat. He's mentioned one stream that it's rather cumbersome to type out his response on another notepad and count whoever got the answer in chat correct by hand. This bot is supposed to streamline the process for this to happen.

### Okay, now what?
The plan currently is to create a working, stable bot that can take chat's options of rock, paper, or scissors and associate that answer with the participant in chat. The goal is to have the bot be able to accept commands for participant answers, compare against the streamer's answer, and reply to chat with a list of participants who won against the streamer.
Since Twitch.tv API Documentation indicates that all external programs that would want to interact with Twitch chat to do so through their IRC protocol (a slightly modified RFC 1459), [libircclient](https://github.com/alexlren/libircclient) is used so we don't have to implement the protocol ourselves (and so I don't have to bang my head on my keyboard reading technical docs XD). This also implies that I'm writing this in C, and this is because I want this bot to parse commands as soon as they come in, so performance is an emphasis (I'm also terrible at JavaScript).

### Goals!
- Create working version/prototype (and eventually a stable release).
  - [libircclient](https://github.com/alexlren/libircclient) stripping and overrides.
  - async functionality.
    - chat command bufferring
    - chat message parsing
    - response storage/memory allocation
  - cli interface
    - request oauth credentials for integration
    - get streamer's rock/paper/scissors position
    - generate and print results/reports to cli (as well as Twitch chat)
  - decide on a build system
    - cmake for developer friendliness
    - GNU Autotools for compatibility
- Documentation
- Create a frontend interface other than cli (a native gui or web interface, will probably be another repository ported in as a submodule).

### Contributing
Contributers are welcome to submit a PR or send patches to "GlidingShadow <<gliding.shadow.gaming@gmail.com>>". Anyone with experience in C is preferred, and I would especially like someone who is familiar with Windows programming API's (because I primarily use Linux exclusively, because reasons) for things like memory management and GUI.

### License
This project is licensed under GPL v3, while [libircclient](https://github.com/alexlren/libircclient) is under Library GPL (basically LGPL before it was LGPL). See [LICENSE](LICENSE) for details.

