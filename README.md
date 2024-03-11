# XML Namespacer

A small script you can add to your build pipeline to transform XML templates in a library into a namespaced variant, to help avoid collisions with other addons.

## Usage

in any workflow (preferably after running the [BigWigsMods/packager](https://github.com/BigWigsMods/packager) step)

```yml
jobs:
  build:
    steps:
      # blah blah blah, grab externals
      - uses: emptyrivers/wow-xml-namespacer@v1.0.0
        with:
          path: path/to/xml/templates # This can be any glob, & is appended with /*.{xml, lua} before being sent to grep
          name: MyAmazingAddOn # reccomend using your addon name, to ensure uniqueness as far as blizzard is concerned
          pattern: MyAddOn #optional, defaults to MyAddOn

      # blah blah blah, upload to CF or wherever

```
