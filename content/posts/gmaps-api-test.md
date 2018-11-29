---
title: "Uji Coba Google Maps API di GoHugo"
date: 2018-11-29T10:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
<div id="map" style="width:100%;height:400px;background:yellow"></div>

<script>
function myMap() {
    var uluru = {lat: -7.5457442, lng: 110.7995443,21}; 
    var map = new google.maps.Map(document.getElementById("map"), { 
      zoom: 5, 
      center: uluru 
    }); 
    var marker = new google.maps.Marker({ 
      position: uluru, 
      map: map 
    }); 
}
</script>
<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyB73BzNYohKRTqDMrLP4yUfyJ_-nGWkasg&callback=myMap"></script>

