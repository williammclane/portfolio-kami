---
layout: post
title: Bloc Chat
thumbnail-path: "img/blocipedia.png"
short-description: We must be able to communicate with each other. We must have Bloc Chat!

---

{:.center}
![]({{ site.baseurl }}/img/blocipedia.png)

## Explanation

The purpose of Bloc Chat was to create a site that would be able to hold multiple chat rooms, be able to send messages through those chat rooms, and have the site recognize two or more different visitors, referring to them by their typed username.

## Problem

My job within Bloc Chat was very hands on and it was divided into 5 different stories; creating a list of chat rooms, the ability to create chat rooms, make sure that the messages are listed in the correct chat rooms, ensure that each visitor has their username display and finally to be able to send messages. I used to given foundation of the product and expanded from there into my list of problems.

## Solution

I first linked the code to firebase, allowing me to use it already designed fundimentals for the chatroom. From there I used javascript to create individuality to the rooms and allowed the user to create more.

I then proceeded to allow items to be stored in the rooms using roomId and allowing messages as well as usernames into the id.
{% highlight javascript %}
        this.currentRoom = function(room) {
            this.currentChatRoom = room.$value;
            currentChatId = room.$id;
            this.messages = Message.getByRoomId(room.$id);
        };
{% endhighlight %}
After that I would use cookies to allow the site to recognize individual visitors.
{% highlight javascript %}
function BlocChatCookies($cookies, $uibModal) { 
    var currentUser = $cookies.get('username'); 
    if (!currentUser || currentUser === '') { 
      $uibModal.open({ 
        templateUrl: '/templates/cookie.html', 
        controller: 'CookieCtrl',  
        controllerAs: 'cookie'
      }) 
    } 
  }
{% endhighlight %}
Finally using the cookies I was able to allow messages written by the visitor to be saved into the roomId instead of premade items.

## Results

By dividing the real problem of making a chat room into multiple steps, I was able to locate problems as they occured. Such times as when the site failed to recognize new visitors or to even save the cookie was a key issue that would have taken much longer to find had the whole problem had not be divided.

## Conclusion

In the end I was able to get the system to work. The chat rooms could be created at whim and messages could be typed in them to be saved. Furthermore the site would demand a username before one could enter. One of my largest problems was getting to site to recognize users. Using cookies was a new concept to me and it was difficult for me to get it to work as I wished. I found that to be the most difficult section of the project.
{:.center}
![]({{ site.baseurl }}/img/blocchatusername.png)
The usual way I would locate where a problem occured was not working and it took a lot of trail and error to find the source of the problem. This project taught me different ways to problem solve for issues in the code which will be invaluable in the future.
