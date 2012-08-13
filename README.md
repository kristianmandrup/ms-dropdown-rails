# ms-dropdown for Rails

[ms-dropdown](http://www.marghoobsuleman.com/jquery-image-dropdown) packaged for use with Rails asset pipeline :)

See: [ms-Dropdown on github](https://github.com/marghoobsuleman/ms-Dropdown)

## Install

`gem 'ms-dropdown-rails'`

## Usage

In `application.js` manifest:

```javascript
//= require jquery.dd.min
```

In `application.css` manifest:

```css
/*
 *= require ms-dropdown/dd
*/
```

## Usage and customization

See the specs folder for html files that demonstrate the functionality and various options.
Also see the [ms-dropdown](http://www.marghoobsuleman.com/jquery-image-dropdown) site for more configuration instructions.

```html
  <select style="width:200px" class="mydds" name="cart-w-labels">
      <option value="calendar" selected="selected" title="icons/icon_calendar.gif">Calendar</option>
      <option value="shopping_cart" title="icons/icon_cart.gif">Shopping Cart</option>
      <option value="cd" title="icons/icon_cd.gif">CD</option>
      <option value="email" title="icons/icon_email.gif">Email</option>
      <option value="faq" title="icons/icon_faq.gif">FAQ</option>
      <option value="games" title="icons/icon_games.gif">Games</option>
      <option value="music" title="icons/icon_music.gif">Music</option>
      <option value="phone" title="icons/icon_phone.gif">Phone</option>
      <option value="graph" title="icons/icon_sales.gif">Graph</option>
      <option value="secured" title="icons/icon_secure.gif">Secured</option>
      <option value="video" title="icons/icon_video.gif">Video</option>
  </select>
```

Or without option labels:

```html
  <select style="width:50px" class="mydds" name="cart">
      <option value="calendar" selected="selected" title="icons/icon_calendar.gif"></option>
      <option value="shopping_cart" title="icons/icon_cart.gif"></option>
      <option value="cd" title="icons/icon_cd.gif"></option>
  </select>
```

Make any `<select>` with the class `mydds` into an ms-dropdown:

```javascript
$(document).ready(function() {

  try {
    $(".mydds").msDropDown().data("dd");
  } catch(e) {
    console.log("Error: "+e.message);
  }
})
```

### Sprite image example

Use the `class` option attribute on each option to identify the sprite image/class to use.

```html
<select name="websites1" id="websites1" style="width:200px;" >
  <option class="calendar" value="calendar">Calendar</option>
  <option class="shoppingcart" value="shopping_cart">Shopping Cart</option>
  <option class="cd" value="cd">CD</option>
  <option class="email" value="email">Email</option>
  <option class="faq" value="faq">FAQ</option>
  <option class="games" value="games">Games</option>
  <option class="music" value="music">Music</option>
  <option class="phone" value="phone">Phone</option>
  <option class="graph" value="graph">Graph</option>
  <option class="secured" value="secured">Secured</option>
  <option class="video" value="video">Video</option>
</select>
```

```javascript
$(document).ready(function() {
  $("#websites1").msDropDown({useSprite:'sprite'}).data("dd");
});
```

The `useSprite:` option takes the name of the sprite to use.

Here the example sprite from the `dd.css` file.

```css
.dd .ddChild a.sprite, .dd .ddChild a.sprite:visited {
  background-image:url(/assets/ms-dropdown/sprite.gif);
  background-repeat:no-repeat;
  padding-left:24px;
}

.dd .ddChild a.calendar, .dd .ddChild a.calendar:visited {
  background-position:0 -404px;
}
.dd .ddChild a.shoppingcart, .dd .ddChild a.shoppingcart:visited {
  background-position:0 -330px;
}
.dd .ddChild a.cd, .dd .ddChild a.cd:visited {
  background-position:0 -439px;
}
.dd .ddChild a.email, .dd .ddChild a.email:visited {
  background-position:0 -256px;
}
.dd .ddChild a.faq, .dd .ddChild a.faq:visited {
  background-position:0 -183px;
}
.dd .ddChild a.games,
.dd .ddChild a.games:visited {
  background-position:0 -365px;
}
.dd .ddChild a.music, .dd .ddChild a.music:visited {
  background-position:0 -146px;
}
.dd .ddChild a.phone, .dd .ddChild a.phone:visited {
  background-position:0 -109px;
}
.dd .ddChild a.graph, .dd .ddChild a.graph:visited {
  background-position:0 -73px;
}
.dd .ddChild a.secured, .dd .ddChild a.secured:visited {
  background-position:0 -37px;
}
.dd .ddChild a.video, .dd .ddChild a.video:visited {
  background-position:0 0;
}
```

### Custom sprite

Simply replace with your own sprite name (here `flags`) and adjust background positions for the sprite classes (here `denmark`).

```css
.dd .ddChild a.flags, .dd .ddChild a.flags:visited {
  background:url(/assets/world_flags_16.png) top left no-repeat;
  padding-left:24px;
}

.dd .ddChild a.denmark, .dd .ddChild a.calendar:visited {
  background-position:0 0px; width: 16px; height: 16px;
}
```

Use the sprite!

```javascript
$("#websites1").msDropDown({useSprite:'flags'}).data("dd");
```

```html
<select name="country" id="country" style="width:200px;" >
  <option class="denmark" value="denmark">Denmark</option>
  ...
</select>
```

Enjoy ;)

## Contributing to ms-dropdown-rails
 
* Check out the latest master to make sure the feature hasn't been implemented or the bug hasn't been fixed yet.
* Check out the issue tracker to make sure someone already hasn't requested it and/or contributed it.
* Fork the project.
* Start a feature/bugfix branch.
* Commit and push until you are happy with your contribution.
* Make sure to add tests for it. This is important so I don't break it in a future version unintentionally.
* Please try not to mess with the Rakefile, version, or history. If you want to have your own version, or is otherwise necessary, that is fine, but please isolate to its own commit so I can cherry-pick around it.

## Copyright

Copyright (c) 2012 Kristian Mandrup. See LICENSE.txt for
further details.

