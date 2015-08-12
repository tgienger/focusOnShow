#<center>Focus On Show
##<center>Angular directive

**what?**

I wanted a way to auto select an element 
(textarea, textbox, etc) when ng-show evaluates to true.

This directive will take either a string id or an array of strings
id's and select the next available (empty) element when they are
shown.

**How?**

Copy the file to your project directory. Add it to your
app dependencies:

    angular.module('yourApp', ['FocusOnShow']);
	
Then simply add the attribute to the element that has
ng-show directive and selectable child elements:

    <div focus-on-show="['selectFirst','selectSecond', {{ctrl.item.id}}]" ng-show="isShown">
		<input type="text" id="selectFirst" ng-model="ctrl.item.name>
		<input type="number" id="selectSecond" ng-model="ctrl.item.price">
		<textarea id="{{ctrl.item.id}}" ng-model="ctrl.item.description">
	</div>
	
Or just one item at a time:

    <div focus-on-show="{{ctrl.item.id}}" ng-show="isShown">
		<input type="text" id="selectFirst" ng-model="ctrl.item.name>
		<input type="number" id="selectSecond" ng-model="ctrl.item.price">
		<textarea id="{{ctrl.item.id}}" ng-model="ctrl.item.description">
	</div>
	
Whenever the element's ng-show evaluates to true it will select the chosen
element or the next empty element if there is a list.