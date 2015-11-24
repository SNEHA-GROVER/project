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



 
