# Preamble

This CSS file is a modified version of the layout capabilities in the javascript library [Polymer](https://www.polymer-project.org) (Version <= 0.5) from Google.

It provides flexible horizontal and vertical layout with CSS3 flexboxes.

# How to use

In your HTML-file simply include the `layout.css`:

    <head>
        ...
        <link rel="stylesheet" href="layout.css" />
        ...
    </head>

From then every following attributes and features are accessable.

# Attributes

## Horizontal and vertical layout

When a container includes the `layout` attribute, it can become a flex container.
You can specify `horizontal`, `vertical` to change the orientation:

    <div horizontal layout>
        <div>One</div>
        <div>Two</div>
        <div>Three</div>
    </div>

![Default layout](screenshots/default.png)

### Flexible children

Children of an element using the `layout` attribute can use `flex` attributes to control their own sizing. For example:

    <div horizontal layout>
        <div>Alpha</div>
        <div flex>Beta (flex)</div>
        <div>Gamma</div>
    </div>

![Flexible children](screenshots/flexible_children_horizontal.png)

The same is true for children of `vertical` elements:

    <div vertical layout style="height:250px">
        <div>Alpha</div>
        <div flex>Beta (flex)</div>
        <div>Gamma</div>
    </div>

![Flexible children](screenshots/flexible_children_vertical.png)

**Note**: for vertical layouts, the container needs to have a height for the children to flex correctly.

Children elements can be told to take up more space by including a "flex ratio" with the `flex` attribute. A flex ratio is specified with a number string: _one_, _two_, _three_, currently up to _twelve_.

For example, to make "Gamma" 2x larger than "Beta" and "Alpha" 3x larger, use `flex two` and `flex three`, respectively:

    <div horizontal layout>
        <div flex three>Alpha</div>
        <div flex>Beta</div>
        <div flex two>Gamma</div>
    </div>

![Flexible children](screenshots/flexible_children_ratio.png)

### Cross-axis alignment

By default, children stretch to fit the cross-axis (e.g. _vertical_ stretching in a _horizontal_ layout).

    <div horizontal layout>
        <div>Stretch Fill</div>
    </div>

![Cross-axis children](screenshots/cross_axis_alignment_default.png)

Center _across_ the main axis (e.g. _vertical_ centering elements in a _horizontal_ layout)
by adding `center`.

    <div horizontal layout center>
        <div>Center</div>
    </div>

![Cross-axis children](screenshots/cross_axis_alignment_center.png)

You can also position at the top/bottom (or left/right in `vertical` layouts) using `start` or `end`.

    <div horizontal layout start>
        <div>start</div>
    </div>
    
    <div horizontal layout end>
        <div>end</div>
    </div>

![Default layout](screenshots/cross_axis_alignment_start.png)

![Cross-axis children](screenshots/cross_axis_alignment_end.png)

## Justification

Justifying content is done with the `*-justified` attributes.

**Example** - start justified

    <div horizontal start-justified layout>
        <div>start-justified</div>
    </div>

![Justification](screenshots/justification_start.png)

**Example** - center justified

    <div horizontal center-justified layout>
        <div>center-justified</div>
    </div>

![Justification](screenshots/justification_center.png)

**Example** - end justified

    <div horizontal end-justified layout>
        <div>end-justified</div>
    </div>

![Justification](screenshots/justification_justified.png)

**Example** - equal space between each element

    <div horizontal justified layout>
        <div>justified</div>
        <div>justified</div>
        <div>justified</div>
    </div>

![Justification](screenshots/justification_justified.png)

**Example** - equal space around each element

    <div horizontal around-justified layout>
        <div>around-justified</div>
        <div>around-justified</div>
    </div>

![Justification](screenshots/justification_around_justified.png)

## Self alignment

Alignment can also be set per-child (instead of using the layout containers rules):

    <div horizontal layout>
        <div flex self-start>Alpha</div>
        <div flex self-center>Beta</div>
        <div flex self-end>Gamma</div>
        <div flex self-stretch>Delta</div>
    </div>

![Self alignment](screenshots/self_alignment.png)

## Wrapping

Wrapped layouts can be enabled with the `wrap` attribute.

    <div horizontal layout wrap style="width: 220px">
        <div>Alpha</div>
        <div>Beta</div>
        <div>Gamma</div>
        <div>Delta</div>
    </div>

![Wrapping](screenshots/wrapping.png)

## Reverse order

Layout direction can be mirrored with the `reverse` attribute.

    <div horizontal layout reverse>
        <div>Alpha</div>
        <div>Beta</div>
        <div>Gamma</div>
        <div>Delta</div>
    </div>

![Reverse order](screenshots/reverse.png)

# Image and text sources

The example images are screenshots taken from [https://www.polymer-project.org/0.5/docs/polymer/layout-attrs.html](https://www.polymer-project.org/0.5/docs/polymer/layout-attrs.html) (access date: 2015-20-06).

The text is modified and taken also from [https://www.polymer-project.org/0.5/docs/polymer/layout-attrs.html](https://www.polymer-project.org/0.5/docs/polymer/layout-attrs.html) (access date: 2015-20-06).
