# Notes

## Observations

### Using the `vector` function beyond the volume size

The `vector` function for retrieving a color index will return `0.0` when addressing beyond the volume size. Therefore, it is not necessary to check wether the `x`, `y` or `z` co-ordinates will be out-of-bounds before calling `vector`.

**For example:**

```glsl
vector(500.0, 500.0, 500.0); // 0.0
vector(-1.0, -1.0, -1.0); // 0.0
```

## Snippets

### Determine if a axis mode is set

`bNoAxisMode` will be `true` when no axis modes are set, false otherwise.

```glsl
bool bNoAxisMode = all(equal(iAxis, vec3(0.0, 0.0, 0.0)));
```

### Determine which axis mode is set

```glsl
bvec3 bAxisMode = equal(iAxis, vec3(1.0, 1.0, 1.0));
```

`bAxisMode` is a `bvec3` indicating which axis mode is set.

**For example:** `bAxisMode.x` will be `true` if the X-Axis mode is set.
