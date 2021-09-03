# Installing the [Xcode] command line tools

Apple has a development tool called [Xcode] which is used to develop native
apps for macOS, iOS, and iPadOS. We don't need [Xcode] itself, but we do need
the [Xcode command line tools], which includes a C compiler and some other tools.

Type or copy and paste this command exactly like this into the terminal and press enter:

```sh
xcode-select --install
```

This should trigger a dialog box to appear asking if you want to install the
command line tools, click Ok and wait for the tools to finish installing.

Once this is finished, move on to [Installing homebrew]

[Installing homebrew]:homebrew-setup.md
[Xcode]:https://developer.apple.com/xcode/
[Xcode command line tools]:https://developer.apple.com/library/archive/technotes/tn2339/_index.html#//apple_ref/doc/uid/DTS40014588-CH1-WHAT_IS_THE_COMMAND_LINE_TOOLS_PACKAGE_
