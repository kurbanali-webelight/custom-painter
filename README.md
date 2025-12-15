# 🎨 Flutter CustomPainter – Custom Shapes Drawing Guide

This document is a **complete reference guide** for drawing custom shapes using Flutter's `CustomPainter`.  
It is designed to help you master all the techniques needed to create any shape on the canvas.

---

## 📌 What This Covers

- Core shape drawing APIs
- Path construction techniques
- Shape styling and effects
- Geometry utilities
- Transform operations for shapes

> ⚠️ This is a **focused reference** for custom shape creation.

---

## 1️⃣ Core Classes (Foundation)

- `CustomPainter`
- `CustomPaint`
- `Canvas`
- `Paint`
- `Size`
- `Offset`
- `Rect`
- `Path`

---

## 2️⃣ CustomPainter Class API

### Required Methods
- `void paint(Canvas canvas, Size size)`
- `bool shouldRepaint(covariant CustomPainter oldDelegate)`

---

## 3️⃣ Canvas Drawing APIs (Basic Shapes)

### Primitive Shapes
- `drawLine` - Draw straight lines
- `drawCircle` - Draw perfect circles
- `drawOval` - Draw ellipses and ovals
- `drawRect` - Draw rectangles
- `drawRRect` - Draw rounded rectangles
- `drawDRRect` - Draw double rounded rectangles (donut shapes)
- `drawArc` - Draw arcs and pie segments

### Complex Shapes
- `drawPath` - Draw custom paths
- `drawPoints` - Draw multiple points (dots, lines, polygons)

---

## 4️⃣ Path Construction & Manipulation

### Path Building Methods
- `moveTo` - Move to a point without drawing
- `lineTo` - Draw straight line to point
- `relativeLineTo` - Draw line relative to current position
- `quadraticBezierTo` - Draw quadratic Bezier curve
- `cubicTo` - Draw cubic Bezier curve
- `arcTo` - Add arc to path
- `arcToPoint` - Add arc between two points

### Adding Predefined Shapes to Paths
- `addRect` - Add rectangle to path
- `addOval` - Add oval to path
- `addRRect` - Add rounded rectangle to path
- `addPolygon` - Add polygon to path
- `addPath` - Combine multiple paths

### Path Operations
- `close` - Close the current contour
- `reset` - Clear the path
- `shift` - Move path by offset
- `transform` - Apply matrix transformation to path
- `contains` - Check if point is inside path

### Path Metrics
- `computeMetrics` - Get measurements of path segments

---

## 5️⃣ Canvas Transforms (Shape Positioning)

- `save` - Save canvas state
- `restore` - Restore canvas state
- `translate` - Move canvas origin
- `rotate` - Rotate canvas
- `scale` - Scale canvas
- `skew` - Skew/shear canvas
- `transform` - Apply matrix transformation

---

## 6️⃣ Paint Properties (Shape Styling)

### Basic Styling
- `color` - Shape color
- `style` - Fill or stroke (`PaintingStyle.fill`, `PaintingStyle.stroke`)
- `strokeWidth` - Line thickness for strokes
- `strokeCap` - Line end style (`round`, `square`, `butt`)
- `strokeJoin` - Corner style (`round`, `miter`, `bevel`)
- `isAntiAlias` - Smooth edges

### Advanced Styling
- `shader` - Apply gradients to shapes
- `blendMode` - How shape blends with background
- `maskFilter` - Blur effects

---

## 7️⃣ Geometry & Math Utilities

### Core Geometry Classes
- `Offset` - Point coordinates (x, y)
- `Size` - Width and height
- `Rect` - Rectangle with position and size
- `RRect` - Rounded rectangle
- `Radius` - Corner radius

### Rect Construction Helpers
- `Rect.fromLTWH` - From left, top, width, height
- `Rect.fromLTRB` - From left, top, right, bottom
- `Rect.fromCenter` - From center point and size
- `Rect.fromCircle` - From center and radius
- `Rect.fromPoints` - From two corner points

### Offset Utilities
- `Offset.distance` - Distance between points
- `Offset.direction` - Angle between points

### Math Helpers
- `lerpDouble` - Linear interpolation between numbers

---

## 8️⃣ Gradients & Shaders (Shape Fills)

### Gradient Types
- `LinearGradient` - Straight gradient between points
- `RadialGradient` - Circular gradient from center
- `SweepGradient` - Angular gradient (pie-like)

### Shader Usage
- `createShader(Rect)` - Create shader for paint

---

## 9️⃣ Clipping (Shape Masking)

- `clipRect` - Clip to rectangle
- `clipRRect` - Clip to rounded rectangle
- `clipPath` - Clip to custom path

---

## 🔟 Common Shape Patterns

### Regular Polygons
- Triangle, Pentagon, Hexagon, Octagon
- Using angle math: `360° / sides`
- `Offset(centerX + radius * cos(angle), centerY + radius * sin(angle))`

### Stars
- Outer and inner radius
- Alternating points

### Rounded Shapes
- Using `RRect` with different corner radii
- Custom rounded paths with `arcTo`

### Wave Patterns
- Sine and cosine curves
- Using `quadraticBezierTo` for smooth waves

### Dashed Lines
- Custom `PathMetric` iteration
- Drawing segments with gaps

### Complex Curves
- Bezier curves for smooth shapes
- Combining multiple curve types

---

## 1️⃣1️⃣ Shape Drawing Techniques

### Filled Shapes
```dart
final paint = Paint()
  ..color = Colors.blue
  ..style = PaintingStyle.fill;
```

### Outlined Shapes
```dart
final paint = Paint()
  ..color = Colors.blue
  ..style = PaintingStyle.stroke
  ..strokeWidth = 2.0;
```

### Gradient Filled Shapes
```dart
final paint = Paint()
  ..shader = LinearGradient(
    colors: [Colors.blue, Colors.purple],
  ).createShader(rect);
```

### Multiple Shapes
- Draw multiple shapes by calling draw methods multiple times
- Use different Paint objects for different styles
- Combine shapes using paths

---

## 1️⃣2️⃣ Mathematical Concepts for Shapes

### Trigonometry
- `sin`, `cos`, `tan` for circular positioning
- Radians: `degrees * pi / 180`

### Distance & Angles
- Distance formula: `sqrt((x2-x1)² + (y2-y1)²)`
- Angle: `atan2(y2-y1, x2-x1)`

### Interpolation
- Linear: `start + (end - start) * t`
- For smooth animations and transitions

---

## 🎯 Recommended Learning Order

1. Basic shapes (circle, rect, line)
2. Path construction (moveTo, lineTo, close)
3. Paint styling (fill, stroke, color)
4. Curves (quadratic & cubic Bezier)
5. Transforms (rotate, scale, translate)
6. Complex paths (combining shapes)
7. Gradients and advanced styling
8. Regular polygons and stars
9. Custom complex shapes

---

## 🧠 Final Note

Mastering custom shape drawing means:
- Understanding **coordinate systems**
- Thinking in **paths and geometry**
- Combining **simple shapes** into complex ones
- Using **math** for precision

This document serves as your **complete reference** for drawing any custom shape in Flutter.

---

✨ Happy Shape Drawing!