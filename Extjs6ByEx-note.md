The list of classes required for this class has to be specified in the requires section, there will be loaded first before instantiating this class.

## Core
### Class System
- Ext: a global singleton object that encapsulates all in the Sencha lib

- Ext.app.Application: a class that represents the entire application, creating a global variable with its name. launch()
- Ext.define(): to create or override a class(extend/override/singleton: true)
```javascript
Ext.define(name, data, callback);
```
- Ext.create(): to create an instance of a class , will automatically download the appropriate JS file if the Ext.Loader is enabled('new' can't)
```javascript
Ext.create(Class, Options);
```
- Ext.onReady(): be called once the page is loaded, rarely use
- Ext.widget(): create widget using its 'xtype' or 'alias'.
- Ext.getClass()
- Ext.getClassName()

- Ext.Base: the base of all Ext classes

- Ext.Class: a low-level factory used by Ext.ClassManager for the creation of a class.

- Ext.ClassManager: manages all the classes and handles mapping from a string class name to actual class objects. 
accessed through: define(); create(); widget(); getClass(); getClassName()

- Ext.Loader: for dynamic dependency loading, use with Ext.require() and Ext.exclude(). -> the required classes are loaded asynchronously.
