---
layout: post
title: BlocChat
thumbnail-path: "img/blocchat.png"
short-description: A simple chat application.

---

{:.center}
![]({{ site.baseurl }}/img/blocchat.png)

## Explanation

Bloc Chat is a chat application built using the AngularJS framework. It allows you to create a username, new chatrooms, and post messages to those chatrooms. Each message posted includes the username of the person who posted it and the time and date it was posted.

## Problem

The requirements for Bloc Chat were:
1. It had to prompt the user to create a username before entering
2. There needed to be a way for the user to create a new chatroom
3. Each room would display the messages associated to that room only
4. Each message would display the date & time, and the username of the person who posted it

## Solution

When the page loads it checks to see if there is a username stored in a browser cookie. If there is no username, a modal pops up which prompts the user to enter a username.

In order to create a new chatroom, the user clicks the New Room button and a modal pops up asking for a room name. Once the room name is entered, it is stored in the database and is accessible to the user.

The ngClick directive was used to store the "active room" by invoking the `activeRoom()` function.
``` html
<ul class="room-list" ng-repeat="room in home.rooms">
  <li class="room-name" ng-click="activeRoom(room)">{{ room.$value }}</li>
</ul>
```
`activeRoom()`, when invoked, stores the argument passed into it which in this case is `room`, in the `$scope.currentRoom` variable.
``` javascript
$scope.activeRoom = function(room) {
  $scope.currentRoom = room;
  $scope.messages = Message.getByRoomId($scope.currentRoom.$id);
};
```
We then use data-binding to display the `$value` of the `currentRoom` variable.
``` html
<h1 class="main-section-title center">{{ currentRoom.$value }}</h1>
```

## Results

Username modal pops up when the page first loads.
{:.center}
![]({{ site.baseurl }}/img/username-modal.png)

New room modal pops up when you click the `New Room` button on the left side.
{:.center}
![]({{ site.baseurl }}/img/new-room-modal.png)

Current room name appears on the top right of the page as well as the messages associated with that room.
{:.center}
![]({{ site.baseurl }}/img/room-messages.png)

## Conclusion

Bloc Chat taught me how to implement Modals in an application using $uibModal. I had the opportunity to use Firebase while working on this project and learned how to make calls to the database as well as add new items to a database.
