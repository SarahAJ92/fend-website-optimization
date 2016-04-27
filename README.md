##Website Performance Optimization portfolio project

This is a project from the Udacity Frontend Web Developer Nanodegree.
The first task was to optimize the index.html, achieving a PageSpeed Insights score of above 90.
The second task was to optimize pizza.html to run in 60 fps, and lowering the time it takes to resize the pizzas.

###Getting started
**Note: This is the source version of the project. To view the production code, please choose the dist branch of this repository**

To check out this project, clone the repository to your computer, and open index.html
I have uploaded the **dist** version of the site to http://www.orell.no/fend-website-optimization/ for use in PageSpeed Insights

###Optimizations

These are some of the optimizations that I have made to the website

####Index.html

* All images have been included in the project and reduced in size, instead of using external links
* Scripts were moved to the bottom of the page to keep them from blocking the CRP
* CSS included in html
* Perfmatters.js is included directly in the html
* All css and js have been minified

####pizza

The updatePositions() function made the site run very slow. This was fixed by moving the document.body lookup outside of the loop.
This caused way too many layouts to be triggered, and it did not need to be looked up every time for the function to work. I removed some repeat code and put into items variable.

The pizza slices was very slow to calculate, and this was because the old function calculated the new width in pixels for every single pizza.
Instead, I have simplified the function to use % widhts.

The loop used to generate the sliding pizzas were generating more pizzas than it is possible to display. Lowered number of loops.

Added a requestAnimationFrame every time the page is scrolled