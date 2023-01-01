- # Your First App
    - ## ng-repeat II
        - In the controller, we used products to store an array containing two objects.
        - Then in the view, we added <div ng-repeat="product in products">. Like ng-app and ng-controller, the ng-repeat is a directive. It loops through an array and displays each element. Here, the ng-repeat repeats all the HTML inside <div class="col-md-6"> for each element in the products array.
        - In this way, ng-repeat shows both products in the $scope.products array. Instead of writing the same HTML twice as before, we just use ng-repeat to generate the HTML twice.
            - ```html
// index.html

<div ng-repeat="product in products" class="col-md-6">
  <div class="thumbnail">
    <img ng-src="{{ product.cover }}">
    <p class="title"> {{ product.name }} </p>
    <p class="price"> {{ product.price | currency }} </p>
    <p class="date"> {{ product.pubdate | date }} </p>
  </div>
</div>```
            - ```javascript
// MainController.js

app.controller('MainController', ['$scope', function($scope) {
  $scope.title = 'My favorite books';
  $scope.promo = 'Get a free book;';
  $scope.products = [
    {
      name: 'The Book of Trees',
      price: 19,
      pubdate: new Date('2014', '03', '08'),
      cover: 'img/the-book-of-trees.jpg'
    },
    {
      name: 'Program or be Programmed',
      price: 8,
      pubdate: new Date('2013', '08', '01'),
      cover: 'img/program-or-be-programmed.jpg'
    }
  ]
}]);```
        - ## Directives
            - We’ve used a few directives so far - ng-app, ng-controller, ng-repeat, and ng-src. What can we generalize about directives?
            - Directives bind behavior to HTML elements. When the app runs, AngularJS walks through each HTML element looking for directives. When it finds one, AngularJS triggers that behavior (like attaching a scope or looping through an array).
        - **ng-click II**
        - Great! Each time you click on the number of likes, the number goes up. How does it work?
            - The ng-click is a directive. When <p class="likes"> is clicked, ng-click tells AngularJS to run the plusOne() function in the controller.
            - The plusOne() function gets the index of the product that was clicked, and then adds one to that product’s likes property.
        - Notice that the plusOne() doesn’t interact with the view at all; it just updates the controller. Any change made to the controller shows up in the view.
    - **Generalizations**
    - Congratulations! You built an AngularJS app from scratch. What can we generalize so far?
        - A user visits the AngularJS app.
        - The __view__ presents the app’s data through the use of __expressions__, __filters__, and __directives__. Directives bind new behavior to HTML elements.
        - A user clicks an element in the view. If the element has a directive, AngularJS runs the function.
        - The function in the __controller__ updates the state of the data.
        - The view automatically changes and displays the updated data. The page doesn’t need to reload at any point.
        - ![](local-asset://Geaux-Notes/IbtGn7chME.png)
        - 
- 
