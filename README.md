# VSCode Keyboard Shortcut Setup For DragonRuby
##VSCode Keyboard Shortcut Setup Tutorial For DragonRuby

### Adding the Keyboard Shortcut
In VSCode add the following to your User level keybindings settings file, easiest way to get to is to click the gear icon at the bottom of a workspace window

<img width="68" height="85" alt="image" src="https://github.com/user-attachments/assets/7f6c8fbd-2c3e-429d-ab2f-3dbce3948249" />

Then Select 

Keyboard Shortcuts

(or by default press Command-K then Command-S)

<img width="306" height="304" alt="image" src="https://github.com/user-attachments/assets/e3f74e37-aff0-4510-803c-87451e616b0a" />

After that, click on the following icon at the top right of they editor

<img width="162" height="66" alt="image" src="https://github.com/user-attachments/assets/d698f228-af87-4cf7-a904-5e7c9d4da426" />

add the following to the file:

```json
// Place your key bindings in this file to override the defaults
[
    {
        "key": "cmd+r",
        "command": "workbench.action.tasks.runTask",
        "args":"Run Game"
    },
]
```

### Run File
next create a "run" file in the root directory of your DragonRuby Project (not in mygame):

```sh
#!/bin/sh
exec ./dragonruby mygame/
```

save it and make it executable via the Terminal:

```sh
chmod +x run
```

### Adding the Run Game Task
Finally in your `.code-workspace` file (create the folder and file if necessary) add the following json:

```json
"tasks": {
    // See https://go.microsoft.com/fwlink/?LinkId=733558
    // for the documentation about the tasks.json format
    "version": "2.0.0",
    "tasks": [
      {
        "label": "Run Game",
        "type": "shell",
        "command": "${workspaceRoot}/run",
        "problemMatcher": []
      },
    ]
  }
```

after that, save your `<file name here>.code-workspace` file

### Conclusion
Now when you press `Command-R` the Run Game task should be run by default and allows rapid checking of changes to your edited code
