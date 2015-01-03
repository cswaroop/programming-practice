# [Polymer](http://www.polymer-project.org)

Agenda

- Structure.
- Transitions.
- Performance.
- Offline.


## <core-toolbar>

A basic container for controls like tabs or buttons

```
<core-toolbar>
   <div flex> All Contacts </div>
</core-toolbar>
```

## <paper-menu-button>

An animating context menu, composed of other elements 

```
<paper-menu-button>
  <paper-icon-button icon="more-vert"> </paper-icon-button>
  <paper-drop-down class="dropdown" halign="right">
    <core-menu class="menu">
      <paper-item>Settings</paper-item>
      <paper-item>Help</paper-item>
      <paper-item>Feedback</paper-item>
    </core-menu>
</paper-menu-button>
```

## <core-header-panel>

A Simple container with a header section and a content section

```
<core-header-panel>
  <core-toolbar> </core-toolbar>
  <div class="content"> </div>
</core-header-panel>

```


## <core-scroll-header-panel>

The `condenses` attribute creaes a nice cross-fade effect

```
<core-scroll-header-panel condenses>
	<core-toolbar>
		...
	</core-toolbar>
</core-scroll-header-panel>
```


## <core-drawer-panel>

A responsive scaffold

```
<core-drawer-panel>
	<div drawer> Drawer Panel... </div>
	<div drawer> Main Panel... </div>
</core-drawer-panel>

```

## <core-list>

A virtualized, "infinite" list

```
	<core-list id="list" flex>
		<template>
			<div>
				<div> {{model.name}} </div>
			</div>
		</template>
	</core-list>
```

```
	this.$.list.data = [
		{name: 'Ada Blick'},
		{name: 'Addy Osmani'}
	];
```

Use core-image to prevent stale images in your list


```
<core-list flex>
	<template>
		<div layout horizontal center>
		  <core-image src="{{model.avatar}}" sizing="cover" preload></core-image>
		<div flex> {{model.name}} </div>
		</div>
	</template>
</core-list>
```

Bind `<core-list>` `scrollTarget` to  `<core-header-panel`s scroller


```
<core-header-panel id="hPanel">
	<core-list id="contactsList" scrollTarget="{{$.hPanel.scroller}}">
	...
	</core-list>
</core-header-panel>
```

or


```
	this.$.list.scrollTarget = this.$.hPanel.scroller;
```


## <core-animated-pages>

A pluggable system for creating smoot transitions from one view to the next

```
<core-animated-pages selected="0" transitions="slide-from-right">
	<section>Geography </section>
	<section>Science </section>
	<section>Music </section>
</core-animated-pages>
```
