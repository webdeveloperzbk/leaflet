---
layout: tutorial_frame
title: Zoom Levels Tutorial
---
<script>

	var map = L.map('map', {
		minZoom: 1,
		maxZoom: 1,
		dragging: false
	});

	var cartodbAttribution = '&copy; <a href="https://skpdi.mosreg.ru">СКПДИ2 ЦРЦТ</a>, &copy; <a href="https://carto.com/attribution">CARTO</a>';

	var positron = L.tileLayer('https://{s}.basemaps.cartocdn.com/light_all/{z}/{x}/{y}.png', {
		attribution: cartodbAttribution
	}).addTo(map);

	var scaleControl = L.control.scale({maxWidth: 150}).addTo(map);

	setInterval(function () {
		map.setView([0, 0], 0, {duration: 1, animate: true});
		setTimeout(function () {
			map.setView([60, 0], 0, {duration: 1, animate: true});
		}, 2000);
	}, 4000);

	map.setView([0, 0], 0);
</script>
