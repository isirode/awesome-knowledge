---
id: 99r2x1rqn5bjkis60k7vu7t
title: Convert Angle to Vector2
desc: ''
updated: 1681658615832
created: 1676142818024
---

## Convert an angle to a Vector2

If you have the angle you want to convert, you can use the cosinus and the sinus to obtain the angle's coordinates:

x = cosinus(angle)
y = sinus(angle)

In mathematics, the cosinus would be the length of the bottom edge, and the sinus would provide the length of the opposite edge.

In graphics, it become the coordinate of the vector.

### Javascript

```javascript

let angle = 90;
let vector = new Vector2();
vector.x = Math.cos(angle);
vector.y = Math.sin(angle);

```

Using the [Math built-in object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)

## Convert this Vector2 to a position

You can obtain a coordinate by multiplying the Vector2 by a length.

```javascript
var coordinate = vector * 5
```

## Convert the Vector2 direction to an angle

You can use atan2(y, x) to obtain the angle back.

### Javascript

```javascript

let angle = Math.atan2(vector.y, vector.x);

```
