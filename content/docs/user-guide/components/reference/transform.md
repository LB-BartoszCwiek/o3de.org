---
linkTitle: Transform
description: ' Use the Transform component to move, rotate, and scale an entity in
  Open 3D Engine. '
title: Transform Component
---

The **Transform** component controls the translation, rotation, and scale information of an entity in the 3D world. When you create an entity in O3DE Editor, the **Transform** component is automatically added. The translation is the coordinate location (x, y, and z axes) of the entity. The rotation is the degree in which the entity is rotated around its center. The uniform scale is the dimension of the entity in comparison to its original size, applied uniformly in each direction.

*World space* refers to the entity's absolute translation, rotation, and scale in the level. If a child is attached to a parent entity, *local space* refers to the entity's translation, rotation, and scale relative to its parent entity.

## Transform Component Properties 

The **Transform** component has the following properties:

**Parent entity**
The entity assigned as the parent. If a parent entity is specified, the **Transform** component follows the parent entity.

### Values 

The **Transform** component has the following values:

**Translate**
The local position (relative to the parent) in meters.

**Rotate**
The local rotation (relative to the parent) in degrees.

**Uniform Scale**
The local scale, with a single value applied uniformly in each direction. Click on the **Add non-uniform scale** button to add a [Non-uniform Scale](/docs/user-guide/components/reference/non-uniform-scale) component, which allows different scale values to be used on each axis of an entity.

**Parent activation**
Configures transform behavior when the parent entity activates.

**Static**
Entities that can't be moved at run time. Some systems in O3DE treat static entities differently than movable entities (for example, the renderer can optimize static entities, making them less resource intensive to draw).

## EBus Request Bus Interface 

**TransformBus** is the request bus for the **Transform** component. An entity's transform is the translation, rotation, and scale information.

For more information about using the event bus (EBus) interface, see [Working with the Event Bus (EBus) system](/docs/user-guide/programming/ebus/).

Use the following request functions with the EBus interface to communicate with other components of your game.

### GetLocalTM 

Returns the entity's local transform. Doesn't include the parent entity's transform.

**Parameters**
None

**Return**
Entity's local transform.

### SetLocalTM 

Sets the entity's local transform, relative to its parent entity, and notifies all listeners.

**Parameters**
Entity's local transform.

**Return**
None

### GetWorldTM 

Returns the entity's world transform, including the parent entity's transform.

**Parameters**
None

**Return**
Entity's world transform.

### SetWorldTM 

Sets the world transform and notifies all listeners.

**Parameters**
Entity's world transform.

**Return**
None

### GetLocalAndWorld 

Retrieves the entity's local and world transforms.

**Parameters**
Transform \[out\] - Local transform, relative to parent entity.
Transform \[out\] - World transform.

**Return**
None

### SetWorldTranslation 

Sets the entity's world space translation.

**Parameters**
New world space location, in x, y, and z coordinates.
Type: Vector3

**Return**
None

### SetLocalTranslation 

Sets the entity's local space translation, which is relative to its parent entity.

**Parameters**
New local space location, in x, y, and z coordinates.
Type: Vector3

**Return**
None

### GetWorldTranslation 

Gets the entity's world space translation.

**Parameters**
None

**Return**
Entity's world space, in x, y, and z coordinates.
Type: Vector3

### GetLocalTranslation 

Gets the entity's local space translation, which is relative to its parent entity.

**Parameters**
None

**Return**
Entity's local space, in x, y, and z coordinates.
Type: Vector3

### MoveEntity 

Moves the entity within world space.

**Parameters**
Offset in world space, in x, y, and z coordinates.
Type: Vector3

**Return**
None

### SetWorldX 

Sets the entity's translation x-axis coordinate in world space.

**Parameters**
X-axis coordinate in world space.
Type: Float

**Return**
None

### SetWorldY 

Sets the entity's translation y-axis coordinate in world space.

**Parameters**
Y-axis coordinate in world space.
Type: Float

**Return**
None

### SetWorldZ 

Sets the entity's translation z-axis coordinate in world space.

**Parameters**
Z-axis coordinate in world space.
Type: Float

**Return**
None

### GetWorldX 

Gets the entity's translation x-axis coordinate in world space.

**Parameters**
None

**Return**
X-axis coordinate in world space.
Type: Float

### GetWorldY 

Gets the entity's translation y-axis coordinate in world space.

**Parameters**
None

**Return**
Y-axis coordinate in world space.
Type: Float

### GetWorldZ 

Sets the entity's translation z-axis coordinate in world space.

**Parameters**
None

**Return**
Z-axis coordinate in world space.
Type: Float

### SetLocalX 

Sets the entity's translation x-axis coordinate in local space.

**Parameters**
X-axis coordinate in local space.
Type: Float

**Return**
None

### SetLocalY 

Sets the entity's translation y-axis coordinate in local space.

**Parameters**
Y-axis coordinate in local space.
Type: Float

**Return**
None

### SetLocalZ 

Sets the entity's translation z-axis coordinate in local space.

**Parameters**
Z-axis coordinate in local space.
Type: Float

**Return**
None

### GetLocalX 

Gets the entity's translation x-axis coordinate in local space.

**Parameters**
None

