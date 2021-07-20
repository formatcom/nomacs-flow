- REF: https://github.com/nomacs/nomacs-plugins/tree/3cd6e61130a6ad4ef722d082f9e9cf0016b68fa0/SIMPLE_PLUGIN


~~~
- Primero busca el json del plugin
~~~

~~~
{
    "PluginName" 	: "User Friendly Plugin Name",
	"Tagline" 	: "Tagline - what does your plugin do?.",
	"Description"	: "Extended description (displayed in the plugin manager).",
	"AuthorName" 	: "Your Name",
	"Company"	: "Your Company",
	"DateCreated" 	: "Today",
	"DateModified"	: "2018-06-05",
	"PluginId"	: "https://guidgenerator.com/ without hyphens, e.g.: 2c1f60f24438431a8dc0ab43b2caad6a",
	"Version"	: "0.1.0"
}
~~~

~~~
- ImageLounge/src/DkCore/DkPluginManager.cpp
~~~

### Plugin Load
~~~
bool DkPluginContainer::load()
~~~

