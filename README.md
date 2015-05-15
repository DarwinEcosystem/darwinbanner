# Darwin's Home Page Banner by Darwin Ecosystem LLC

The Darwin's Home Page Banner offers a visual reprentation for a current topic trending keywords and clusters by geoloc.  The data is generated by our [KeywordMeme™ API](https://github.com/DarwinEcosystem/Documentation/wiki/REST-API-Resources).

<hr>

# Example

![Gif](https://raw.githubusercontent.com/DarwinEcosystem/darwinbanner/master/demo.gif)

Sample Query url: http://darwintrend.herokuapp.com/trends.json which auto geolocates and serves trends keywords.

<hr>

Here is a single trend item example:

```javascript
{
_id: "5551cec2b61f8703000eb808",
tag: "Lio",
country: 16,
created_at: "2015-05-12T09:58:26.843Z",
apiKeywords: [
{
term: "carlo",
weight: 100
},
{
term: "cocodrills",
weight: 8
},
{
term: "free",
weight: 8
},
{
term: "noir",
weight: 7
},
{
term: "special",
weight: 7
}
],
__v: 0
}
```

##### The country code mapping can be found at : https://github.com/felginep/hawttrends/blob/master/HawtTrends/Controller/HTTermsDownloader.m

##### The app uses [Telize](www.telize.com) to locate your country code, then uses it to query the trends for visualization,

You can request the trends for a specific country either by its country code number or abbreviation:

http://darwintrend.herokuapp.com/trends/1 or darwintrend.herokuapp.com/trends/US will achieve the same result.

<hr>

# Quick start
```
For development:
    npm install
    gulp

Then run in another terminal

    node index.js

The app leverages PIXIjs WebGL Canvas and [GSAP TweenMax](https://greensock.com/gsap).

Pixi Library was tweaked to achieve good circles.
```

```javascript
var segs =  Math.ceil(Math.abs(sweep) / (Math.PI * 2)) * 600;
```

PIXIjs uses only a low segments number to draw an arc, which makes the converting into graphics looking weird (pixellised circle)
Upping the segments variable allows to refine the shape to look like an actual circle.


#### Demo available at : http://darwinbanner.herokuapp.com

<hr>

# Skipping loading

For debugging purposes you can skip the loading animation by adding a sample data and initializing the app yourself:

Add `<script src="/sampleData.js"></script>` to the index.ntl scripts list.

Replace the lines
```javascript
//Setting up new app
app = new App();

//Fetching datas
app.fetchDatas();
```

with

```javascript
app = new App();
$('.loader').hide();
app.setup();
```

#### [Copyright (c) 2015 Darwin Ecosystem LLC](http://www.darwineco.com)
