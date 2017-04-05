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

### Event
- 'listeners' config add listeners to events when the instance is created
- on() add events after the instance is created
- un() to remove
- add listeners to DOM element:
```javascript
var div = Ext.get('mydiv');
div.on(...);
```
### Access DOM
- Ext.get(): takes the ID of a DOM node, and return Ext.dom.Element
- Ext.query(): selects the child nodes of a given root bassed on the passed CSS selector, return HTMLElement[]/Ext.dom.Element[]
- Ext.select(): returns a single object of type CompositeElement using **CSS/XPath selector**, use',' in selector to multiple search
select() use HTML body as the root by def, so use with Ext.get()
```javascript
Ext.select('div.row[title = bar] : first'); // selection chaining: class-row, attribute-title, first child
```
- Ext.ComponentQuery: .query(): xtype-'button'; ID-'#foo' or nested selectors

### Component
- Ext.component: base class of all the built-in components. 
- xtype: use for lazy loading, not instantiate immediately

### Container
- Ext.container.Container: base class, capable of holding other components
- Ext.toolbar
- Ext.panel.Panel
- Ext.Editor

### Layout
- position and size, def- auto












