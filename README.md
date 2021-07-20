- REF: https://github.com/nomacs/nomacs/tree/master/ImageLounge/src
- REF: https://github.com/nomacs/nomacs-plugins/blob/master/manuals/Creating-a-new-plugin.md
- REF: https://github.com/nomacs/nomacs-plugins/tree/3cd6e61130a6ad4ef722d082f9e9cf0016b68fa0/SIMPLE_PLUGIN
- REF: https://doc.qt.io/qt-5/qpluginloader.html


### PluginManager codigo fuente
~~~
- ImageLounge/src/DkCore/DkPluginManager.cpp
~~~

### Tipos de plugins
~~~
- ImageLounge/src/DkCore/DkPluginInterface.h
~~~

~~~
- DkPluginInterface
	- virtual QImage image()
	- virtual QList<QAction*> createActions(QWidget*)
	- virtual QList<QAction*> pluginActions() const
	- virtual bool closesOnImageChange() const
	- virtual QSharedPointer<DkImageContainer> runPlugin(...)
	
- DkBatchPluginInterface : public DkPluginInterface
	- virtual void preLoadPlugin() const
	- virtual void postLoadPlugin(...)
	- virtual QString name()
	- virtual void loadSettings(QSettings&)
	- virtual void saveSettings(QSettings&) const

- DkViewPortInterface : public DkPluginInterface
	- virtual bool hideHUD() const	
	- virtual bool createViewPort(QWidget* parent)
	- virtual DkPluginViewPort* getViewPort()
	- virtual void setVisible(bool visible)	
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

### loadJson llama a loadMetaData
~~~
void DkPluginContainer::loadMetaData(const QJsonValue& val)
~~~
