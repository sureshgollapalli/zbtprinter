# zbtprinter
A Cordova/Phonegap driver for Zebra bluetooth printers

This is a fork of https://github.com/mmilidoni/zbtprinter with discovery

##Usage
You can find Zebra printer using:

```
cordova.plugins.zbtprinter.find(function(mac) { 
        alert(mac); 
    }, function(fail) { 
        alert(fail); 
    }
);
```

You can send data in ZPL Zebra Programing Language:

```
cordova.plugins.zbtprinter.print("AC:3F:A4:1D:7A:5C", "^XA^FO10,10^AFN,26,13^FDHello, World!^FS^XZ",
    function(success) { 
        alert("Print ok"); 
    }, function(fail) { 
        alert(fail); 
    }
);
```

##Install
###Cordova

```
cordova plugin add https://github.com/mmilidoni/zbtprinter.git
```

###Very important!

This plugin is in developer version, you need to set MAC Address of your printer at following file:

```
src/android/it/zenitlab/cordova/plugins/zbtprinter/ZebraBluetoothPrinter.java
```

##ZPL - Zebra Programming Language
For more information about ZPL please see the  [PDF Official Manual](https://support.zebra.com/cpws/docs/zpl/zpl_manual.pdf)