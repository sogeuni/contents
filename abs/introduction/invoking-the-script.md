---
title: 2.1. Invoking the script
draft: true
---

Having written the script, you can invoke it by **`sh scriptname`**, [^1] or alternatively **`bash scriptname`**. (Not recommended is using **`sh <scriptname`**, since this effectively disables reading from [[a-detailed-introduction-to-io-and-io-redirection#STDINOUTDEF|stdin]] within the script.) Much more convenient is to make the script itself directly executable with a [[basic#CHMODREF|chmod]].

Either:

**`chmod 555 scriptname`** (gives everyone read/execute permission) [^2]

or

**`chmod +rx scriptname`** (gives everyone read/execute permission)

**`chmod u+rx scriptname`** (gives only the script owner read/execute permission)

Having made the script executable, you may now test it by **`./scriptname`**. [^3] If it begins with a "sha-bang" line, invoking the script calls the correct command interpreter to run it.

As a final step, after testing and debugging, you would likely want to move it to `/usr/local/bin` (as _root_, of course), to make the script available to yourself and all other users as a systemwide executable. The script could then be invoked by simply typing **`scriptname [ENTER]`** from the command-line.

[^1]: Caution: invoking a _Bash_ script by **`sh scriptname`** turns off Bash-specific extensions, and the script may therefore fail to execute.

[^2]: A script needs _read_, as well as execute permission for it to run, since the shell needs to be able to read it.

[^3]: Why not simply invoke the script with **scriptname**? If the directory you are in ([[internal-variables#PWDREF|$PWD]]) is where scriptname is located, why doesn't this work? This fails because, for security reasons, the current directory (./) is not by default included in a user's [[internal-variables#PATHREF|$PATH]]. It is therefore necessary to explicitly invoke the script in the current directory with a **./scriptname**.
