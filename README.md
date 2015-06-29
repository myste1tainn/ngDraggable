# myste1tainn / ngDraggable
ngDraggable is a drag-and-drop module for AngularJS capable of creating 
draggable-objects and drop-target on the fly. More information on this will be on soon.

## Installation
- Install with bower `$ bower install myste1tainn/ngDraggable`
- Add **ngDraggable** as dependencies e.g. `angular.module('myApp', ['ngDraggable'])`

## Basic Usage
- For an element to be draggable, add `draggable-object` attribute.
- For an element to be a drop target, add `drop-target` attribute.

```
<!-- This is drag-and-drop without data transferring -->
<div draggable-object>Drag Me!</div>
<div drop-target>Drop Here</div>
```

### Composition
The module comprises of 2 controllers and 1 service namely:
`draggableObject`, dropTarget`, and `$drag`

### Getting Controllers
You can access the controllers by using the `$drag` through service injection
`$drag.$getDraggedObject()` and `$drag.$getDropTarget()`
The return object will be currently-dragged-object and currently-dragovered-target
respectively, otherwise they will be null.

```
.controller('myController', function($scope, $element, $attrs, **$drag**){
	var draggedObject = $drag.$getDraggedObject();
	var dropTarget = $drag.$getDropTarget();
})
```

## Features
- Drag-and-Drop w/ or w/o data (Automatically transfer, if any)
- Flexible `drop-target` specifying
- Flexible `draggable-object` specifying

## Coming Soon
- Drag-and-Drop controller-controller data transfer
- Drag-and-Drop Reordering
- Drag-and-Drop Animation
- Drag-and-Drop Data Cloning