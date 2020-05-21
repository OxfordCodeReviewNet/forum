# Carrying out remote code reviews
Because in-person code reviews is not always possible, here is some advice on how to do it remotely!

## Visual Studio Code with Liveshare plugin

Visual Studio code is a code editor from Microsoft.
Liveshare is an extension for VS code that enables developers to work collaboratively on a piece of code.

- [Getting started with Visual Studio code](https://code.visualstudio.com/docs/introvideos/basics)
- [Getting started with Liveshare for VS code](https://www.digitalocean.com/community/tutorials/how-to-use-live-share-with-visual-studio-code)

## tmate.io
[tmate](https://tmate.io/) is a tool for sharing terminal sessions over the internet.
It is based on the famous [tmux](https://github.com/tmux/tmux/wiki) **t**erminal **mu**tiple**x**er.

To start sharing your termnial, simply enter in your terminal
```bash
tmate
```
which stars a tmux session inside your terminal (it shouldn't look very different except from the colored bar at the bottom).

Next, enter
```bash
tmate show-messages
```

```bash
$ tmate show-messages
Thu May 21 09:49:13 2020 [tmate] Connecting to ssh.tmate.io...
Thu May 21 09:49:13 2020 [tmate] Note: clear your terminal before sharing readonly access
Thu May 21 09:49:13 2020 [tmate] web session read only: https://tmate.io/t/ro-j2nMRX7qmFJePwDgNmvEWC4uQ
Thu May 21 09:49:13 2020 [tmate] ssh session read only: ssh ro-j2nMRX7qmFJePwDgNmvEWC4uQ@lon1.tmate.io
Thu May 21 09:49:13 2020 [tmate] web session: https://tmate.io/t/daSqRGCWXcZkyc9WunwebVXye
Thu May 21 09:49:13 2020 [tmate] ssh session: ssh daSqRGCWXcZkyc9WunwebVXye@lon1.tmate.io
$
```

To share your terminal, simply share one of the adresses with your collaborator.
For instance, for your collaborator to see your terminal live, their must enter
```bash
ssh ro-j2nMRX7qmFJePwDgNmvEWC4uQ@lon1.tmate.io
```
in theirs.
To view it in a web browser, they can visit `https://tmate.io/t/ro-j2nMRX7qmFJePwDgNmvEWC4uQ`.

- **ssh session read only** (recommended): Join the session through `ssh`, read only mode.
- **web session read only** (most straightforward solution): View terminal through a web browser. Still a bit unstable but when it works, it's great!
- **ssh session read only**: Join the session through `ssh`. The collaborator has write-acess to your terminal, and can therefore execute commands on your system!
- **web session** (not recommended): Allow access to your collaborator to your terminal through a web browser.

**Starting and sharing a tmate session**:

![tmate server side](tmate-server-side.gif)

**Joining a tmate session using ssh:**

![tmate client side](tmate-client-side.gif)

### Access denied. Check your ssh keys
To use tmate over ssh, each participant must have their pair of ssh keys set up.

Here's [a guide](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-1804) on how to do it (*only step 1 is required for using tmate*).

## Screen sharing
