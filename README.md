# analytics

A module that acts as an interface to Google Analytics

### Usage

```JavaScript

var Analytics = require("analytics");
var a = new Analytics();

$(function() {

  $("a.outbound-link").click(function (e) {

    a.trackEvent({
      eventCategory: "event category",
      eventAction: "click",
      eventLabel: "label",
      hitCallback: a.sendTo($(e.target).attr("href"), e) // tracks link, THEN sends to URL
    });

  });

  $(".hover").hover(function (e) {

    a.trackEvent({
      eventCategory: "event category",
      eventAction: "hover",
      eventLabel: "label"
    });

  });

});

```
