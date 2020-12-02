---
layout: page
title: GatewayAutox.com Photos
permalink: /photos
comments: false
redirect_from: 
  - "/Photos"
---

Photos from Gateway Autocross Assocation Events


<script type="text/javascript"> 
$(document).ready(function(){    
$.getJSON("https://api.flickr.com/services/feeds/groups_pool.gne?jsoncallback=?",
      	{
      		lang: "en-us",
      		id: "2880274@N20",
      		format: "json"
      	}, displayImages);

	function displayImages(data) {

	var htmlString = "";

    	$.each(data.items, function(i,item){
        var sourceSquare = (item.media.m).replace("_m.jpg", "_m.jpg");
        var largeImage = (item.media.m).replace("_m.jpg", "_b.jpg");
        htmlString += '<a href="' + largeImage + '" ';
        htmlString += ' data-gallery ';
        htmlString += ' title="' + item.title + '"';
        //htmlString += ' data-ob_linkText="View on Flickr"';
        //htmlString += ' data-ob_link="' + item.link + '"';
		//htmlString += ' name="' + item.link + '"';
        //htmlString += ' data-ob_share="false"';
        htmlString += '>';
        htmlString += '<img title="' + item.title + '" src="' + sourceSquare;
        htmlString += '" alt="'; 
		htmlString += item.title + '" />';
        htmlString += '</a>';
    });

	$('#btimages').html(htmlString + "");



    document.getElementById('btimages').onclick = function registerGallery(event) {
        event = event || window.event;
        var target = event.target || event.srcElement,
            link = target.src ? target.parentNode : target,
            options = { index: link, event: event },
            links = this.getElementsByTagName('a');
        blueimp.Gallery(links, options);
    };


}
});

</script>


<div id="btimages"> </div> 




<h3><a href="https://www.flickr.com/groups/gatewayautox/">See more photos and add your own in our Flickr group</a></h3>

