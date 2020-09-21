## Introduction to Web Mapping with Leaflet

### Working with Markers

Leaflet Markers are used to identify location on a digital map (static or interactive). Markers used are images (png), SVGs or custom HTML element. Leaflet provides the the basic image marker icon in .png file format. The marker consist of two images the icon and it's shadow. Other marker icon options include:
 
 - Circle Marker
 - Div Icons
 - Custom Image Icons

#### Displaying default Marker

Using the previous blog code we add the following

```javascript

    var nairobi = L.marker([-1.284945, 36.822625]).addTo(map);
```

![Empty Map](output/markers/default_marker.PNG)

The above code will add a marker located at Nairobi CBD. The above code creates a marker instance, which takes a required argument which can be an array of `[latitude, longitude]` or an instance of `L.LatLng` class such as `L.latLng(-1.284945, 36.822625);`. Always remember the order latitude then longitude.

We can provide descriptive information to the marker using popup. This will be covered in the next tutorial, however, it is as easy as: replace the above line with the following

```javascript
    var nairobi = L.marker([-1.284945, 36.822625]).bindPopup("I am Nairobi").addTo(map);
```
![Empty Map](output/markers/popup.PNG)

Clicking the marker the popup will be displayed.



### Cricle Markers

Circle markers creates marker either as SVGs or a Canvas element depending on the renderer selected.

```javascript
     // ....
    var tokyo = L.circleMarker([35.6769865,139.7603121]).bindPopup("I am Tokyo").addTo(map);
```

![Empty Map](output/markers/circle_marker.PNG)

The above code segment create a circle marker with default styling. Like the `L.marker` class the coordinates in the format described previously are required. Default is not always great and does not meet our needs. `L.circleMarker` inherits some properties to create custom styles on the svg. The styles are described using JavasScript object.
Replace the above code with the following.

```javascript
     // ....
   var tokyoStyle = {
        radius:30,
        fillOpacity:1,
        fillColor:"#ea9500",
        color:"#ea9500",
        weight:0
    };

    var tokyo = L.circleMarker([35.6769865,139.7603121], 
        tokyoStyle
    ).bindPopup("I am Tokyo").addTo(map);
```




