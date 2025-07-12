## Working Idea
	- 10th June 2025 - node.js starts the process, opens a shell script and runs the python script. The script and the tensorflow task list is packaged in with **Pyinstaller** that packages these two files in an executable that doesn't require downloading libraries and other things in the user's side.
	- The solution is to launch the face-tracker and then immediately "detach" it, letting it run completely on its own in the background. The Node.js script's only job will be to launch it and then listen for OSC data, without maintaining a fragile I/O connection. This is the standard and most stable way to manage long-running background tasks.
-
- ## Ideas / Brainstorming / Thinking
	- Need to find how I can run the script on a server (?) and simply receive the OSC values in the [[amxd Patch]]
	- Search if there is a way to automatically trigger a pyhton script from within an [[amxd Patch]]
	- Potentially found out that **pyinstaller** (https://pyinstaller.org/en/stable/) bundles a Python application and all its dependencies into a single package. The user can run the packaged app without installing a Python interpreter or any modules.
-
-