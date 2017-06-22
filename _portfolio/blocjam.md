---
layout: post
title: Bloc Jams
thumbnail-path: "img/blocjams.png"
short-description: Music is meant to be listened too and Bloc Jams was made just for that. Through Bloc Jams five songs of classical origins can now be played straight from one's own computer.

---

{:.center}
![]({{ site.baseurl }}/img/blocjams.png)

## Explanation

My part to play in Bloc Jams, was divided into 3 parts, the home page, the album's list page, and the album's song list page. Much of the javascript, html, images, css and songs were already complete, however they were not organized to form a proper web page and that is what I was brought in to do.

## Problem

I was to bring together these vast lines of code to create a working website that would play the music provided and looking amazing while doing it. Furthermore I was needed to create working buttons within the album's song list page that would freely change between songs, while also showing which song was playing. I was originally using only javascript without any premade libraries but switched the project over to add the jQuery library to clean up many of the lines of code that could be switched out. This freed up space to avoid lower page performance while also allowing the code to look and feel easier to follow.

## Solution

Setting up the provided code was simply connecting the provided lines of code with where they were needed to go. Switching to jQuery to clean up lines of code is also proven to fix certain performance speeds on larger projects and while it was not required for this one, should more songs be added, then this would fix the problems that occur in the future. Furthermore, concerning the buttons on the bar within the album song list page, I used certain functions such as nextSongNumbedrCell and previousSongNumberCell to ensure that the seek bar provided a more convenient means of moving between songs. 

{% highlight javascript %}
var nextSong = function() {

    var currentSongIndex = trackIndex(currentAlbum, currentSongFromAlbum);
    currentSongIndex++;

    if (currentSongIndex >= currentAlbum.songs.length) {
        currentSongIndex = 0;
    }

    var lastSongNumber = currentlyPlayingSongNumber;

    setSong(currentSongIndex + 1);
    currentSoundFile.play();
    updateSeekBarWhileSongPlays();
    updatePlayerBarSong();

    var $nextSongNumberCell = $('.song-item-number[data-song-number="' + currentlyPlayingSongNumber + '"]');

    var $lastSongNumberCell = $('.song-item-number[data-song-number="' + lastSongNumber + '"]');

    $nextSongNumberCell.html(pauseButtonTemplate);

    $lastSongNumberCell.html(lastSongNumber);

};
var previousSong = function() {

    var currentSongIndex = trackIndex(currentAlbum, currentSongFromAlbum);
    currentSongIndex--;

    if (currentSongIndex < 0) {

        currentSongIndex = currentAlbum.songs.length - 1;

    }

    var lastSongNumber = currentlyPlayingSongNumber;

    setSong(currentSongIndex + 1);
    currentSoundFile.play();
    updateSeekBarWhileSongPlays();
    updatePlayerBarSong();

    $('.main-controls .play-pause').html(playerBarPauseButton);

    var $previousSongNumberCell = $('.song-item-number[data-song-number="' + currentlyPlayingSongNumber + '"]');

    var $lastSongNumberCell = $('.song-item-number[data-song-number="' + lastSongNumber + '"]');

    $previousSongNumberCell.html(pauseButtonTemplate);

    $lastSongNumberCell.html(lastSongNumber);

};
{% endhighlight %}

## Results

Testing the work was a constant necessity to ensure when errors occurred, it was known where the error was made and where the corrections needed to be provided. If certain buttons didn't do their job, such as certain instances when the next song button wouldn't change the song on the first click but on the second, I was able to go through that function and correct the mistake. This one in particular was concerning the currentSongIndex and it not recognizing that the first count was not recorded and lagged behind by 1.  

## Conclusion

{:.center}
![]({{ site.baseurl }}/img/blocjamssongs.png)

The final product was a success despite all of the set backs that occured. Certain buttons not doing what they were suppose to, the list of songs not showing up, or playing when they did, definantly caused delay, but in the end these problems were located and corrected. I will admit that I had doubts going into the project, it was my first real project after all and I had no real experience in this field at all before this but I am happy to state despite certain schedule delays, I found the project to come together quite well. I learned throughout this project how the codes came together and how to problem solve when they didn't. This project gave me the basic understanding of working on projects like these and helped me understand the was these languages communicated with each other to create a working website.