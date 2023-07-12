# <img src="https://github.com/dcannizzaro/Beetlemania/assets/737638/d506e047-92c0-4103-9933-caba66fc8899" width="24"> Beetleman 

A real-time framework for interactive dialog with large language models (LLMs)

<img src="https://github.com/dcannizzaro/Beetlemania/assets/737638/3de87f86-48a5-4179-8b98-23f2d2b616fc" width="650">

&nbsp;

## Dashboard

The _Dashboard_ is the interactive web interface used for generating content in the system. It consists of the [server](https://github.com/dcannizzaro/Beetlemania/tree/main/dashboard) and [beetles](https://github.com/dcannizzaro/Beetlemania/tree/main/dashboard/beetles) modules written in Python, and a web browser client, written in JS/CSS/HTML and served via [Flask](https://flask.palletsprojects.com/en/2.3.x/). The _Dashboard_ communicates with The _Orchestrator_ (and sometimes with web-clients) via sockets

The _Dashboard_ supports the following features:
* Login/authentication of users in database
* Editing of initial prompts (system/user) for a scene
* Ongoing creation/editing of actions (interactive prompts)
* Generation of dialog from LLMs via prompts/actions
* Staging, editing and publishing of lines of dialog to the _Orchestrator_
* Saving/loading of scenes as files with history, parameters, etc (JSON)
* _Automatic_ mode to allow scenes to run unattended
* Handling of memory/context for memory-less LLMs (e.g. GPT-3.5/4)

Developers: see [this page](https://github.com/dcannizzaro/Beetlemania/blob/main/dashboard/README.md#the-dashboard) for info on building/running the _Dashboard_ and [this page](https://github.com/dcannizzaro/Beetlemania/blob/main/dashboard/server/config.py) for config options

&nbsp;

## Orchestrator

The _Orchestrator_ is monolithic Python application responsible for scheduling and managing scenes. It communicates with two OBS instances (foreground and background) and the _Dashboard_ via sockets

The _Orchestrator_  supports the following features:
* Triggering, switching and loading of scenes according to a remote schedule
* Triggering of videos on foreground/background OBS instances
* Control of timing, placement, fonts, etc. for dialog subtitles
* Control of text-to-speech generation and voice/character mapping
* Streaming of content to Twitch and other platforms

Developers: see [this page](https://github.com/dcannizzaro/Beetlemania/blob/main/orchestrator/README.md#the-orchestrator) for info on building/running the _Orchestrator_ and [this page](https://github.com/dcannizzaro/Beetlemania/blob/main/orchestrator/config.json) for config options
 
&nbsp;

