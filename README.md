# myste1tainn / ngDraggable
ngDraggable is a drag-and-drop module for AngularJS capable of creating 
draggable-objects and drop-target on the fly. More information on this will be on soon.

## Installation
- Install with bower `$ bower install myste1tainn/ngDraggable`
- Add **ngDraggable** as dependencies e.g. `angular.module('myApp', ['ngDraggable'])`

## Usage
- For an element to be draggable, add `draggable-object` attribute.
- For an element to be a drop target, add `drop-target` attribute.

```
<div draggable-object>Drag Me!</div>
<div drop-target>Drop Here</div>
```

## Features
- Drag-and-Drop w/o data
- Drag-and-Drop w/ data (Automatically transfer)
- Flexible `drop-target` specifying
- Flexible `draggable-object` specifying

## Coming Soon
- Drag-and-Drop Reordering
- Drag-and-Drop Animation
- Drag-and-Drop Data Cloning