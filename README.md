# project
<div>

<strong>Start: </strong>

<select id="start" onchange="calcRoute();">

  <option value="chicago, il">Chicago</option>

  <option value="st louis, mo">St Louis</option>

  <option value="joplin, mo">Joplin, MO</option>

  <option value="oklahoma city, ok">Oklahoma City</option>

  <option value="amarillo, tx">Amarillo</option>

  <option value="gallup, nm">Gallup, NM</option>

  <option value="flagstaff, az">Flagstaff, AZ</option>

  <option value="winona, az">Winona</option>

  <option value="kingman, az">Kingman</option>

  <option value="barstow, ca">Barstow</option>

  <option value="san bernardino, ca">San Bernardino</option>

  <option value="los angeles, ca">Los Angeles</option>

</select>

<strong>End: </strong>

<select id="end" onchange="calcRoute();">

  <option value="chicago, il">Chicago</option>

  <option value="st louis, mo">St Louis</option>

  <option value="joplin, mo">Joplin, MO</option>

  <option value="oklahoma city, ok">Oklahoma City</option>

  <option value="amarillo, tx">Amarillo</option>

  <option value="gallup, nm">Gallup, NM</option>

  <option value="flagstaff, az">Flagstaff, AZ</option>

  <option value="winona, az">Winona</option>

  <option value="kingman, az">Kingman</option>

  <option value="barstow, ca">Barstow</option>

  <option value="san bernardino, ca">San Bernardino</option>

  <option value="los angeles, ca">Los Angeles</option>

</select>

</div>



 <script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyC68rVKtnMXyFhH_S6jUtn9evJ51Yv3kVA&signed_in=true&callback=initMap"

        async defer></script>

<!-- <script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDVY9Uih2y2p8Uah4i0NuJBSRFVH1ibQPQ&signed_in=true&callback=initialize"

        async defer></script> -->

<script>





var directionsDisplay;

var map;



function initialize() {

  directionsDisplay = new google.maps.DirectionsRenderer();

  var chicago = new google.maps.LatLng(41.850033, -87.6500523);

  var mapOptions = {

    zoom:7,

    center: chicago

  }

  map = new google.maps.Map(document.getElementById("map"), mapOptions);

  directionsDisplay.setMap(map);

}



function calcRoute() {

  var start = document.getElementById("start").value;

  var end = document.getElementById("end").value;

  var request = {

    origin:start,

    destination:end,

    travelMode: google.maps.TravelMode.DRIVING

  };

  directionsService.route(request, function(result, status) {

    if (status == google.maps.DirectionsStatus.OK) {

      directionsDisplay.setDirections(result);

    }

  });

}

</script>


<style>      html, body {

        height: 100%;

        margin: 0;

        padding: 0;

      }

      #map {

        height: 100%;

      }

#floating-panel {

  position: absolute;

  top: 10px;

  left: 25%;

  z-index: 5;

  background-color: #fff;

  padding: 5px;

  border: 1px solid #999;

  text-align: center;

  font-family: 'Roboto','sans-serif';

  line-height: 30px;

  padding-left: 10px;

}</style>

<div id="floating-panel">

<strong>Select Train no: </strong>

<select id="train" onchange="calcRoute(this.options[this.selectedIndex].getAttribute('start'),this.options[this.selectedIndex].getAttribute('end'));">

<option start="" end="">Select Train no.</option>

<option start="delhi" end="lucknow">11111</option>

<option start="delhi" end="kanpur">12111</option>

<option start="delhi" end="mumbai">11311</option>

<option start="mumbai" end="goa">111141</option>

<option start="delhi" end="shimla">11115</option>

<option start="mumbai" end="pune">12211</option>

<option start="bareilly" end="dehradun">12524</option>

<option start="dehradun" end="haridwar">12346</option>

</select>

<strong>&nbsp;&nbsp;&nbsp; OR &nbsp;&nbsp;&nbsp;</strong>

<strong>Start: </strong>

<input type="text" id="start" style="width:10%;">

<strong>End: </strong>

<input type="text" id="end" style="width:10%;">

<input type="button" value="SEARCH" onclick="calcRoute1();">

</div><div id="map"></div>

<script src="https://maps.googleapis.com/maps/api/js?v=3.exp&sensor=false"></script>

<script>
 
