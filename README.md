- REF: https://github.com/nomacs/nomacs-plugins/tree/3cd6e61130a6ad4ef722d082f9e9cf0016b68fa0/SIMPLE_PLUGIN
- REF: https://doc.qt.io/qt-5/qpluginloader.html


###PluginManager codigo fuente
~~~
- ImageLounge/src/DkCore/DkPluginManager.cpp
~~~

### Cargar todos los Plugins
~~~
void DkPluginManager::loadPlugins()
~~~

### Cargar un plugin desde un archivo
~~~
bool DkPluginManager::singlePluginLoad(const QString& filePath)
~~~

### singlePluginLoad Instancia DkPluginContainer
~~~
DkPluginContainer::DkPluginContainer(const QString& pluginPath)
~~~

### DkPluginContainer llama a loadJson
~~~
void DkPluginContainer::loadJson()
~~~

### Ejemplo del json del plugin
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
