# AS3HX

The Haxe Foundation supports a tool called "AS3HX" which handles a lot of the conversion from ActionScript to Haxe.

## Setup

First, make sure that you have followed the directions for downloading and installing Haxe on your system.

Open a command-prompt or terminal, and install AS3HX:

```bash
haxelib install as3hx
```

## Running AS3HX

Once you have AS3HX installed, you can run AS3HX to convert an input source into an output Haxe directory

```bash
haxelib run as3hx path/to/as3 path/to/output
```

## Configuration

The first time you run AS3HX, the tool will generate a file called ".as3hx_config.xml" in your home directory, such as "/home/joshua/.as3hx_config.xml" or "C:\Users\Joshua\.as3hx_config.xml"

Open this file in a text editor and you can change a number of different options for how AS3HX will process ActionScript 3.0 source and generate corresponding Haxe source.

After changing the configuration file, try running the `as3hx` command again to compare the results.

These are some of the options available

### `<indentChars value="    " />`

Edit which characters are used for indentation. Common values include "\t" or "    " for tab or space indentation.

### `<bracesOnNewline value="true" />`

Edit whether braces will be placed on a new line, or whether they will be "cuddled" on the same line. You can enter "true" or "false"

### `<spacesOnTypeColon value="true" />`

Edit whether spaces are inserted around type declarations, such as `var hello : String` compared to `var hello:String`. You can select "true" or "false"

### `<vectorToArray value="true" />`

Edit whether Vector.<> references will be replaced with Haxe typed Array<> references. OpenFL includes an openfl.Vector class that behaves similar to the Flash Vector.<> type, so this conversion is not necessary. You can choose "true" or "false"

### `<useFastXML value="true" />`

Edit whether XML parsing will be replaced with AS3HX "FastXML" parsing, which requires the addition of an extra class in order to compile the source. You can select "true" or "false"

## Quirks

No converter is perfect, and AS3HX has a few quirks. Particularly, AS3HX is not always able to determine types when casting, and is not able to handle E4X XML well.

Some types of conversion may be a bit overzealous as well. Converting ActionScript Dictionaries to the Haxe Map type, for example, may be appropriate, but you can also use the openfl.utils.Dictionary type for better compatibility.

## Contributing to AS3HX

AS3HX is an open-source project, hosted at [https://github.com/haxefoundation/as3hx](https://github.com/haxefoundation/as3hx] and contributions are welcome!