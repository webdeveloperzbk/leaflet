---
layout: tutorial_frame
title: Custom Icons Tutorial
---
<script>
	var map = L.map('map').setView([51.5, -0.09], 13);

	L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
		attribution: '&copy; <a href="https://skpdi.mosreg.ru">СКПДИ2 ЦРЦТ</a>'
	}).addTo(map);

	var LeafIcon = L.Icon.extend({
		options: {
			shadowUrl: 'leaf-shadow.png',
			iconSize:     [38, 95],
			shadowSize:   [50, 64],
			iconAnchor:   [22, 94],
			shadowAnchor: [4, 62],
			popupAnchor:  [-3, -76]
		}
	});

	var greenIcon = new LeafIcon({iconUrl: 'leaf-green.png'});

	var mGreen = L.marker([51.5, -0.09], {icon: greenIcon}).addTo(map);

</script>
