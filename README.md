
# Vala language server

This extension contains the Vala language server.

## Test

```
flatpak run --command=/usr/lib/sdk/vls/bin/vala-language-server org.gnome.Sdk/x86_64/master
vls-DEBUG: main.vala:223: Finished constructing
```

## Usage

You can bundle the Vala language server with your Flatpak application by adding this SDK extension to your Flatpak manifest. For example:

```
{
  "id" : "org.example.MyApp",
  "branch" : "1.0",
  "runtime" : "org.gnome.Platform",
  "runtime-version" : "3.36",
  "sdk" : "org.gnome.Sdk",
  "sdk-extensions" : [ "org.freedesktop.Sdk.Extension.vls" ],
  "modules" : [ {
    "name" : "myapp",
    "buildsystem" : "simple",
    ....
  } ]
  ....
  "finish-args" : [ "--env=PATH=/usr/lib/sdk/vls/bin:/usr/bin" ]
}
```
