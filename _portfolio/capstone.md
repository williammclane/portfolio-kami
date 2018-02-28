---
layout: post
title: Capstone
thumbnail-path: "img/capstone.PNG"
short-description: My first game I every created. An idea that started from pong to a game all its own.

---

{:.center}
![]({{ site.baseurl }}/img/capstone.PNG)

## Explanation

The purpose of my Capstone was to create something all my own. I have always loved games and I wanted to create one that I could be proud to say was mine and have people enjoy playing it. 

## Problem

The problem I had with this project was the multiple components that needed to be randomly reset without causing the game to reset entirely. As I wanted the different levels to be different than the last I needed to have the obstacles (green) change locations on their own.

## Solution

My solution was to create each object with its own variable. 
{% highlight javascript %}
        objectPosX = Math.floor(Math.random() * (canvas.width/10)) * 10;
        objectPosY = Math.floor(Math.random() * (canvas.height/10)) * 10;
        objectSize = 10;

        objectPosX1 = Math.floor(Math.random() * (canvas.width/10)) * 10;
        objectPosY1 = Math.floor(Math.random() * (canvas.height/10)) * 10;
        objectSize1 = 10;
{% endhighlight %}
Then I just created a random coordinates creator to go off whenever the player reached the goal.
{% highlight javascript %}
    function animate(){
    if (levelNumber >= 6){
        alert("You Win!");
        window.location.reload();
    }
    if (collision(xPos, yPos, xEndPos, yEndPos) <= 0){
        xPos = 0;
        yPos = 0;
        levelNumber += 1;
{% endhighlight %}

## Results

The end results created a game that gave randomly generated levels within the space provided.

## Conclusion

In the end I created my first game that is playable and in some ways fun. By no means am I done with it. Despite it being a project required by my apprenticeship, I am still proud of my game and I intend to continue working on it as a hobby so that others can enjoy it as well.