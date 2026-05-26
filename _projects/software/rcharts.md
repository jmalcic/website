---
title: RCharts
links:
  - url: https://github.com/jmalcic/rcharts
    type: GitHub repo
    address: jmalcic/rcharts
---

RCharts is a charting library for Action View which produces JS-agnostic SVG charts.

In the time since popular JS charting libraries were created, significant advances in CSS have made it possible to use 
the browser's rendering engine for more and more things where JS was previously unavoidable. 
Rather than starting from the assumption that client-side rendering in JS is inevitable for charts, 
RCharts builds on the premise that decent baseline functionality is now possible just with server-side rendering.

Being able to lean on the browser's rendering engine results in visibly improved client-side 
rendering performance and eliminates the scope for undesirable interactions with other rendering in JS. 
This makes it possible to layer interactivity on top of charts much more reliably, 
because the chart is no different from the rest of the page. 
One possible progressive enhancement would be panning and zooming, 
using a Stimulus controller to send a request to the server and reload the chart with different parameters.

RCharts was conceived specifically with Turbo morphing in mind. 
Because morphing is able to update pages and frames at the level of individual attributes, 
when CSS transitions are added to SVG elements, properties determining placement and size of elements 
can be animated like any other. Like other styling, you can control all aspects of the transitions using CSS, 
by overriding variables in the stylesheet provided or by using your own styles.
