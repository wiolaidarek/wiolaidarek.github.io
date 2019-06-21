---
title: Mapa
---

Lokalizację parkingów, karczmy i oczywiście Sanktuarium na Wiktorówkach znajdziecie na poniższej mapie.

<div id='googleMap' style='width: 100%; height: 400px;'></div>

<script>
	var center = {
		'lat': 49.30,
		'lng': 20.05
	} 
	var parking_wierch = {
		'position': {lat: 49.284997, lng: 20.112783},
		'label': 'Parking',
	}
	var parking_oswald = {
		'position': {lat: 49.282389, lng: 20.087412},
		'label': 'Parking',
	}
	var tatrzanski_bor = {
		'position': {lat: 49.311799, lng: 20.061783},
		'label': 'Tatrzański Bór - przyjęcie',
	}
	var wiktorowki = {
		'position': {lat: 49.265404, lng: 20.086490},
		'label': 'Sanktuarium Wiktorówki - ślub',
	}

	function myMap() {
	  var mapProp = {
	    disableDefaultUI: true,
	    center: new google.maps.LatLng(center['lat'], center['lng']),
	    zoom: 12,
	    zoomControl: true,
	    scaleControl: true,
	    rotateControl: true,
	    mapTypeId: 'terrain',
	  };

	  var map = new google.maps.Map(document.getElementById("googleMap"), mapProp);

	  var marker = new google.maps.Marker(
		  {
			position: tatrzanski_bor['position'],
			label: tatrzanski_bor['label'],
			map: map,
		  }
	  ) 
	  var marker = new google.maps.Marker(
		  {
			position: wiktorowki['position'],
			label: wiktorowki['label'], 
			map: map,
		  }
	  ) 
	  var marker = new google.maps.Marker(
		  {
			position: parking_wierch['position'],
			label: parking_wierch['label'], 
			map: map,
		  }
	  ) 
	  var marker = new google.maps.Marker(
		  {
			position: parking_oswald['position'],
			label: parking_oswald['label'], 
			map: map,
		  }
	  ) 
	}
</script>
<script src="maps.js" charset="utf-8"></script>
<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyBN52hWwgKhTTfdSzwtqH1JbWtCJLYHcwY&callback=myMap"></script>
