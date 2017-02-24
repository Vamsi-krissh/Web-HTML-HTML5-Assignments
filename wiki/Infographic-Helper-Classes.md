#Infographic Helper Classes#
Applying the following classes to elements will change their text color or their layout. You can see a complete list of instructions on helper classes used at [wiki/Helper-Classes](Helper-Classes.md)

##Text Colors##
Use the following class names to alter the colors of text:

1. **Associates by Region**
	* text-blue-dark-sm
	* text-blue-light-sm
	* text-green-sm
2. **Associates by Segment**
	* text-purple-light-sm
	* text-orange-sm
	* text-yellow-light-sm
	* text-blue-light-sm
	* text-brown-sm
	* text-green-sm
	* text-gold-sm
	* text-pink-sm
	* text-teal-alt-sm
	
**Example:**

`<li><a href="..." class="text-green-sm">Some text</li>`

##Grids##
Use the following to generate a 3-column grid (at the `lg` breakpoint) on the unordered list:

```
	<ul class="grid">
		<li class="grid-col-lg col-lg-4-12"></li>
		<li class="grid-col-lg col-lg-4-12"></li>
		<li class="grid-col-lg col-lg-4-12"></li>
	</ul>
```

##Completed Example##

```
	<div class="pad-sm-0-4">
	    <h3 class="space-sm-3-0">ASSOCIATES BY REGION</h3>
	    <ul class="grid">
	        <li class="grid-col-lg col-lg-4-12"><p class="text-blue-dark-sm">41.1% Americas</p></li>
	        <li class="grid-col-lg col-lg-4-12"><p class="text-blue-light-sm">19.3% Asia Pacific</p></li>
	        <li class="grid-col-lg col-lg-4-12"><p class="text-green-sm">39.6% Europe, Africa and Middle East</p></li>
	    </ul>
	</div>
	
	<div class="pad-sm-0-4">
	    <h3 class="space-sm-3-0">ASSOCIATES BY SEGMENT</h3>
	    <ul>
	        <li class="grid-col-lg col-lg-4-12"><p class="text-purple-light-sm">48.8% Petcare</p></li>
	        <li class="grid-col-lg col-lg-4-12"><p class="text-orange-sm">2.6%Food</p></li>
	        <li class="grid-col-lg col-lg-4-12"><p class="text-yellow-ligh-sm">0.8% Drinks</p></li>
	        <li class="grid-col-lg col-lg-4-12"><p class="text-blue-light-sm">22.4% Wrigley</p></li>
	        <li class="grid-col-lg col-lg-4-12"><p class="text-brown-sm">22.5% Chocolate</p></li>
	        <li class="grid-col-lg col-lg-4-12"><p class="text-green-sm">0.1% Symbioscience</p></li>
	        <li class="grid-col-lg col-lg-4-12"><p class="text-gold-sm">1.3% Corporate</p></li>
	        <li class="grid-col-lg col-lg-4-12"><p class="text-pink-sm">1.3% Multi-sales Europe</p></li>
	        <li class="grid-col-lg col-lg-4-12"><p class="text-teal-alt-sm">1.3% Other</p></li>
	    </ul>
	</div>
```