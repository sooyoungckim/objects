---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---
   
<section class='slide' id="projects" style="padding-top:5em;">

    <div class="container">
      <div class="row">

      
      
        <div class="ten columns offset-by-one">
        
		<h2>Projects</h2>

		<div style="display:flex;flex-direction:row;flex-wrap:wrap;">
		{% for exhibit in site.data.exhibits %}
		
		       {% assign mod = forloop.index | modulo: 12 %}

			<a href="{{ exhibit.URL }}" target="_blank" class='tile' id='exhibit{{ exhibit.ID }}'>
				   <div class='tile-img'>
				     <img src='{{ "/assets/images/" | relative_url }}{{ exhibit.Thumbnail }}' style='width:100%'/>
				   </div>
				   <div class='tile-content color{{ mod }}'> 
				     	<h3>{{ exhibit.Title }}</h3>
					<cite>{{ exhibit.Author }}</cite>
				   </div>
			</a>
		
		{% endfor %}		
               </div>
        </div>

      </div> <!-- /.row -->
    </div> <!-- /.container -->
      
      
</section>
   
   
   
   
   

      
      
