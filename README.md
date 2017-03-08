# ExtjsExp
Ext JS 6.2.0

##Class:

Declaration: Ext.define(className, members, onClassCreated);
*className: The class name
*members is an object that represents a collection of class members in key-value pairs
*onClassCreated is an optional function callback that is invoked when all dependencies of the defined class are ready and the class itself is fully created.
It is recommended to get in the habit of always using Ext.create() to create new instance since it allows you to take advantage of dynamic loading.
There is also a dedicated config property that gets processed by the powerful Ext.Class pre-processors before the class is created.
Static members can be defined using the statics config
You can use Ext.getDisplayName() to get the display name of any method. This is especially useful for throwing errors that have the class name and method name in their description
When an error is thrown in any method of any class defined using Ext.define(), you should see the method and class names in the call stack if you are using a WebKit based browser 

##Layout:

The layout system handles the sizing and positioning of every Component in your application.
Every container has a layout that manages the sizing and positioning of its child Components. 

##Component:

An Ext JS application's UI is made up of one or many widgets called Components. 
All Components are subclasses of the Ext.Component class which allows them to participate in automated lifecycle management including instantiation, rendering, sizing and positioning, and destruction.
 A typical application's Component hierarchy starts with a Viewport at the top, which has other Containers and/or Components nested within it.
Child Components are added to a Container using the Container's items configuration property.
Every Component has a symbolic name called an xtype.
 This is where xtypes come in handy by allowing a Container's children to be configured up front, but not instantiated until the Container determines it is necessary.
All Components have built in show and hide methods. 
Floating Component are positioned outside of the document flow using CSS absolute positioning, and do not participate in their Containers' layout. Some Components such as Windows are floating by default, but any Component can be made floating using the floating configuration.
Floating Components are automatically rendered to the document body the first time their show method is called.

It is recommended to extend the nearest base class to the functionality required. This is because of the automated lifecycle management Ext JS provides which includes automated rendering when needed, automatic sizing and positioning of Components when managed by an appropriate layout manager, and automated destruction on removal from a Container.

Ext.Base is the building block of all Ext JS classes, and the prototype and static members of this class are inherited by all other classes.
Ext JS uses the Template method pattern to delegate to subclasses, behavior which is specific only to that subclass.

##Data Package:

The data package is what loads and saves all of the data in your application. 1. Ext.data.Model; 2. Store; 3. Ext.proxy.Proxy
1.  A Model represents an entity in an application. Field, Proxies, Validation, Association.
The schema*(in Base class) is a manager for all of the models in your application. 
2. Proxies are used by Models and Stores to handle the loading and saving of Model data.
Examples of client proxies include Memory and Local Storage
Server proxies handle the marshaling of data to a remote server. 
A schema is a collection of entities that have associations with one another. 
Models are typically used with a Store, which is basically a collection of records (instances of a Model-derived class). 
Stores are able to perform sorting, filtering and grouping locally and remotely.
Models can be linked together with the Associations API.  reference: 'User',
Validators are defined as an object keyed by field name which map to the rules that define a valid field. These rules are expressed as a validator object config or an array of these configs.

##Gestures:

In addition to standard DOM events, Elements also fire synthesized "gesture" events. From a browser's perspective, there are 3 primary types of pointer, touch, and mouse events - start, move, and end.

...

##Events:

We can pass listeners to the component when the class was instantiated. Or, if we already have an instance, we can add listeners using the .on() function.
.un()
scope
single: true,*(listen to one event only once)
buffer: 2000,*(only invoked once every 2 seconds)
Firing your own events is done by calling fireEvent with an event name.
Use Ext.defer to delay the function that fires custom event

##OOP in ExtJS

Ext.define() to define a new class. In Ext JS, all classes are children of a common base class unless explicitly specified. This base class is Ext.Base.

Ext.create() to create an instance

constructor to enable pass value to create(), take an argument object, then we can pass an object containing properites/values.

Ext.apply(this, config) to auto set value in constructor

extend; defining parent class to realize *inheritance*

config block to restrict access to the object's properties so they can only be set and retrieved using accessor methods(auto-generated by initConfig()).

*The config block should only include new configs unique to its class. You should not include configs already defined in a parent class's config block. Parent class properties are defined outside the config block*

applyXxx(newvValue, oldValue) to apply CHECK


##Grids
Ext.grid.Panel is simply a component that displays data contained in a Ext.data.Store. Ext.data.Store can be thought of as a collection of records, or Ext.data.Model instances.

->  separating concerns: Ext.grid.Panel is only concerned with displaying the data, while Ext.data.Store takes care of fetching and saving the data using Ext.data.proxy.Proxy.

 A renderer is a function that modifies the underlying value and returns a new value for display. Some of the most common renderers are included in Ext.util.Format.
 
All Grid panels have an Ext.selection.Model, which determines how data is selected. 
 
Cell editing allows you to edit the data in a Grid panel one cell at a time. The first step in implementing cell editing is to configure an editor for each Ext.grid.column.Column in your Grid Panel that should be editable. , to enable editing we need to configure the Ext.grid.Panel with a Ext.grid.plugin.CellEditing.

Row editing

Paging

In 6.2.0, components embedded in grids have access to the ViewModel and all the data within it.


**Panel VS Container**
RowWidegt only work in panel

**Flex**
Flex may be applied to child items of a box layout (Ext.layout.container.VBox or Ext.layout.container.HBox). Each child item with a flex property will fill space (horizontally in hbox, vertically in vbox) according to that item's relative flex value compared to the sum of all items with a flex value specified.

**vbox VS hbox**
hbox; in a row; vbox: in a column.

**Combobox**

forceSelection: true

**AJAX vs JSONP**
JSONP can only make GET request as using <script>

##ViewModel

A ViewModel is a class that manages a data object. It then allows those interested in this data to bind to it and be notified when it changes. 
*bound data will always take priority over static configuration values but may be delayed in order to fetch that data.
*all of the children of the component with a viewModel also have access to their container's data.




