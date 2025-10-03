# Advertisement

An ad displays third-party promotional content

## Types

#### Ad
A standard ad
> The following example uses a basic [AdSense implementation](https://support.google.com/adsense/answer/181947?ctx=as2&rd=2&ref_topic=29033). Your code will vary depending on your ad network.
```html
<div class="ui medium rectangle ad">
  <script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
  <ins class="adsbygoogle"
       style="display:inline-block;width:300px;height:250px"
       data-ad-client="ca-pub-4591861188995436"
       data-ad-slot="4640466102"></ins>
  <script>
  (adsbygoogle = window.adsbygoogle || []).push({});
  </script>
</div>
<div class="ui leaderboard ad">
  <script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
  <!-- Leaderboard -->
  <ins class="adsbygoogle"
       style="display:inline-block;width:728px;height:90px"
       data-ad-client="ca-pub-4591861188995436"
       data-ad-slot="6710577704"></ins>
  <script>
  (adsbygoogle = window.adsbygoogle || []).push({});
  </script>
</div>
<div class="ui banner ad">
  <script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
  <!-- Banner -->
  <ins class="adsbygoogle"
       style="display:inline-block;width:468px;height:60px"
       data-ad-client="ca-pub-4591861188995436"
       data-ad-slot="9803644904"></ins>
  <script>
  (adsbygoogle = window.adsbygoogle || []).push({});
  </script>
</div>
```
```html
<div class="ui medium rectangle ad">
  <!-- Ad Code Goes Here
  <ins class="adsbygoogle"
       style="display:inline-block;width:300px;height:250px"
       data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
       data-ad-slot="XXXXXXXXXX"></ins>
  <script>
  (adsbygoogle = window.adsbygoogle || []).push({});
  </script>
  !-->
</div>
<div class="ui leaderboard ad">
<!-- Leaderboard
<ins class="adsbygoogle"
     style="display:inline-block;width:728px;height:90px"
     data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
     data-ad-slot="XXXXXXXXXXXXXXXX"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>
!-->
</div>
<div class="ui banner ad">
<!-- Banner
<ins class="adsbygoogle"
     style="display:inline-block;width:468px;height:60px"
     data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
     data-ad-slot="XXXXXXXXXXXXXXXX"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>
!-->
</div>
```

#### Common Units
An advertisement can appear in common ad unit sizes
> These additional examples use the `test` variation to appear on the page. `ui ad` is best used as a wrapper for third party ad network content like [AdSense](http://www.google.com/adsense/start/) or [DoubleClick](http://www.google.com/doubleclick/publishers/welcome/).
```html
<div class="ui medium rectangle test ad" data-text="Medium Rectangle"></div>
<div class="ui banner test ad" data-text="Banner"></div>
<div class="ui leaderboard test ad" data-text="Leaderboard"></div>
<div class="ui large rectangle test ad" data-text="Large Rectangle"></div>
<div class="ui half page test ad" data-text="Half Page"></div>
```

#### Mobile
An ad can use common mobile ad sizes
> Mobile ads will automatically only appear on mobile browser viewports
```html
<div class="ui mobile leaderboard test ad" data-text="Mobile Leaderboard"></div>
<div class="ui mobile banner test ad" data-text="Mobile Banner"></div>
```

#### Rectangle
An ad can use a common rectangle ad unit size
```html
<div class="ui vertical rectangle test ad" data-text="Vertical Rectangle"></div>
<div class="ui small rectangle test ad" data-text="Small Rectangle"></div>
```

#### Button
An ad can use button ad unit size
```html
<div class="ui button test ad" data-text="Button"></div>
<div class="ui square button test ad" data-text="Square Button"></div>
<div class="ui small button test ad" data-text="Small Button"></div>
```

#### Skyscraper
An ad can use skyscraper ad unit size
```html
<div class="ui skyscraper test ad" data-text="Skyscraper"></div>
<div class="ui wide skyscraper test ad" data-text="Wide Skyscraper"></div>
```

#### Banner
An ad can use banner ad unit size
```html
<div class="ui banner test ad" data-text="Banner"></div>
<div class="ui vertical banner test ad" data-text="Vertical Banner"></div>
<div class="ui top banner test ad" data-text="Top Banner"></div>
<div class="ui half banner test ad" data-text="Half Banner"></div>
```

#### Leaderboards
An ad can use leaderboard ad unit size
```html
<div class="ui leaderboard test ad" data-text="Leaderboard"></div>
<div class="ui large leaderboard test ad" data-text="Large Leaderboard"></div>
<div class="ui billboard test ad" data-text="Billboard"></div>
```

#### Panorama
An ad can use panorama ad unit size
```html
<div class="ui panorama test ad" data-text="Panorama"></div>
```

#### Netboard
An ad can use netboard ad unit size
```html
<div class="ui netboard test ad" data-text="Netboard"></div>
```

## Variations

#### Centered
An advertisement can appear centered
```html
<div class="ui centered banner test ad"></div>
```

#### Test
A advertisement can be formatted to help verify placement
> You can adjust the text displayed for your test ad placement by changing the value of `data-text`
```html
<div class="ui medium rectangle test ad" data-text="Ad Unit 1"></div>
<div class="ui medium rectangle test ad" data-text="Ad Unit 2"></div>
```
