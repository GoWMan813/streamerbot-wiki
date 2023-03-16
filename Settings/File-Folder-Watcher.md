---
title: File/Folder Watcher
description: 
published: true
date: 2023-03-16T07:00:04.973Z
tags: 
editor: markdown
dateCreated: 2021-08-25T21:31:58.151Z
---

With the `File/Folder Watcher` feature you can specify an action to run whenever a file that matches the defined filter is modified

Folder watch actions that have been defined will show in this pane to indicate the `Folder being watched`, `The file filter`, is `Enabled` state and the **[Action](/Actions)** that will trigger when the conditions are met

![file-folder-watcher-018.png](/file-folder-watcher-018.png)

<kbd>Right-clicking</kbd> inside the pane opens the context menu

## Context Menu

---:|---
`Add` | Add a new folder watch definition
`Edit` | Open the `Edit File/Folder Watcher` dialogue to modify the highlighted entry | This is the same as <kbd>Double-Clicking</kbd> the entry
`Delete` | Delete the highlighted entry
`Set Action` | Shortcut to the `Select Action` dialogue
`Enabled` | Shortcut to set the Active state of the Folder Watch entry

## Edit File/Folder Watcher Dialogue
![file-folder-watcher-edit-018.png](/file-folder-watcher-edit-018.png)
Can only monitor specific files or Monitors entire folders and will trigger on every match defined in the filter

> Filters can be a generic or specific as required and uses the `*` symbol as a wildcard.
> eg. `*.*` will match all files in a folder, `*.txt` will match all text files, `some*.txt` will match all text files that begin with the word `some` and so on
{.is-success}

### Action Selector
![action-selector-018.png](/action-selector-018.png)

The action list can be filtered using the control in the upper right to help find what you need easier.

To assign an action, select it form the list and press the `Select` button

To unassign all action press the `Clear` button

-----

The action specified will get access to the following variables:

Name | Description
----:|:------------
`%changeType%` | The type of change | `Changed`, `Created`, `Deleted`
`%fullPath%` | The full path to the file
`%fileName%` | The file name with extension
`%name%` | The file name without the extention
`%empty%` | A boolean value indicating if the file is empty

If you have `As JSON` ticked, it will add all root elements as arguments.

If `As JSON` is not ticked, it will add the following variables if the JSON cannot be parsed:

Name | Description
----:|:------------
`%lineCount%` | The number of lines in the file
`%line#%` | The line of the file, replace # with the line number you want
`%lineEscaped#%` | The line of the file URL encoded, replace # with the line number you want

---

- [<i class="mdi mdi-chevron-left"></i> **Settings *Go Back***](/en/Settings)
{.btn-grid .my-5}