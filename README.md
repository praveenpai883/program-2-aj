<!DOCTYPE html>
<html>
<head>
 <title>AngularJS Shopping List App</title>
 <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js"> 
 </script>
</head>
<body>
<div ng-app="myApp" ng-controller="myCtrl">
<h1>Shopping List App</h1>
<ul>
<li ng-repeat="item in items">{{item}}</li>
</ul>
<input type="text" ng-model="newItem" placeholder="Enter New Item">
<button ng-click="addItem()">Add Item</button>
<button ng-click="removeItem(index)">Remove Item</button>
</div>
<script>
var app = angular.module("myApp", []);
app.controller("myCtrl", function($scope) {
$scope.items = ["Milk", "Bread", "Eggs"];
 $scope.addItem = function() {
 $scope.items.push($scope.newItem);
 $scope.newItem = "";
 };
$scope.removeItem = function(index) {
 $scope.items.splice(index, 1);
 };
});
</script>
</body>
</html>
