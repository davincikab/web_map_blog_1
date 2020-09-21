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
    var tokyo = L.circleMarker([35.6769865,139.7603121]).bindPopup("I am Tokyo").addTo(map);
```

![Empty Map](output/markers/circle_marker.PNG)


