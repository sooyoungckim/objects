---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---
<section id="home">
<div class="container">
  <div class='row'>
    <div class='one column'>&nbsp;</div>
  
    <div class='five columns' id="c1" style="height:700px;display: flex;flex-direction: column;justify-content: center;">
        <h1 class='mobile-site-title' style="margin-top:30%;text-align:center;font-weight:bold;">αντικείμενα / objects</h1>

        <div id="rotating-imgs" style='display:none;'>


	<div class="cycle-slideshow">

	{% for exhibit in site.data.exhibits %}
	    <img id="img{{ exhibit.ID }}" width="100%" src="{{ "/assets/images/" | relative_url }}{{ exhibit.Thumbnail }}" alt="{{ exhibit.Title }}">
	{% endfor %}
	</div>
        
        <!--
        <div class="cycle-slideshow">
        {% for exhibit in site.data.exhibits %}
	    <img width="100%" src="{{ "/assets/images/" | relative_url }}{{ exhibit.Thumbnail }}" alt="{{ exhibit.Title }}">
	 {% endfor %}
	</div>
	
	
	

	 <ul class="image-cycle" 
	    data-target="li" 
	    data-interval="9000" 
	    data-width="60%" 
	    data-speed="9000" style="display:inline-block;">
		{% for exhibit in site.data.exhibits %}
		 {% if forloop.index < 2 %}
		    <li class='active'><img id="img{{ exhibit.ID }}" class='image-cycle-img' src="{{ "/assets/images/" | relative_url }}{{ exhibit.Thumbnail }}" data-cycle-title="{{ exhibit.Title }}" alt="{{ exhibit.Title }}" /></li>
		{% endif %}
		 {% if forloop.index > 1 %}
		    <li><img id="img{{ exhibit.ID }}" class='image-cycle-img' src="{{ "/assets/images/" | relative_url }}{{ exhibit.Thumbnail }}" data-cycle-title="{{ exhibit.Title }}" alt="{{ exhibit.Title }}" /></li>
		{% endif %}	
		{% endfor %}	  
	</ul>
	-->
	</div>
    
    </div>
    <div class="six columns" id="c2" style="margin-left:0px;height:700px;">
       <img class="site-title" src="{{ "/assets/images/logo2.svg" | relative_url }}" style="height:100%;width:auto;" />
    </div>
  </div>
</div>
</section>




<script>

var w = jQuery(window).width();
var h = jQuery(window).height();

jQuery("#c1").css('height',h+'px');
jQuery("#c2").css('height',h+'px');

setTimeout(function(){
    jQuery("#rotating-imgs").fadeIn();
}, 300);

jQuery(".cycle-slideshow img").each(function(i,v){
  var id = jQuery(v).attr('id');
  var tooltip = jQuery(v).attr('alt');
  tippy( "#"+id, { content: tooltip});
});


</script>


<script src="{{ "/assets/js/cycle.js" | relative_url }}"></script>
<script>
//var ex1 = new Cycle('.image-cycle');
</script>
