# HTML5 design patterns

*Work in progress*

HTML5 design patterns for common modules.

## Page base

The basic structure of a HTML page. Language and text direction has been defined, it has a head tag with a title and meta character setting, the body tag is empty. 

	<!DOCTYPE html>
	<html lang="en-GB" dir="ltr">
		<head>
			<title>Page unique title</title>
			<meta charset="utf-8" />
		</head>
		<body>
		</body>
	</html>
	
The basic page structure with the addition of conditional comments setting Internet Explorer version specific classnames.
	
	<!DOCTYPE html>
	<!--[if IE 8]><html class="ie8" lang="en-GB" dir="ltr"><![endif]-->
	<!--[if IE 9]><html class="ie9" lang="en-GB" dir="ltr"><![endif]-->
	<!--[if !IE]><!--><html lang="en-GB" dir="ltr"><!--<![endif]-->
		<head>
			<title>Page unique title</title>
			<meta charset="utf-8" />
		</head>
		<body>
		</body>
	</html>
	
## Search

A simple search form, one that would commonly be found on as part of the header on most pages. 

	<form action="#" id="quick-search" role="search">
		<fieldset>
			<legend class="accessible">Quick search</legend>
			<label class="accessible" for="quick-search-input">Search</label>
			<input id="quick-search-input" name="quick-search-input" placeholder="Search this site" type="search" />
			<input id="quick-search-submit" name="quick-search-submit" type="submit" value="Submit" />
		</fieldset>
	</form>

## Page header

	<header id="header" role="banner">
		<p id="skip" class="accessible"><a href="#main">Skip to content</a></p>
		<div id="branding">
			<h1 class="accessible">Example site heading</h1>
			<a href="#"><img src="/images/brand-logo.png" alt="Brand logo description"></a>					
		</div>
		<nav id="navigation" role="navigation">
			<h2 class="accessible">Site navigation</h2>
			<ul class="navigation-menu">
				<li><a class="selected" href="#">Site section</a></li>
				<li><a href="#">Site section</a>
					<ul class="navigation-submenu">
						<li><a href="#">Site sub-section</a></li>
						<li><a href="#">Site sub-section</a></li>
					</ul>
				</li>
				<li><a href="#">Site section</a></li>
				<li><a href="#">Site section</a></li>
			</ul>
		</nav>
		<form action="#" id="quick-search" role="search">
			<fieldset>
				<legend class="accessible">Quick search</legend>
				<label class="accessible" for="quick-search-input">Search</label>
				<input id="quick-search-input" name="quick-search-input" placeholder="Search this site" type="search" />
				<input id="quick-search-submit" name="quick-search-submit" type="submit" value="Submit" />
			</fieldset>
		</form>
	</header>
	
## Article

	<article class="post">
		<header class="post-header">
			<h1 class="post-title">Example article title</h1>
			<p>Posted on <a href="#"><time datetime="2012-05-09">09 May 2012</time></a> by <a href="#">George Paterson</a></p>
		</header>
		<p>Example article text</p>
		<p>Example article text</p>
		<footer class="post-footer">
			<p>Posted in <a href="#">example</a> category</p>
			<p>Tagged as <a href="#">example tag</a></p>
			<p><a href="#">2 comments on example article</a></p>
		</footer>
	</article>
	
	<article class="post">
		<header class="post-header">
			<h1 class="post-title">Example article title</h1>
		</header>
		<div class="post-content">
			<p>Example article text</p>
			<p>Example article text</p>
		</div>
		<footer class="post-footer">
			<p>Posted in <a href="#">example</a> category</p>
			<p>Tagged as <a href="#">example tag</a></p>
			<p><a href="#">2 comments on example article</a></p>
		</footer>
	</article>

## Pagination

	<div class="pagination">
		<h2 class="pagination-title accessible">Pagination</h2>
		<p class="pagination-page">Showing page 3 of 10</p>
		<ul class="pagination-controls">
			<li class="pagination-first"><a href="#">First</a></li>
			<li class="pagination-previous"><a href="#">Previous</a></li>
			<li><a href="#">1</a></li>
			<li><a href="#">2</a></li>
			<li class="pagination-selected"><a href="#">3</a></li>
			<li><a href="#">4</a></li>
			<li><a href="#">5</a></li>
			<li class="pagination-next"><a href="#">Next</a></li>
			<li class="pagination-last"><a href="#">Last</a></li>
		</ul>
	</div>

