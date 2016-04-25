##Website Performance Optimization portfolio project

This is a project from the Udacity Frontend Web Developer Nanodegree.
The first task was to optimize the index.html, achieving a PageSpeed Insights score of above 90.
The second task was to optimize pizza.html to run in 60 fps, and lowering the time it takes to resize the pizzas.

###Install

To check out this project, clone the repository to your computer, and open index.html

###Optimizations

These are some of the optimizations that I have made to the website

####Index.html

*All images have been included in the project and reduced in size, instead of using external links
*Scripts were moved to the bottom of the page to keep them from blocking the CRP
*CSS included in html
*Perfmatters.js is included directyl in the html
*All css and js have been minified

####pizza
The updatePositions() function made the site run very slow. This was fixed by moving the document.body lookup outside of the loop.
This caused way too many layouts to be triggered, and it did not need to be looked up every time for the function to work. I removed some repeat code and put into items variable.

The pizza slices was very slow to calculate, and this was because the old function calculated the new width in pixels for every single pizza.
Instead, I have simplified the function to only remove and add bootstrap classes to the randomPizzaContainer, and the CSS does the rest of the work.