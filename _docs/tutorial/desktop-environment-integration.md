---
version: v1.4.13
permalink: /docs/tutorial/desktop-environment-integration/
category: Tutorial
redirect_from:
  - /docs/v0.37.8/tutorial/desktop-environment-integration/
  - /docs/v0.37.7/tutorial/desktop-environment-integration/
  - /docs/v0.37.6/tutorial/desktop-environment-integration/
  - /docs/v0.37.5/tutorial/desktop-environment-integration/
  - /docs/v0.37.4/tutorial/desktop-environment-integration/
  - /docs/v0.37.3/tutorial/desktop-environment-integration/
  - /docs/v0.36.12/tutorial/desktop-environment-integration/
  - /docs/v0.37.1/tutorial/desktop-environment-integration/
  - /docs/v0.37.0/tutorial/desktop-environment-integration/
  - /docs/v0.36.11/tutorial/desktop-environment-integration/
  - /docs/v0.36.10/tutorial/desktop-environment-integration/
  - /docs/v0.36.9/tutorial/desktop-environment-integration/
  - /docs/v0.36.8/tutorial/desktop-environment-integration/
  - /docs/v0.36.7/tutorial/desktop-environment-integration/
  - /docs/v0.36.6/tutorial/desktop-environment-integration/
  - /docs/v0.36.5/tutorial/desktop-environment-integration/
  - /docs/v0.36.4/tutorial/desktop-environment-integration/
  - /docs/v0.36.3/tutorial/desktop-environment-integration/
  - /docs/v0.35.5/tutorial/desktop-environment-integration/
  - /docs/v0.36.2/tutorial/desktop-environment-integration/
  - /docs/v0.36.0/tutorial/desktop-environment-integration/
  - /docs/v0.35.4/tutorial/desktop-environment-integration/
  - /docs/v0.35.3/tutorial/desktop-environment-integration/
  - /docs/v0.35.2/tutorial/desktop-environment-integration/
  - /docs/v0.34.4/tutorial/desktop-environment-integration/
  - /docs/v0.35.1/tutorial/desktop-environment-integration/
  - /docs/v0.34.3/tutorial/desktop-environment-integration/
  - /docs/v0.34.2/tutorial/desktop-environment-integration/
  - /docs/v0.34.1/tutorial/desktop-environment-integration/
  - /docs/v0.34.0/tutorial/desktop-environment-integration/
  - /docs/v0.33.9/tutorial/desktop-environment-integration/
  - /docs/v0.33.8/tutorial/desktop-environment-integration/
  - /docs/v0.33.7/tutorial/desktop-environment-integration/
  - /docs/v0.33.6/tutorial/desktop-environment-integration/
  - /docs/v0.33.4/tutorial/desktop-environment-integration/
  - /docs/v0.33.3/tutorial/desktop-environment-integration/
  - /docs/v0.33.2/tutorial/desktop-environment-integration/
  - /docs/v0.33.1/tutorial/desktop-environment-integration/
  - /docs/v0.33.0/tutorial/desktop-environment-integration/
  - /docs/v0.32.3/tutorial/desktop-environment-integration/
  - /docs/v0.32.2/tutorial/desktop-environment-integration/
  - /docs/v0.31.2/tutorial/desktop-environment-integration/
  - /docs/v0.31.0/tutorial/desktop-environment-integration/
  - /docs/v0.30.4/tutorial/desktop-environment-integration/
  - /docs/v0.29.2/tutorial/desktop-environment-integration/
  - /docs/v0.29.1/tutorial/desktop-environment-integration/
  - /docs/v0.28.3/tutorial/desktop-environment-integration/
  - /docs/v0.28.2/tutorial/desktop-environment-integration/
  - /docs/v0.28.1/tutorial/desktop-environment-integration/
  - /docs/v0.28.0/tutorial/desktop-environment-integration/
  - /docs/v0.27.3/tutorial/desktop-environment-integration/
  - /docs/v0.27.2/tutorial/desktop-environment-integration/
  - /docs/v0.27.1/tutorial/desktop-environment-integration/
  - /docs/v0.27.0/tutorial/desktop-environment-integration/
  - /docs/v0.26.1/tutorial/desktop-environment-integration/
  - /docs/v0.26.0/tutorial/desktop-environment-integration/
  - /docs/v0.25.3/tutorial/desktop-environment-integration/
  - /docs/v0.25.2/tutorial/desktop-environment-integration/
  - /docs/v0.25.1/tutorial/desktop-environment-integration/
  - /docs/v0.25.0/tutorial/desktop-environment-integration/
  - /docs/v0.24.0/tutorial/desktop-environment-integration/
  - /docs/v0.23.0/tutorial/desktop-environment-integration/
  - /docs/v0.22.3/tutorial/desktop-environment-integration/
  - /docs/v0.22.2/tutorial/desktop-environment-integration/
  - /docs/v0.22.1/tutorial/desktop-environment-integration/
  - /docs/v0.21.3/tutorial/desktop-environment-integration/
  - /docs/v0.21.2/tutorial/desktop-environment-integration/
  - /docs/v0.21.1/tutorial/desktop-environment-integration/
  - /docs/v0.21.0/tutorial/desktop-environment-integration/
  - /docs/v0.20.8/tutorial/desktop-environment-integration/
  - /docs/v0.20.7/tutorial/desktop-environment-integration/
  - /docs/v0.20.6/tutorial/desktop-environment-integration/
  - /docs/v0.20.5/tutorial/desktop-environment-integration/
  - /docs/v0.20.4/tutorial/desktop-environment-integration/
  - /docs/v0.20.3/tutorial/desktop-environment-integration/
  - /docs/v0.20.2/tutorial/desktop-environment-integration/
  - /docs/v0.20.1/tutorial/desktop-environment-integration/
  - /docs/v0.20.0/tutorial/desktop-environment-integration/
  - /docs/latest/tutorial/desktop-environment-integration/
