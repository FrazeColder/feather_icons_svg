# Feather Icons SVG for Flutter

[Feather Icons](https://feathericons.com/) port to Flutter. This package renders the icons as SVG
pictures. This makes it possible to customize icon properties in runtime (stroke width etc.).

## Difference to the original package
I have added a `fill` property to this package, so you can use the iconic feather icons also as solid icons.
You can either pass `true` so the icon will be filled with the color which is already provided via the `color` property, or you can simply pass you own Color to the `fill` property.

## Usage

```dart
class MyExampleWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return FeatherIcon(
      FeatherIcons.calendar,
      color: Colors.red,
      size: 30,
      strokeWidth: 1.5,
      fill: true // also accepts a Color property e.g.: fill: Colors.yellow
    );
  }
}
```

You can also use `FeatherIconTheme` inherited widget to customize default values for Widget
subtree.

## Install

Add `feather_icons_svg` package into your `pubspec.yaml`.

```shell
flutter pub add flutter_icons_svg
```

## Development

To fetch SVG icons from original Feather Icons repository, run `tool/fetch-icons.sh`.

The SVG contains unsupported content. To fix all fetched icons, run `tool/fix_svg.dart`. This
replaces invalid SVG attributes for every file and saves it.

Finally, to run source code generation to create `flutter_icons_svg.dart` file with named
constructor for every icon, run `tool/generator.dart`.
