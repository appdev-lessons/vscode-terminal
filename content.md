# The terminal in VSCode

We are using the [VSCode](https://code.visualstudio.com/) integrated code editor in this course. Whenever you boot up a fresh Codespace, this is the application that you are interacting with to explore your files, Git version control (commit, push, etc.), edit your code, and view your live app preview. 

Let's discuss the all important **terminal** integrated into VSCode.

## Codespace (VSCode) layout

Whenever you boot up a fresh Codespace, [Visual Studio Code](https://code.visualstudio.com/) (a.k.a. VSCode) is the application that you are interacting with.

The basic components of the VSCode window are the three **panes**:

* the **left pane** 
  * containing the **file explorer** and **source control tabs** (where you create and open files and visit your Git version control)
* the **top pane** 
  * containing the **code editor tabs** (where you type and edit files in your codebase)
* the **bottom pane** 
  * containing the **terminal** and **ports tabs** (where you run a live app server on a port with `rackup` and run `rake grade`)

<!-- ![](/assets/vscode-layout.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686338851/vscode-layout_yh62tb.png)
{: .bleed-full }

### Reopen a pane

Sometimes you might accidentally close out of the explorer (left pane) or terminal (bottom pane).

To reopen them, there are keyboard shortcuts to close and reopen:

* <kbd>Ctrl</kbd> (Windows) or <kbd>Cmd</kbd> (Mac) + <kbd>B</kbd> for left pane, 
* <kbd>Ctrl</kbd> (Windows) or <kbd>Cmd</kbd> (Mac) + <kbd>J</kbd> for bottom pane.

But, you can always click on the top left hamburger menu to bring up the VSCode options and visit "View" to reopen:

<!-- ![](/assets/vscode-reopen-editor-or-terminal.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686338878/vscode-reopen-editor-or-terminal_ekhafk.png)
{: .bleed-full }

## The terminal

The term "terminal" is a bit squishy, you may also hear it called the command-line, command prompt, or shell, among other terms. In this course, we typically use the term **bash prompt** since that is the specific terminal program that we are interacting with most often. 

All of these usually mean the same thing: A place for you to type commands ("instructions") to be run by the underlying operating system or coding environment.

### The terminal layout

Take a moment to read about the all-important, but perhaps unfamiliar, terminal tab in the bottom pane of the VSCode window.

In the terminal tab, we have:

<!-- ![](/assets/terminal-hello-world-layout.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1689097394/terminal-hello-world-layout_pin2jy.png)
{: .bleed-full }

* The GitHub repo name.
* The current git "branch", or version of the code, that you are on (usually this will be `main`).
* The `%` sign, or **bash prompt**. 
    * `bash` is a program running at the operating system level that allows you to enter instructions to the computer.
    * You may see other styles of **command prompt**, like a `$` or `>` symbol. If you see one of these symbols at the end of your terminal prompt, it means the terminal can be typed into and new commands can be run.
* A `+` button icon for opening additional fresh bash prompts in tabs.
* If you open another bash tab, you will see a navigation pane to click between them.

### Server and Ports

I have two bash prompt environments open in the terminal tab ([more about terminal environments below](#terminal-environments){: target="_self"}). Clicking on the second bash prompt, we see I have `bin/dev` running, which is my live application preview server for Rails apps (we will build up to this from `rackup`, then `ruby app.rb`):

<!-- ![](/assets/terminal-second-bash-tab.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686338918/terminal-second-bash-tab_d8v5y2.png)
{: .bleed-full }

Note that we no longer have access to the `%`-symbol bash prompt, because this terminal is now dedicated to running the live app preview.

If you want to cancel the web server, thus closing your live app preview, and returning you to the bash prompt to enter another command, you can just press:

* <kbd>Ctrl</kbd> + <kbd>C</kbd>

That's a very important command: it will cancel any currently running terminal process if your terminal gets stuck doing something and you want access to the prompt again to enter new commands.

With the live app preview running, to open the live preview in a new browser tab, visit the "Ports" tab in the bottom pane, look for the port with a green dot 🟢 on the left side (indicating that it is active), and hover over the "Local Address" column, then click the globe 🌐 button to "Open in Browser":

![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1688656108/ports-tab_cfaa1k.png)

This is very useful if I ever accidentally close the browser tab running the live app preview: **Just click this button in the Ports tab to reopen the preview, assuming you have an active web server terminal running**.

#### A note about ports

What is a port exactly? 

You can think of a "network port" as something that allows types of programs to run. Or that certain types of programs need to run on a port.

The web server of a Rails app runs on a port (port 3000 by default). This allows us to visit the web application in the browser using the IP Address of the computer _plus_ the port number.

Since we're working in Codespaces (and not running the web server on our own computer), Codespaces gives us a URL to access the web application. 

Locally, when your computer connects to a network, you get an address (an IP address, like `192.168.8.9`) that other computers use to reach programs running on it. But you don’t want to be limited to only one program being able to talk to the outside world, so you can further subdivide your address by using ports, usually a four digit number that you append after a colon: `192.178.8.9:3000` is the one we usually assign to our development web server.

### Close unused terminals

Ever in a situation where you have a bunch of terminals open and you're getting confused about what's running where? Likely you've been using that `+` button to create new terminals many times, and most of the open terminals aren't necessary anymore.

Hover over the unused terminal and click the trash icon to close it:

<!-- ![](/assets/terminal-close-bash.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686338917/terminal-close-bash_m6snsk.png)

I like to keep **maximum ~3 terminals open** at any given time: one for entering bash prompt commands like `rake grade`; one for running the live app preview with a web server; and another for exploring my Ruby code or database with `irb`, `pry`, `bin/console`, `rails console`, etc.

### Terminal environments

You can think of the terminal "environment" like a list of settings and configurations that change what the terminal does.

For instance, here I have three terminals open:

* Our standard bash prompt environment for entering commands like `rake grade` or `bin/dev`
* `pry` for interacting with a database (we could also run `bin/console` or `rails console` for that)
* `irb` for typing in pure Ruby code

<!-- ![](/assets/terminal-environments.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686338917/terminal-environments_aoo9b4.png)
{: .bleed-full }

The `irb` (or `pry`, `bin/console`, `rails console`) command will change the bash prompt from

```
%
```

to (`irb`)

```
3.2.1 :001 >
```

or (console commands)

```
[1] pry(main)>
```

_It's important to always know which environment you are in._ **I cannot enter `rake grade` in the `irb` terminal, which has the `>` command prompt!** 

If I wanted to kill the `irb` environment and return to `bash` to enter `rake grade` or `bin/dev`, I need to type: `exit` to return to my standard bash prompt:

<!-- ![](/assets/terminal-environments-exit.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686338918/terminal-environments-exit_a8j029.png)
{: .bleed-full }

You can also always open a new bash prompt for entering non-Ruby or database commands with the `+` icon. But, again, [avoid opening excessive terminals](#close-unused-terminals){: target="_self"}.

## Pagination from long commands in your database console

Sometimes when the output of a Ruby expression is very long, `rails console` is going to paginate it for you. You will have a `:` prompt when this is true, and you can hit <kbd>return</kbd> to scroll through line by line, or <kbd>space</kbd> to scroll through page by page.

When you reach the end of the output, you'll see `(END)`.

**To get back to the regular prompt so that you can enter your next command, just hit <kbd>q</kbd> at any time.**

## Exit or reload after model changes

If you are in `rails console` and then make a change to a model (for example, you define a new method or fix a syntax error), then, annoyingly, you have to `exit` and then start a new `rails console` to pick up the new logic. The console is not live-loading with changes we make to our app. Alternatively, you can use the `reload!` method.

## Useful keyboard shortcuts at the terminal

### Tab completion

If you are running some pure Ruby `.rb` file, and there are multiple files with similar names or just a long name that you don't want to type all of, start typing the name and then just press <kbd>Tab</kbd> on your keyboard to let the terminal complete the name. You rarely need to type full filenames out — use **tab completion**!

### Previous commands

To re-run a previous command at the terminal, you can use the <kbd>Up ↑</kbd> and <kbd>Down ↓</kbd> arrow keys to look at the history of commands you've run in a terminal.

This is very helpful for running `rake grade` if you are doing it several times.

### Clear Terminal

Mac OS: <kbd>⌘</kbd> + <kbd>K</kbd>

Windows: <kbd>Ctrl</kbd> + <kbd>K</kbd>

<!-- ![](assets/technical-setup/clear_terminal.gif) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1677022025/clear_terminal_rhjozb.gif)

### Interrupt command

If something goes wrong with a terminal program (i.e. you made a typo, a program gets stuck in an infinite loop, etc), you can generally interrupt it with <kbd>Ctrl</kbd> + <kbd>C</kbd>:

<!-- ![](assets/technical-setup/ctrl-c-to-quit.gif) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1677022070/ctrl-c-to-quit_qyjv7f.gif)

### Q to exit

When the output of a terminal command is too tall for a terminal tab to display at once, it paginates. Press <kbd>Space</kbd> to step through it one page at a time, or <kbd>Q</kbd> to quit and get back to the terminal prompt so that you can execute your next command.

Mac OS, Windows: <kbd>Q</kbd>

<!-- ![](assets/technical-setup/q-to-exit.gif) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1677022080/q-to-exit_x8qeys.gif)

### Command Palette

The most important thing to memorize is how to open the **Command Palette**, which will allow you to fuzzy search within for all other commands. If the command has a keyboard shortcut mapped to it, the shortcut will be displayed to the right. This is the best way to learn the keyboard shortcuts for the commands that you use most frequently.

Mac OS: <kbd>⌘</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd>

Windows: <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd>

<!-- ![](assets/technical-setup/gitpod-command-palette.gif) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1677022098/gitpod-command-palette_mlwknm.gif)

### Quick open file

To quickly jump to a file:

Mac OS: <kbd>⌘</kbd> + <kbd>P</kbd>

Windows: <kbd>Ctrl</kbd> + <kbd>P</kbd>

And then fuzzily search for its name. For example, you could type "phco" to get to **ph**otos_**co**ntroller.rb and the list would quickly narrow to bring that file to the top of the list.

<!-- ![](assets/technical-setup/open_file.gif) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1677022111/open_file_e1qts7.gif)