## Sort controls

	<div class="sort">
		<div class="sort-items">
			<h2 class="sort-items-title">Items per page</h2>
			<ul class="sort-items-list">
				<li class="sort-items-selected"><a href="#">20 <span class="accessible">items per page selected</span></a></li>
				<li><a href="#">40 <span class="accessible">items per page</span></a></li>
				<li><a href="#">60 <span class="accessible">items per page</span></a></li>
				<li><a href="#">Show all <span class="accessible">items</span></a></li>
			</ul>
		</div>
		<div class="pagination sort-pagination">
			<h2 class="pagination-title accessible">Pagination</h2>
			<p class="pagination-status">Showing page 3 of 10</p>
			<ul class="pagination-controls">
				<li class="pagination-first"><a href="#">First</a></li>
				<li class="pagination-previous"><a href="#">Previous</a></li>
				<li><a href="#">1</a></li>
				<li><a href="#">2</a></li>
				<li class="pagination-selected"><a href="#">3</a></li>
				<li><a href="#">4</a></li>
				<li><a href="#">5</a></li>
				<li class="pagination-next"><a href="#">Next</a></li>
				<li class="pagination-last"><a href="#">Last</a></li>
			</ul>
		</div>
		<div class="sort-view">
			<h2 class="sort-view-title">Sort view by</h2>
			<ul>
				<li class="sort-view-selected"><a href="#">Grid view <span class="accessible">selected</span></a></li>
				<li><a href="#">List view</a></li>
			</ul>
		</div>	
	</div>

## Faceted navigation as links

	<nav id="facet-navigation" role="navigation">
		<header class="facet-navigation-header">
			<h2>Facet navigation</h2>
			<p><a href="#">Reset all <span class="accessible">faceted navigaton</span></a></p>
		</header>
		<section class="facet">
			<header class="facet-header">
				<h3 class="facet-title">Example single select</h3>
				<p class="facet-reset"><a href="#">Reset <span class="accessible">example single select facet</span></a></p>
				<p class="facet-description">Optional description of single select facet.</p>
			</header>
			<ul class="facet-list facet-single-select">
				<li class="facet-option facet-selected"><a href="#">Facet option <span class="accessible">selected</a></li>
				<li class="facet-option"><a href="#">Facet option</a></li>
			</ul>
		</section>
		<section class="facet">
			<header class="facet-header">
				<h3 class="facet-title">Example multi select</h3>
				<p class="facet-reset"><a href="#">Reset <span class="accessible">example multi select facet</span></a></p>
				<p class="facet-description">Optional description of multi select facet.</p>
			</header>
			<ul class="facet-list facet-multi-select">
				<li class="facet-option facet-selected"><a href="#">Facet option <span class="accessible">selected</a></li>
				<li class="facet-option"><a href="#">Facet option</a></li>
				<li class="facet-option facet-selected"><a href="#">Facet option <span class="accessible">selected</a></li>
			</ul>
		</section>
		<footer class="facet-navigation-footer">
			<p><a href="#">Reset all <span class="accessible">faceted navigaton</span></a></p>
		</footer>
	</nav>
	
## Product list

	<ul id="product-list">
		<li class="product">
			<article class="product-article">
				<figure class="product-figure">
					<a href="#">
						<img class="product-image" src="example.jpg" alt="Example product image" />
						<img class="product-offer" src="offer.jpg" alt="Example product is 50% off retail price" />
					</a>
				</figure>
				<h3 class="product-title">Short description of the example product.</h3>
				<p class="product-review">
					<a href="#">
						<span class="product-review-average">Average rating is 4 stars for this example product</span> 
						<span class="product-review-count">from 22 reviews.</span>
					</a>
				</p>
				<ul class="product-price">
					<li class="product-price-current">Current price of the example product</li>
					<li class="product-price-previous">Previous price of the example product</li>
					<li class="product-price-saving">Saving on previous price of the example product</li>
				</ul>
			</article>
		</li>
	</ul>
	
## Page footer

	<footer id="footer" role="contentinfo">
		<h2 class="accessible">Colophon</h2>
		<ul class="colophon">
			<li><a href="#">About</a></li>
			<li><a href="#">Contact us</a></li>
			<li>Copyright &copy; 2012</li>
		</ul>
	</footer>
	
	<footer id="footer" role="contentinfo">
		<section id="colophon">
			<h2 class="accessible">Colophon</h2>
			<ul class="colophon">
				<li><a href="#">About</a></li>
				<li><a href="#">Contact us</a></li>
				<li>Copyright &copy; 2012</li>
			</ul>
		</section>
	</footer>
	
	<footer id="footer" role="contentinfo">
		<div id="colophon">
			<h2 class="accessible">Colophon</h2>
			<ul class="colophon">
				<li><a href="#">About</a></li>
				<li><a href="#">Contact us</a></li>
				<li>Copyright &copy; 2012</li>
			</ul>
		</div>
	</footer>
