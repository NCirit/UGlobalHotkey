## UGlobalHotkey

### Decription

UGlobalHotkey is an extension for Qt framework, which implements global hotkeys functionality for Windows Linux and MacOSX platforms.
It is written by [bakwc](https://github.com/bakwc), extracted from [Pastexen](https://github.com/bakwc/Pastexen) and turned into a shared library by me.

### Building from source

* You can either open project with QtCreator and press Build button
* Or build it using terminal:

```
qmake  
make
```

### Building with Cmake

Install `qt6-base-dev qt6-base-private-dev` and then:

```
mkdir build
cd build
cmake -G Ninja ..
ninja
```

### Usage example

```
UGlobalHotkeys *hotkeyManager = new UGlobalHotkeys(); 
hotkeyManager->RegisterHotkey("Ctrl+Shift+F12");
connect(hotkeyManager, &UGlobalHotkeys::Activated, [=](size_t id)
{
    qDebug() << "Activated: " << QString::number(id);
});
```

### License

UGlobalHotkey library is licensed as Public Domain, so you are free to do anything with it.
