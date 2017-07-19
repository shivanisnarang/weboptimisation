## Website Performance Optimization portfolio project

#### Part 1: Optimize PageSpeed Insights score for index.html

-- To improve the pagespeed score, i have inlined the font and style css files and put the 'async' tag on Google analytics JS file and therefore reducing CRP to one. I used ImageMagick to compress the images "views/images/pizzeria.jpg" and "img/profilepic.jpg" and used Grunt tool and its plugins (grunt-contrib-uglify, grunt-contrib-cssmin, grunt-contrib-htmlmin) to minify all of the necessary files to reduce the amount of bytes that needed to be downloaded. I have used npm install command to save these plugins as dev dependencies in the package.json file.All the minified files are in the production folder and the production folder also has images that has been compressed.

Website: https://shivanisnarang.github.io/weboptimisation/

Pagespeed Score: https://developers.google.com/speed/pagespeed/insights/?url=https%3A%2F%2Fshivanisnarang.github.io%2Fweboptimisation%2F





#### Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js. 

You might find the FPS Counter/HUD Display useful in Chrome developer tools described here: [Chrome Dev Tools tips-and-tricks](https://developer.chrome.com/devtools/docs/tips-and-tricks).

-- In the for loop of function updatePositions(), it calculates phase 200 times when it only calculates 5 unique values. In order to solve this duplicity problem, the phase calculation is calculated outside the for loop and stored in an array for access.

Replaced a slow method to access the DOM, document.querySelectorAll(), with a faster method, document.getElementsByClassName().

In updatePositions(), the function accesses the DOM with the class name 'mover' every time the user decides to scroll. It only needs to access the DOM once. It is moved into the global scope for updatePositions() to use.

For the eventListener 'DOMContentLoaded', in the for loop, 200 pizzas aren't seen in rendering. I dynamically create the pizza amount based on height of user's web browser.

To reduce painting, I used transform translateZ and translate3d and backface-visibility hidden CSS properties to have them in their own seperate layers.

In changePizzaSizes(size) function, the variables dx and newwidth don't need to be iterated in the for loop because it's all the same width. The variables were put outside the for loop to reduce time. Created a local variable randomPizzaContainer to store the elements by class name randomPizzaContainer to decrease the amount of times it needs to access the DOM.

### Customization with Bootstrap
The portfolio was built on Twitter's <a href="http://getbootstrap.com/">Bootstrap</a> framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>
