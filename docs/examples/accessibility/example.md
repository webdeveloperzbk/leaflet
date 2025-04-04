---
layout: tutorial_frame
title: Accessible markers
---

<script>

	var map = L.map('map').setView([55.755819, 37.617644], 4);

	var tiles = L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
		maxZoom: 19,
		attribution: '&copy; <a href="https://skpdi.mosreg.ru">СКПДИ2 ЦРЦТ</a>'
	}).addTo(map);

	var marker = L.marker([50.4501, 30.5234], {alt: 'Moscow'}).addTo(map)
		.bindPopup('Moscow, never sleep!');

</script>
