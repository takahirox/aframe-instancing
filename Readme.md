# A-Frame instancing component

This is an example component for A-Frame to take advantage of three.js instanced rendering support. This is useful if you have to render a large number of objects with the same geometry and material but with different world transformations. This will help you to reduce the number of draw calls and thus improve the overall rendering performance in your application.

This is a proof of concept that replicates a large number of spheres with random colors and transformations in just one draw call.

### Component API

| Property | Description | Default Value |
| -------- | ----------- | ------------- |
| `count`    | The number of geometries to instance | `10000` |
| `frustumCulled` | Attempt to hide the instances when out of view of the camera frustum to improve performance. Setting to `true` doesn't work well at the moment because the camera frustum doesn't "know" where the instanced geometries are located. | `false` |

### Installation and Usage

#### Browser

Install and use by directly including the [browser files](dist):

```html
<head>
  <title>My A-Frame Scene</title>
  <script src="https://aframe.io/releases/1.0.4/aframe.min.js"></script>
  <script src="[update this URL when takahirox accepts PR and pushes to npm]"></script>
</head>

<body>
  <a-scene>
    <a-entity instancing="count:40000; frustumCulled: false;"></a-entity>
  </a-scene>
</body>
```

### Work in progress
This is a work in progress and could be improved in the future, for example:
- Allow other primitive geometries to be instanced in addition to the default sphere geometry
- Provide support for more advanced materials
- Provide support for imported glTF models to be instanced
- Provide improved support for frustumCulling ([further research on frustum culling with instancing](https://stackoverflow.com/questions/45378920/three-js-with-instancing-cant-get-it-to-work-without-frustumculling-false))
