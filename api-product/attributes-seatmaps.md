###### Seatmap Properties

The seatmap properties are defined below:

| Req | Attribute        | Value       | Notes |
|:---:| ---------------- | ----------- | ----- |
|     | id               | id or name of the map | |
|     | img              | background image URL if any | |
|     | w                | width of this map in pixels | |
|     | h                | height of this map in pixels | |
|     | seats            | list of `seat` JSON objects (see next section) | | |

If the `img` tag is not given, then the seat map will be drawn with the styles
specified or using the default values.

The `seats` attributes are defined in the following table:

| Req | Attribute | Value       | Notes |
|:---:| --------- | ----------- | ----- |
|     | id        | area id or name | |
|     | s         | optional section tag (used by styles) | |
|     | sh        | shape options are: `r`=rect, `c`=circle, `p`=polygon | |
|     | pts       | comma-separated list of coordinate points, depending on the `sh` shape value | |
|     | q         | number of tickets in this area | |
|     | na        | this area is unavailable at the moment | |
|     | sub       | name of the `sub` or reference map of this area | |
|     | t         | title or label to show when a mouse hovers over it | | |

The `pts` attribute details the coordinate points of the specified `sh` (shape)
value.

* For circles, the pts contains three digits: "cx,cy,radius"
* For rectangles, "x1,y1,x2,y2"
* For polygons, "x1,y1,x2,y2,x3,y3,..."

Seatmap properties also have an optional `styles` attribute. This attribute has
a child attribute of `"s-tag"` which list the styles of the seat tag. The JSON
looks something like this:

    "styles": {
      "s-tag": {
        "stroke": "#RRGGBB",
        "width": 1,
        "fill": "#RRGGBB",
        "na": "#RRGGBB",
        "selected": "#RRGGBB",
        "opacity": 0.5
      }
    }

The `s-tag` attributes are defined as:

| Req | Attribute | Value       | Notes |
|:---:| --------- | ----------- | ----- |
|     | stroke    | colour as RGB #RRGGBB | |
|     | width     | 1 | |
|     | fill      | colour as RGB #RRGGBB | |
|     | na        | not available colour as RGB #RRGGBB | |
|     | opacity   | 0.5 half-transparent to background | | |

