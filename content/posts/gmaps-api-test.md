---
title: "Uji Coba Google Maps API di GoHugo"
date: 2018-11-29T10:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyB73BzNYohKRTqDMrLP4yUfyJ_-nGWkasg&callback=myMap"></script>

<script>
function myMap() {
var mapProp= {
    center:new google.maps.LatLng(51.508742,-0.120850),
    zoom:5,
};
var map=new google.maps.Map(document.getElementById("googleMap"),mapProp);
}
</script>


