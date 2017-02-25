# ExtjsExp
Ext JS 6.2.0

Class:
Declaration: Ext.define(className, members, onClassCreated);
*className: The class name
*members is an object that represents a collection of class members in key-value pairs
*onClassCreated is an optional function callback that is invoked when all dependencies of the defined class are ready and the class itself is fully created.
It is recommended to get in the habit of always using Ext.create() to create new instance since it allows you to take advantage of dynamic loading.
There is also a dedicated config property that gets processed by the powerful Ext.Class pre-processors before the class is created.
Static members can be defined using the statics config
You can use Ext.getDisplayName() to get the display name of any method. This is especially useful for throwing errors that have the class name and method name in their description
When an error is thrown in any method of any class defined using Ext.define(), you should see the method and class names in the call stack if you are using a WebKit based browser 

Layout:
The layout system handles the sizing and positioning of every Component in your application.
Every container has a layout that manages the sizing and positioning of its child Components. 

Component:
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























