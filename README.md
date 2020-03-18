# guiserver
native GUIs for scripting languages

guiserver is a standalone binary that you can start from a scripting language, then use to create native windows. Communication is through simple plain text or JSON-RPC 2.0 (like a [language server](https://langserver.org/).) The protocol for guiserver is the same on all platforms, so your scripts don't need to change. Distribute your scripts, runtime and guiserver together for a native GUI.

guiserver can be made for different combinations of platform, architecture and toolkit. For example, linux-x64-QT, windows-x64-win32, tinycore-linux-x86-fltk, etc... Any platform can be supported by making a guiserver for that platforms native toolkit. This strategy supports obscure platforms allowing them to create their own guiserver, and future changes by using an updated guiserver that speaks the same protocols. This also lets the user choose the toolkit, by providing their own guiserver; a BSD user could use a QT version of guiserver on a Gnome desktop. Finally, guiserver preserves the users accessibility settings, font and theme choices.

guiserver is different from wxwidgets because it's not a library you link to, but a stand-alone executable that can be updated or replaced by the user after distribution. The abstraction of toolkits is also different: guiserver will try to use the lowest common denominator of functionality with polyfills.

Status: `planning`

## Goals
* create GUIs with the native toolkit
* speak JSON-RPC and a relaxed text language
* simple communication through stdin/stdout, tcp or shared memory
* presise layout or an easy/automatic method
