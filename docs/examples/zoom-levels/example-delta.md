---
layout: tutorial_frame
title: Zoom Levels Tutorial
---
<script>

	var map = L.map('map', {
		minZoom: 0,
		maxZoom: 18,
		zoomSnap: 0,
		zoomDelta: 0.25
	});

	var cartodbAttribution = '&copy; <a href="https://skpdi.mosreg.ru">СКПДИ2 ЦРЦТ</a>, &copy; <a href="https://carto.com/attribution">CARTO</a>';

	var positron = L.tileLayer('https://{s}.basemaps.cartocdn.com/light_all/{z}/{x}/{y}.png', {
		attribution: cartodbAttribution
	}).addTo(map);

	var ZoomViewer = L.Control.extend({
		onAdd: function () {
			var container = L.DomUtil.create('div');
			var gauge = L.DomUtil.create('div');
			container.style.width = '200px';
			container.style.background = 'rgba(255,255,255,0.5)';
			container.style.textAlign = 'left';
			map.on('zoomstart zoom zoomend', function (ev) {
				gauge.innerHTML = 'Zoom level: ' + map.getZoom();
			});
			container.appendChild(gauge);
			return container;
		}
	});

	var zoomViewerControl = (new ZoomViewer()).addTo(map);

	map.setView([0, 0], 0);
</script>
