## Notes on the RentPath repository

We created this fork so that we could add a RequireJS wrapper and use the code as a Bower dependency. Hopefully that will be the extent of the changes. However if you make more changes, please be careful that you open PRs on the "dev" branch of this repo and not on the "master" branch of the upstream repo: [combatwombat/marker-animate](https://github.com/combatwombat/marker-animate).

Original README content follows...

# Animated marker movement in Google Maps

A nice alternative to `marker.setPosition(latLng)`. Include jQuery and jQuery Easing Plugin for more easing options.

Demo: http://robsite.net/static/markermove/markermove.html (click on the map)

**Update: For a much nicer and unobtrusive marker animation library based on this one, check out [marker-animate-unobtrusive](https://github.com/terikon/marker-animate-unobtrusive)**

## Usage

Include `markerAnimate.js` after Google Maps and call `animateTo` on a `google.maps.Marker`:

    // params:
    // newPosition        - the new Position as google.maps.LatLng()
    // options.duration   - animation duration in ms (default 1000)
    // options.easing     - easing function from jQuery and/or the jQuery easing plugin (default 'linear')
    // options.complete   - callback function. Gets called, after the animation has finished

    marker.animateTo(newPosition [, {easing: 'easeOutBounce', duration: 1000, complete: function(){}}]);

## Example

    var marker = new google.maps.Marker({position: new google.maps.LatLng(0,0), map: myMap, title: 'Hello World!'});
    var newPosition = new google.maps.LatLng(13,42);

    // move marker in 1000ms and with linear animation.
    marker.animateTo(newPosition); 

    // or with callback and options for easing and duration in milliseconds. Needs jQuery Easing Plugin.
    marker.animateTo(newPosition, {  easing: "easeOutBounce",
                                     duration: 1000,
                                     complete: function() {
                                       alert("animation complete");
                                     }
                                  });
