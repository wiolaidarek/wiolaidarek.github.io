---
title: Mapa
image:
  path: /assets/images/car-map.jpg
  thumbnail: /assets/images/car-map-thmb.jpg
  caption: Uważajcie na siebie, nie zgubcie się
---

Lokalizację parkingów, karczmy i oczywiście Sanktuarium na Wiktorówkach znajdziecie na poniższej mapie.
Droga między karczmą a parkingami prowadzi przez Murzasichle - nie dajcie się poprowadzić nawigacji przez leśne ścieżki i trzymajcie się głównych dróg! Jej przebycie zajmuje ok. 20 minut.

<div id='googleMap' style='width: 100%; height: 400px;'></div>

<script>
	var icon_base_path = 'http://maps.google.com/mapfiles/kml/shapes/' 
	var icon_parking_path = icon_base_path + 'parking_lot.png'
	var church_icon_path = icon_base_path + 'church.png'
	var party_icon_path = icon_base_path + 'bars.png'
	var center = {
		'lat': 49.30,
		'lng': 20.05
	} 
	var parking_wierch = {
		'position': {lat: 49.284997, lng: 20.112783},
		'label': 'Parking - Wierch Poroniec',
		'icon': icon_parking_path,
	}
	var parking_oswald = {
		'position': {lat: 49.282389, lng: 20.087412},
		'label': 'Parking - Zazadnia',
		'icon': icon_parking_path,
	}
	var tatrzanski_bor = {
		'position': {lat: 49.311799, lng: 20.061783},
		'label': 'Tatrzański Bór - przyjęcie i noclegi',
		'icon': party_icon_path,
	}
	var wiktorowki = {
		'position': {lat: 49.265404, lng: 20.086490},
		'label': 'Sanktuarium Wiktorówki - ślub',
		'icon': church_icon_path,
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
			icon: tatrzanski_bor['icon'],
			map: map,
		  }
	  ) 
	  var marker = new google.maps.Marker(
		  {
			position: wiktorowki['position'],
			label: wiktorowki['label'],
			icon: wiktorowki['icon'],
			map: map,
		  }
	  ) 
	  var marker = new google.maps.Marker(
		  {
			position: parking_wierch['position'],
			label: parking_wierch['label'], 
			icon: parking_wierch['icon'],
			map: map,
		  }
	  ) 
	  var marker = new google.maps.Marker(
		  {
			position: parking_oswald['position'],
			label: parking_oswald['label'], 
			icon: parking_oswald['icon'],
			map: map,
		  }
	  ) 
	}
</script>
<script src="maps.js" charset="utf-8"></script>
<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyBN52hWwgKhTTfdSzwtqH1JbWtCJLYHcwY&callback=myMap"></script>
