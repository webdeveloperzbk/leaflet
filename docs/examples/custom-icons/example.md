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
	var redIcon = new LeafIcon({iconUrl: 'leaf-red.png'});
	var orangeIcon = new LeafIcon({iconUrl: 'leaf-orange.png'});

	var mGreen = L.marker([51.5, -0.09], {icon: greenIcon}).bindPopup('I am a green leaf.').addTo(map);
	var mRed = L.marker([51.495, -0.083], {icon: redIcon}).bindPopup('I am a red leaf.').addTo(map);
	var mOrange = L.marker([51.49, -0.1], {icon: orangeIcon}).bindPopup('I am an orange leaf.').addTo(map);

</script>
