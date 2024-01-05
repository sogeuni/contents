---
title: 7.5. Testing Your Knowledge of Tests
---

The systemwide xinitrc file can be used to launch the X server. This file contains quite a number of _if/then_ tests. The following is excerpted from an "ancient" version of xinitrc (_Red Hat 7.1_, or thereabouts).

```bash
if [ -f $HOME/.Xclients ]; then
  exec $HOME/.Xclients
elif [ -f /etc/X11/xinit/Xclients ]; then
  exec /etc/X11/xinit/Xclients
else
     # failsafe settings.  Although we should never get here
     # (we provide fallbacks in Xclients as well) it can't hurt.
     xclock -geometry 100x100-5+5 &
     xterm -geometry 80x50-50+150 &
     if [ -f /usr/bin/netscape -a -f /usr/share/doc/HTML/index.html ]; then
             netscape /usr/share/doc/HTML/index.html &
     fi
fi
```

Explain the _test_ constructs in the above snippet, then examine an updated version of the file, /etc/X11/xinit/xinitrc, and analyze the _if/then_ test constructs there. You may need to refer ahead to the discussions of [[textproc#^GREPREF|grep]], [[sedawk#^SEDREF|sed]], and [[regexp#^REGEXREF|regular expressions]].