**Return**
X-axis coordinate in local space.
Type: Float

### GetLocalY 

Gets the entity's y-axis coordinate in local space.

**Parameters**
None

**Return**
Y-axis coordinate in local space.
Type: Float

### GetLocalZ 

Gets the entity's z-axis coordinate in local space.

**Parameters**
None

**Return**
Z-axis coordinate in local space.
Type: Float

### GetWorldRotation 

Gets the angles in radians for each principle axis around which the world transform is rotated in the following order: z-axis, y-axis, x-axis.

**Parameters**
None

**Return**
The Euler angles in radians, which indicate the degree of rotation around each principle axis.
Type: Vector3

### GetWorldRotationQuaternion 

Gets the quaternion that represents the world rotation.

**Parameters**
None

**Return**
The quaternion that represents the world rotation.
Type: Quaternion

### SetLocalRotation 

Sets the local rotation around each principle axes in the following order: z-axis, y-axis, x-axis.

**Parameters**
The Vector3 denoting radian angles of the rotations around each principle axis.
Type: Vector3

**Return**
None

### SetLocalRotationQuaternion 

Sets the local rotation matrix using a quaternion.

**Parameters**
The local rotation matrix.
Type: Quaternion

**Return**
None

### RotateAroundLocalX 

Rotates around the local x-axis for a radian angle.

**Parameters**
The radian angle to rotate around the local x-axis.
Type: Float

**Return**
None

### RotateAroundLocalY 

Rotates around the local y-axis for a radian angle.

**Parameters**
The radian angle to rotate around the local y-axis.
Type: Float

**Return**
None

### RotateAroundLocalZ 

Rotates around the local z-axis for a radian angle.

**Parameters**
The radian angle to rotate around the local z-axis.
Type: Float

**Return**
None

### GetLocalRotation 

Gets angles in radian for each principle axis around which the local transform is rotated in the following order: z-axis, y-axis, x-axis.

**Parameters**
None

**Return**
Indicates how much in radian is rotated around each principle axis.
Type: Vector3

### GetLocalRotationQuaternion 

Gets the quaternion representing the local rotation.

**Parameters**
None

**Return**
The quaternion that represents the local rotation.
Type: Quaternion

### SetLocalUniformScale 

Sets local uniform scale of the transform.

**Parameters**
Local uniform scale of the transform, applied equally to each axis.
Type: Float

**Return**
None

### GetLocalUniformScale 

Gets the uniform scale value, applied equally to each axis in local space.

**Parameters**
None

**Return**
Uniform scale value, applied equally to each axis in local space.
Type: Float

### GetWorldUniformScale 

Gets the uniform scale value, applied equally to each axis in world space.

**Parameters**
None

**Return**
Uniform scale value, applied equally to each axis in world space.
Type: Float

### GetParentId 

Returns the parent entity's ID. If the entity does not have a parent, the entity ID is invalid.

**Parameters**
None

**Return**
EntityID of the parent
Type: Int

### SetParent 

Sets the entity's parent entity and notifies all listeners. The entity's local transform is moved into the parent entity's space to preserve the entity's world transform.

**Parameters**
EntityId - Parent entity ID
Type: Int

**Return**
None

### SetParentRelative 

Sets the entity's parent entity, moves the transform relative to the parent entity, and notifies all listeners. This function uses the world transform as a local transform and moves the transform relative to the parent entity.

**Parameters**
EntityId - Parent entity ID
Type: Int

**Return**
None

### GetChildren 

Returns the entity IDs of the entity's immediate children.

**Parameters**
None

**Return**
Vector of EntityIds

### GetAllDescendants 

Returns the entity IDs of all descendants of the entity. The descendants are the entity's children, the children's children, and so on. The entity IDs are ordered breadth first.

**Parameters**
None

**Return**
Vector of EntityIds

### GetEntityAndAllDescendants 

Returns the entity ID of the entity and all its descendants. The descendants are the entity's children, the children's children, and so on. The entity IDs are ordered breadth first, and this entity's ID is the first in the list.

**Parameters**
None

**Return**
Vector of EntityIds

### IsStaticTransform 

Returns whether the transform is static. A static transform doesn't move and doesn't respond to requests to move it.

**Parameters**
None

**Return**
Boolean

## EBus Notification Bus Interface 

**TransformNotificationBus** is the notification bus for the **Transform** component. Use the following notification functions with the EBus interface to communicate with other components of your game.

For more information about using the event bus (EBus) interface, see [Working with the Event Bus (EBus) system](/docs/user-guide/programming/ebus/).

### OnTransformChanged 

Signals that the local or world transform of the entity changed.

**Parameters**
Transform - The new local transform of the entity
Transform - The new world transform of the entity

### OnParentChanged 

Signals that the parent of the entity changed.

**Parameters**
EntityId - The entity ID of the previous parent. The entity ID is invalid if there was no previous parent.
EntityId - The entity ID of the new parent. The entity ID is invalid if there is no new parent.

### OnChildAdded 

Signals that a child was added to the entity.

**Parameters**
EntityId - The entity ID of the added child

### OnChildRemoved 

Signals that a child was removed from the entity.

**Parameters**
EntityId - The entity ID of the removed child
