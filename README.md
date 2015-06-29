# myste1tainn / ngDraggable
ngDraggable is a drag-and-drop module for AngularJS capable of creating 
draggable-objects and drop-target on the fly. ngDraggable also support Non-HTML5 dragging
More information on this will be on soon.

[See myste1tainn/ngDraggable in action](http://dev-mysteltainn.rhcloud.com/git/ngdraggable)

## Installation
- Install with bower `$ bower install myste1tainn/ngDraggable`
- Add **ngDraggable** as dependencies e.g. `angular.module('myApp', ['ngDraggable'])`

## Composition
The module comprises of 2 controllers and 1 service namely:
`draggableObject`, `dropTarget`, and `$drag`. Mostly, you'll be interacting with the service

## Usage
- For an element to be draggable, add `draggable-object` attribute.
- For an element to be a drop target, add `drop-target` attribute.

```HTML
<!-- This is drag-and-drop without data transferring -->
<div draggable-object>Drag Me!</div>
<div drop-target>Drop Here</div>
```

```HTML
<!-- This is drag-and-drop with data transferring -->
<!-- This would mean you drag fruit and drop it into baskets -->
<div ng-repreat="basket in someCtrl.baskets">
	<div ng-repeat="fruit in basket.fruits" drop-target drop-model="basket.fruits">
		<div draggable-object drag-data="fruit" drag-model="basket.fruits">
			{{ fruit.name }}
		</div>
	</div>
</div>
```

### Getting Controllers
You can access the controllers by using the `$drag` through service injection
`$drag.$getDraggedObject()` and `$drag.$getDropTarget()`
The return object will be currently-dragged-object and currently-dragovered-target
respectively, otherwise they will be null.

```JavaScript
.controller('myController', function($scope, $element, $attrs, $drag){
	var draggedObject = $drag.$getDraggedObject();
	var dropTarget = $drag.$getDropTarget();
})
```

### Events
In myste1tainn/ngDraggable, you can listen to events on both the service and controllers
If you only need to know the presence/absence of `draggleObjects`/`dropTarget`, then using
`$drag`'s events should be enough. To attach events listner do 
`$drag.on('object.event', callback)`, to detach use `.un` instead.

#### Events on $drag
| Event Name | Description |
| --------------- | ------------------------------ |
| draggable.get | Any draggable-object is dragged. |
| draggable.lost | Any draggable-object is drop. |
| droptarget.get | Any draggable-object is dragged into any droptarget. |
| droptarget.lost | Any draggable-object is dragged out of any droptarget. |
| droptarget.over | Any draggable-object is dragged over any droptarget. |

#### Events on draggedObject (Controller)
| Event Name | Description |
| --------------- | ------------------------------ |
| dragstart | The draggable-object is started being dragged. |
| drag | The draggable-object is dragged around. |
| dragend | The draggable-object is dropped. |

#### Events on dropTarget (Controller)
| Event Name | Description |
| --------------- | ------------------------------ |
| dragenter | A draggable-object is dragged into the drop-target. |
| dragover | A draggable-object is dragged over the drop-target. |
| dragleave | A draggable-object is dragged out of the drop-target. |

## Features
- Drag-and-Drop w/ or w/o data (Automatically transfer, if any)
- Flexible `drop-target` specifying
- Flexible `draggable-object` specifying

## Coming Soon
- Drag-and-Drop cross controller data transfer
- Drag-and-Drop Reordering
- Drag-and-Drop Animation