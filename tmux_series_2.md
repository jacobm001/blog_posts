**Author:** Jacobm001

**Publish Status:** draft

**Suggested Tags:** raspberrypi, raspbian, tmux

# Tmux 102: Getting to know Tmux.

[Last week's article](https://raspberrypise.tumblr.com/post/141348857424/tmux-101-installing-from-source), discussed how to install Tmux from the source.  This week, we'll be focusing on Tmux's basic usage and look into some basic use cases for these features.

## Launching Tmux

### Open Tmux

Tmux is launched form a standard terminal. If you're in a desktop environment, you'll need to open a terminal, otherwise simply type the command `tmux`. At this point you should see a terminal that looks similar to what you're accustomed to, with a yellow-green bar on the bottom with some writing on it. Congrats, you've started your first Tmux session!

Now, before we go any further it's probably important to list some vocabulary:

- **session:** An instance of Tmux. You can have multiple sessions running at the same time, but in most cases you will only ever interact with one of them at a time.
- **window:** A window is similar to a web browser's tab.
- **pane:** The actual interactive shell provided by Tmux. By default, each window has one pane, but the window can be divided into multiple panes.

### What Does the Writing Mean?

Tmux manages to fit a surprising amount of information into a relatively small space. On the far right, we see a number (probably `0`) in brackets. This indicates our session name. By default, the session name is `0`. As you may have guesses, Tmux will increment that number for each open session. So if you detach this session, and start a second, the name of the new session would be `1`.

Next we see a list of the windows, and their names. Each window is given an auto incremented number, and by default its name is whatever application is currently running on the focused pane. The asterisk (`*`) indicates that window `0:bash` is active.

 
