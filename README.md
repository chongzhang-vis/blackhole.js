blackHole.js
============

## Introduce

![Blackhole.js](http://i.imgur.com/6d588zV.png)

This library is child of two parents:  
* [WorldBank Contract Awards](http://d3.artzub.com/wbca/)
* [GitHub Visualizer](http://artzub.com/ghv)

The main objective of this library is the visualization of data that change over time.
Suitable for the visualization of such data as:
* Commits history ([GitHub Visualizer](http://artzub.com/ghv)) 
* Economic Indicators ([Distribution of Russian budget 2013](http://clearspending.artzub.com/), [LuckyLunch](http://works.artzub.com/luckylunch/))
* Network attacks ([NetMonitor](http://artzub.com/img/demo_netMon.gif)) 
* And etc.

Depends of [D3js](http://d3js.org)

## Structure

- [Quick Example](#qe)
- [Documentation](#api)
    - [Properties](#Properties)
    - [Settings](#Settings)
    - [Methods](#Methods)
- [For developers](#fd)

<a name="qe" />
## Quick Examples
  

> For fast look [Example I](http://codepen.io/artzub/pen/vcfyd)

We have data (generated by [script](http://codepen.io/artzub/pen/bIkvH.js)):

```json
[
  {
    "key": 119,
    "category": "nemo,",
    "parent": {
      "name": "cumque5",
      "key": 5
    },
    "date": "2014-01-29T15:39:45.340Z"
  },
  {
    "key": 96,
    "category": "nemo,",
    "parent": {
      "name": "cumque5",
      "key": 5
    },
    "date": "2014-01-29T19:56:18.885Z"
  },
  {
    "key": 125,
    "category": "nemo,",
    "parent": {
      "name": "cumque5",
      "key": 5
    },
    "date": "2014-01-30T01:00:53.648Z"
  },
  {
    "key": 51,
    "category": "nemo,",
    "parent": {
      "name": "eveniet1",
      "key": 1
    },
    "date": "2014-01-30T06:46:51.531Z"
  },
  {
    "key": 237,
    "category": "nemo,",
    "parent": {
      "name": "cumque5",
      "key": 5
    },
    "date": "2014-01-30T12:25:14.810Z"
  },
  //...
]
```

And code:

```html
<div id="canvas"></div>
<script src="http://d3js.org/d3.v3.min.js"></script>
<script src="http://lib.artzub.com/js/blackhole.js/blackhole.js"></script>
<script>
var data = rawData.map(function(d) {
        d.date = new Date(d.date);
        return d;
    })
    , stepDate = 864e5
    , d3bh = d3.blackHole("#canvas")
    ;

d3bh.setting.drawTrack = true;

d3bh.on('calcRightBound', function(l) {
        return +l + stepDate;
    })
    .start(data)
    ;
</script>
```

<a name="api" />
## Documentation

### Properties

* __version__
* __setting__

### Settings

* __alpha__
* __childLife__
* __parentLife__
* __edgeLife__
* __rateOpacity__
* __rateFlash__
* __blendingLighter__
* __increaseChildWhenCreated__
* __createNearParent__
* __zoomAndDrag__
* __zoom__
* __scale__
* __translate__
* __scaleExtent__
* __colorless__
* __colorlessFlash__
* __drawEdge__
* __drawChild__
* __drawChildLabel__
* __drawParent__
* __drawParentLabel__
* __drawPaddingCircle__
* __drawHalo__
* __drawTrack__
* __drawVanishingTail__
* __drawAsPlasma__
* __drawParentImg__
* __lengthTrack__
* __padding__
* __parentColors__
* __categoryColors__
* __skipEmptyDate__
* __realtime__
* __hasLabelMaxWidth__
* __asyncParsing__

### Methods

* __.IsRun__
* __.IsPaused__
* __.stop__
* __.pause__
* __.resume__
* __.selectNode__
* __.selectCategory__
* __.frozenCategory__
* __.parents__
* __.children__
* __.categories__
* __.categoryMax__
* __.sort__
* __.filter__
* __.speed__
* __.size__
* __.translate__
* __.scale__
* __.append__
* __.start__
* __.getCanvas__
* __.findStyleProperty__
* __.style__
* __.on__ = function(key, value) {...}  

    > ***key*** — string value form __keys__  
    > ***value*** — function  

    *keys*:  
    - __calcrightbound__
    - __processing__
    - __processed__
    - __stopped__
    - __beforeparsing__
    - __parsing__
    - __afterparsing__
    - __getchildlabel__
    - __getparentlabel__
    - __getselectedcolor__
    - __getvisiblebystep__
    - __getcreatenearparent__
    - __getname__
    - __getcategorykey__
    - __getcategoryname__
    - __getkey__
    - __getchildkey__
    - __getparentkey__
    - __getparent__
    - __getparentimage__
    - __getgroupby__
    - __getvalue__
    - __getparentradius__
    - __getchildradius__
    - __getparentposition__
    - __getparentfixed__
    - __finished__
    - __starting__
    - __started__
    - __mouseovernode__
    - __mousemove__
    - __mouseoutnode__
    - __particleattarget__
    
<a name="fd" />
## For developers

![ga](http://www.google-analytics.com/__utm.gif?utmwv=4&utmac=UA-28343295-16&utmdt=blackholeReadme&utmhid=2052327202&utmn=1)
