
# Tips for configuring ROOT on VS code IDE

## Table of contents

- [Let VS Code recognize ROOT include paths](#Let-VS-Code-recognize-ROOT-include-paths)
- [ROOT File Viewer extension](#ROOT-File-Viewer-extension)

## Let VS Code recognize ROOT include paths

Many of you may have encountered a problem for which, when writing a ROOT macro on VS Code, ROOT include paths are not recognized by the IDE:

<img src="https://github.com/JustWhit3/useful-guides/blob/master/img/ROOT_vscode.png">

This ca be easily solved by following this passages:

1) Go on the top of your VS Code IDE and click on *View* -> *Command palette*. Then search for *Edit configurations (UI)* and click on it.

<img src="https://github.com/JustWhit3/useful-guides/blob/main/img/edit_config.png">

2) Search for *One include path per line* option and add a new line with the path to your ROOT directory, as in the example screenshot below:

<img src="https://github.com/JustWhit3/useful-guides/blob/main/img/include_path.png">

3) Save, close VS Code and reopen it and now the problem of ROOT include path recognition is disappeared.

## ROOT File Viewer extension

In case you have trouble visualizing ROOT histograms in the TBrowser, you can partially solve this by installing the *ROOT File Viewer* extension for VS Code.

<img src="https://github.com/JustWhit3/useful-guides/blob/main/img/ROOT_extension.png">

Thanks to this you can easily navigate through .root files histograms and visualize them, but you cannot perform operations between histograms directly from this visualizer. More information can be found [here](https://root.cern/blog/vscode-extension-announcement/).

<img src="https://github.com/JustWhit3/useful-guides/blob/main/img/vscode_extension.gif">