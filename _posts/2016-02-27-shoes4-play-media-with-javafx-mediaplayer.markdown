---
layout: post
title:  "Play media on Shoes4 with JavaFX MediaPlayer"
date:   2016-02-27 16:37:00
---

For Shoes4 the [video](https://github.com/shoes/shoes4/issues/113) method is not yet available so if you want to play an mp3 file for example on [Shoes4](https://github.com/shoes/shoes4) you can use the [MediaPlayer](https://docs.oracle.com/javafx/2/api/javafx/scene/media/MediaPlayer.html) class from JavaFX.
<br />
There is only one trick that you're not allowed to miss and the trick is that you have to create a new instance of [JFXPanel](https://docs.oracle.com/javafx/2/api/javafx/embed/swing/JFXPanel.html) because the MediaPlayer is depending on the JavaFX interface. Otherwise you will experience an `java.lang.IllegalStateException: Toolkit not initialized` exception.
<br />
For example to play `file.mp3` you can run the following code:

{% highlight ruby %}
require 'shoes'

java_import javafx.scene.media.Media
java_import javafx.scene.media.MediaPlayer
java_import javafx.embed.swing.JFXPanel

Shoes.app do
  JFXPanel.new

  media = Media.new("file:///Users/andrei/Downloads/a.mp3")
  @player = MediaPlayer.new(media)
  @player.play
end
{% endhighlight %}