source_url: >-
  https://github.com/electron/electron/blob/master/docs/tutorial/desktop-environment-integration.md
title: Desktop Environment Integration
excerpt: >-
  Applications define tasks based on both the program&apos;s features and the
  key
      things a user is expected to do with them. Tasks should be context-free, in
      that the application does not need to be running for them to work. They
      should also be the statistically most common actions that a normal user would
      perform in an application, such as compose an email message or open the
      calendar in a mail program, create a new document in a word processor, launch
      an application in a certain mode, or launch one of its subcommands. An
      application should not clutter the menu with advanced features that standard
      users won&apos;t need or one-time actions such as registration. Do not use tasks
      for promotional items such as upgrades or special offers.
sort_title: desktop-environment-integration
---
# Desktop Environment Integration

Different operating systems provide different features for integrating desktop applications into their desktop environments. For example, on Windows, applications can put shortcuts in the JumpList of task bar, and on Mac, applications can put a custom menu in the dock menu.

This guide explains how to integrate your application into those desktop environments with Electron APIs.

## Notifications (Windows, Linux, macOS)

All three operating systems provide means for applications to send notifications to the user. Electron conveniently allows developers to send notifications with the [HTML5 Notification API](https://notifications.spec.whatwg.org/), using the currently running operating system's native notification APIs to display it.

**Note:** Since this is an HTML5 API it is only available in the renderer process.

```javascript
let myNotification = new Notification('Title', {
  body: 'Lorem Ipsum Dolor Sit Amet'
})

myNotification.onclick = () => {
  console.log('Notification clicked')
}
```

While code and user experience across operating systems are similar, there are fine differences.

### Windows

*   On Windows 10, notifications "just work".
*   On Windows 8.1 and Windows 8, a shortcut to your app, with a [Application User Model ID](https://msdn.microsoft.com/en-us/library/windows/desktop/dd378459(v=vs.85).aspx), must be installed to the Start screen. Note, however, that it does not need to be pinned to the Start screen.
*   On Windows 7, notifications are not supported. You can however send "balloon notifications" using the [Tray API]({{site.baseurl}}/docs/api/tray#traydisplayballoonoptions-windows).

Furthermore, the maximum length for the notification body is 250 characters, with the Windows team recommending that notifications should be kept to 200 characters.

### Linux

Notifications are sent using `libnotify`, it can show notifications on any desktop environment that follows [Desktop Notifications Specification](https://developer.gnome.org/notification-spec/), including Cinnamon, Enlightenment, Unity, GNOME, KDE.

### macOS

Notifications are straight-forward on macOS, you should however be aware of [Apple's Human Interface guidelines regarding notifications](https://developer.apple.com/library/mac/documentation/UserExperience/Conceptual/OSXHIGuidelines/NotificationCenter.html).

Note that notifications are limited to 256 bytes in size - and will be truncated if you exceed that limit.

## Recent documents (Windows & macOS)

Windows and macOS provide easy access to a list of recent documents opened by the application via JumpList or dock menu, respectively.

**JumpList:**

![JumpList Recent Files](http://i.msdn.microsoft.com/dynimg/IC420538.png)

**Application dock menu:**

<img src="https://cloud.githubusercontent.com/assets/639601/5069610/2aa80758-6e97-11e4-8cfb-c1a414a10774.png" height="353" width="428" >

To add a file to recent documents, you can use the [app.addRecentDocument]({{site.baseurl}}/docs/api/app#appaddrecentdocumentpath-os-x-windows) API:

```javascript
const {app} = require('electron')
app.addRecentDocument('/Users/USERNAME/Desktop/work.type')
```

And you can use [app.clearRecentDocuments]({{site.baseurl}}/docs/api/app#appclearrecentdocuments-os-x-windows) API to empty the recent documents list:

```javascript
const {app} = require('electron')
app.clearRecentDocuments()
```

### Windows Notes

In order to be able to use this feature on Windows, your application has to be registered as a handler of the file type of the document, otherwise the file won't appear in JumpList even after you have added it. You can find everything on registering your application in [Application Registration](http://msdn.microsoft.com/en-us/library/windows/desktop/ee872121(v=vs.85).aspx).

When a user clicks a file from the JumpList, a new instance of your application will be started with the path of the file added as a command line argument.

### macOS Notes

When a file is requested from the recent documents menu, the `open-file` event of `app` module will be emitted for it.

## Custom Dock Menu (macOS)

macOS enables developers to specify a custom menu for the dock, which usually contains some shortcuts for commonly used features of your application:

**Dock menu of Terminal.app:**

<img src="https://cloud.githubusercontent.com/assets/639601/5069962/6032658a-6e9c-11e4-9953-aa84006bdfff.png" height="354" width="341" >

To set your custom dock menu, you can use the `app.dock.setMenu` API, which is only available on macOS:

```javascript
const {app, Menu} = require('electron')

const dockMenu = Menu.buildFromTemplate([
  {label: 'New Window', click () { console.log('New Window') }},
  {label: 'New Window with Settings',
    submenu: [
      {label: 'Basic'},
      {label: 'Pro'}
    ]
  },
  {label: 'New Command...'}
])
app.dock.setMenu(dockMenu)
```

## User Tasks (Windows)

On Windows you can specify custom actions in the `Tasks` category of JumpList, as quoted from MSDN:

> Applications define tasks based on both the program's features and the key things a user is expected to do with them. Tasks should be context-free, in that the application does not need to be running for them to work. They should also be the statistically most common actions that a normal user would perform in an application, such as compose an email message or open the calendar in a mail program, create a new document in a word processor, launch an application in a certain mode, or launch one of its subcommands. An application should not clutter the menu with advanced features that standard users won't need or one-time actions such as registration. Do not use tasks for promotional items such as upgrades or special offers.
> 
> It is strongly recommended that the task list be static. It should remain the same regardless of the state or status of the application. While it is possible to vary the list dynamically, you should consider that this could confuse the user who does not expect that portion of the destination list to change.

**Tasks of Internet Explorer:**

![IE](http://i.msdn.microsoft.com/dynimg/IC420539.png)

Unlike the dock menu in macOS which is a real menu, user tasks in Windows work like application shortcuts such that when user clicks a task, a program will be executed with specified arguments.

To set user tasks for your application, you can use [app.setUserTasks]({{site.baseurl}}/docs/api/app#appsetusertaskstasks-windows) API:

```javascript
const {app} = require('electron')
app.setUserTasks([
  {
    program: process.execPath,
    arguments: '--new-window',
    iconPath: process.execPath,
    iconIndex: 0,
    title: 'New Window',
    description: 'Create a new window'
  }
])
```

To clean your tasks list, just call `app.setUserTasks` with an empty array:

```javascript
const {app} = require('electron')
app.setUserTasks([])
```

The user tasks will still show even after your application closes, so the icon and program path specified for a task should exist until your application is uninstalled.

## Thumbnail Toolbars

On Windows you can add a thumbnail toolbar with specified buttons in a taskbar layout of an application window. It provides users a way to access to a particular window's command without restoring or activating the window.

From MSDN, it's illustrated:

> This toolbar is simply the familiar standard toolbar common control. It has a maximum of seven buttons. Each button's ID, image, tooltip, and state are defined in a structure, which is then passed to the taskbar. The application can show, enable, disable, or hide buttons from the thumbnail toolbar as required by its current state.
> 
> For example, Windows Media Player might offer standard media transport controls such as play, pause, mute, and stop.

**Thumbnail toolbar of Windows Media Player:**

![player](https://i-msdn.sec.s-msft.com/dynimg/IC420540.png)

You can use [BrowserWindow.setThumbarButtons]({{site.baseurl}}/docs/api/browser-window#winsetthumbarbuttonsbuttons-windows-7) to set thumbnail toolbar in your application:

```javascript
const {BrowserWindow} = require('electron')
const path = require('path')

let win = new BrowserWindow({
  width: 800,
  height: 600
})

win.setThumbarButtons([
  {
    tooltip: 'button1',
    icon: path.join(__dirname, 'button1.png'),
    click () { console.log('button1 clicked') }
  },
  {
    tooltip: 'button2',
    icon: path.join(__dirname, 'button2.png'),
    flags: ['enabled', 'dismissonclick'],
    click () { console.log('button2 clicked.') }
  }
])
```

To clean thumbnail toolbar buttons, just call `BrowserWindow.setThumbarButtons` with an empty array:

```javascript
const {BrowserWindow} = require('electron')
let win = new BrowserWindow()
win.setThumbarButtons([])
```

## Unity Launcher Shortcuts (Linux)

In Unity, you can add custom entries to its launcher via modifying the `.desktop` file, see [Adding Shortcuts to a Launcher](https://help.ubuntu.com/community/UnityLaunchersAndDesktopFiles#Adding_shortcuts_to_a_launcher).

**Launcher shortcuts of Audacious:**

![audacious](https://help.ubuntu.com/community/UnityLaunchersAndDesktopFiles?action=AttachFile&do=get&target=shortcuts.png)

## Progress Bar in Taskbar (Windows, macOS, Unity)

On Windows a taskbar button can be used to display a progress bar. This enables a window to provide progress information to the user without the user having to switch to the window itself.

On macOS the progress bar will be displayed as a part of the dock icon.

The Unity DE also has a similar feature that allows you to specify the progress bar in the launcher.

**Progress bar in taskbar button:**

![Taskbar Progress Bar](https://cloud.githubusercontent.com/assets/639601/5081682/16691fda-6f0e-11e4-9676-49b6418f1264.png)

To set the progress bar for a Window, you can use the [BrowserWindow.setProgressBar]({{site.baseurl}}/docs/api/browser-window#winsetprogressbarprogress) API:

```javascript
const {BrowserWindow} = require('electron')
let win = new BrowserWindow()
win.setProgressBar(0.5)
```

## Icon Overlays in Taskbar (Windows)

On Windows a taskbar button can use a small overlay to display application status, as quoted from MSDN:

> Icon overlays serve as a contextual notification of status, and are intended to negate the need for a separate notification area status icon to communicate that information to the user. For instance, the new mail status in Microsoft Outlook, currently shown in the notification area, can now be indicated through an overlay on the taskbar button. Again, you must decide during your development cycle which method is best for your application. Overlay icons are intended to supply important, long-standing status or notifications such as network status, messenger status, or new mail. The user should not be presented with constantly changing overlays or animations.

**Overlay on taskbar button:**

![Overlay on taskbar button](https://i-msdn.sec.s-msft.com/dynimg/IC420441.png)

To set the overlay icon for a window, you can use the [BrowserWindow.setOverlayIcon]({{site.baseurl}}/docs/api/browser-window#winsetoverlayiconoverlay-description-windows-7) API:

```javascript
const {BrowserWindow} = require('electron')
let win = new BrowserWindow()
win.setOverlayIcon('path/to/overlay.png', 'Description for overlay')
```

## Flash Frame (Windows)

On Windows you can highlight the taskbar button to get the user's attention. This is similar to bouncing the dock icon on macOS. From the MSDN reference documentation:

> Typically, a window is flashed to inform the user that the window requires attention but that it does not currently have the keyboard focus.

To flash the BrowserWindow taskbar button, you can use the [BrowserWindow.flashFrame]({{site.baseurl}}/docs/api/browser-window#winflashframeflag) API:

```javascript
const {BrowserWindow} = require('electron')
let win = new BrowserWindow()
win.once('focus', () => win.flashFrame(false))
win.flashFrame(true)
```

Don't forget to call the `flashFrame` method with `false` to turn off the flash. In the above example, it is called when the window comes into focus, but you might use a timeout or some other event to disable it.

## Represented File of Window (macOS)

On macOS a window can set its represented file, so the file's icon can show in the title bar and when users Command-Click or Control-Click on the title a path popup will show.

You can also set the edited state of a window so that the file icon can indicate whether the document in this window has been modified.

**Represented file popup menu:**

<img src="https://cloud.githubusercontent.com/assets/639601/5082061/670a949a-6f14-11e4-987a-9aaa04b23c1d.png" height="232" width="663" >

To set the represented file of window, you can use the [BrowserWindow.setRepresentedFilename]({{site.baseurl}}/docs/api/browser-window#winsetrepresentedfilenamefilename-os-x) and [BrowserWindow.setDocumentEdited]({{site.baseurl}}/docs/api/browser-window#winsetdocumenteditededited-os-x) APIs:

```javascript
const {BrowserWindow} = require('electron')
let win = new BrowserWindow()
win.setRepresentedFilename('/etc/passwd')
win.setDocumentEdited(true)
```

## Dragging files out of the window

For certain kinds of apps that manipulate on files, it is important to be able to drag files from Electron to other apps. To implement this feature in your app, you need to call `webContents.startDrag(item)` API on `ondragstart` event.

In web page:

```html
<a href="#" id="drag">item</a>
<script type="text/javascript" charset="utf-8">
  document.getElementById('drag').ondragstart = (event) => {
    event.preventDefault()
    ipcRenderer.send('ondragstart', '/path/to/item')
  }
</script>
```

In the main process:

```javascript
const {ipcMain} = require('electron')
ipcMain.on('ondragstart', (event, filePath) => {
  event.sender.startDrag({
    file: filePath,
    icon: '/path/to/icon.png'
  })
})
```
