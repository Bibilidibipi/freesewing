---
title: bartackFractionAlong
---

The `bartackFractionAlong` macro allows you to add a _bartack_ marker to your
sewing pattern. More specifically, a bartack along a fraction of a path.  
It is provided by the [annotations plugin](/reference/plugins/annotations).

## Signature

```js
macro('banner', {
  Number angle=0,
  Number density=3,
  Number end=1,
  Number length=15,
  Path path,
  String prefix='',
  Number start=0,
  String suffix='',
  Number width=3,
})
```

## Example

<Example caption="Example of the bartackFractionAlong macro">
```js
({ Point, Path, macro, part }) => {

  macro('bartackFractionAlong', { 
    path: new Path()
      .move(new Point(15,15))
      .curve(
        new Point(20, 20),
        new Point(30, 20),
        new Point(35, 15),
      ),
    start: 0.2,
    end: 0.8,
  })

  return part
}
```
</Example>

## Configuration

| Property     | Default    | Type       | Description |
|-------------:|------------|------------|-------------|
| `angle`      | `0`        | `number`   | The angle under which to draw the bartack |
| `density`    | `3`        | `number`   | Controls how close the stitches are together |
| `end`        | `1`        | `number`   | At which fraction of the path length (from `0` to `1`) should the bartack end |
| `length`     | `15`       | `number`   | Length of the bartack |
| `path`       |            | `Path`     | The path the bartack should follow |
| `prefix`     |            | `string`   | A prefix to apply to the name of the generated path |
| `start`      | `0`        | `number`   | At which fraction of the path length (from `0` to `1`) should the bartack start |
| `suffix`     |            | `string`   | A suffix to apply to the name of the generated path |
| `width`      | `3`        | `number`   | Width of the bartack |

## Result

| Generated Element | Description |
|-------------------|-------------|
| `paths.${prefix}bartack${suffix}` | Path generated for the bartack marker |
