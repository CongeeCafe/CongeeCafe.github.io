---
layout: post
title: Looking Through the Glass at Hack the North
featured-image: HackTheNorth_2014.jpg
---

This year, a thousand students from across the world gathered in Waterloo's Engineering 5 building for Hack the North, Canada's largest international hackathon.

As this was my first hackathon, I arrived with little knowledge of what to expect. I wasn't familiar with the structure of the event or what I was supposed to do when I got there. I didn't even have a project idea in mind. But somehow, the uncertainty didn't bother me -- it only made things more exciting.

Fortunately, soon after checking in, I was introduced to another fellow hackathoner by a friend I ran into. Since we were both looking for a team, we decided to work together on whatever we decide to make. Being with a partner made me feel more confident about the whole event. Although I wouldn't have minded working alone, I felt that working with someone else would be much more worthwhile.

During the opening events, my partner and I joined with two other people, making us a team of four. We just so happened to all be first year Waterloo students at our first hackathon. With the building so full, we were also fortunate to have a table in a nice classroom that my original partner found beforehand to work in. Our workplace had a great view of the hallways and workplaces around and beneath us. I found it a bit intimidating at first, but I soon learned to enjoy it. Settled down at our table together for the first time, we were calm but motivated, and we were ready to make something.

My team spent the next half hour deliberating on what our project should be. Our ideas were all over the place: a web app that maps the prevalence of a given job across different geographical regions, a smart Android app that tells you when to sleep based on your schedule for the next day, a Google maps-like app that gives step by step directions to each room on campus, and much more. Despite all the crazy ideas we had, we settled on something smaller and within the scope of a 3 day hackathon.

<h2>Introducing WatIsFood</h2>

Inspired by the popular WatIsRain app, WatIsFood aims to solve the hunger epidemic experienced by university students. The app helps them find food by mapping out all the open food serveries on campus. It also displays store details such as descriptions and operating hours.

{% include image.html url="/assets/blog/img/watisfood_splash.png" caption="The WatIsFood home screen" %}

Development for the app went smoothly at first, but as expected, we eventually ran into various problems. Being responsible for developing the map and marker display for each restaurant location, I faced the challenge of developing an efficient way to display this information.

<h3>Map drawing</h3>
I originally wanted to store and display the map as a vector file. This had the advantage of being able to zoom without losing image quality, which is essential when navigating a map. However, the lack of a native way to display vector files on Android and a suitable third party SVG library quickly led me back to the drawing board. With the option of having a vector map out, I decided to instead use a single high quality raster image. Of course, during testing, I was greeted with an abundance of out-of-memory errors due to the large size of the map. I tried to break down the map into smaller tiles, with separate tiles for each zoom level to improve image quality, but time restraints led me to back out from this approach. Eventually, I settled with just shrinking down the map image to an acceptable size. It definitely wasn't the best solution, but it'll work for now.

<h3>Marker drawing</h3>
Drawing store markers consisted of two parts: positioning the markers on the map and overlaying them on top of the map. Having a fixed size image made positing the store markers a breeze. The markers were positioned based on the coordinates of the stores on the image, and their visibility was determined by whether or not the store was open. Drawing them, however, required much more experimenting. The most obvious way to draw the markers was to overlay them on top of the map in separate ImageView. Unfortunately, this approach led to a lot of lag when panning and zooming on the map. The next option was to draw the markers directly on the map and display it as a single image. I used Android's built-in bitmap functions to merge the images, and after some more memory optimizations, the marker drawing was done.

<h3>Marker touch detection</h3>
This was the part of development that caused me the most headaches. The process seemed simple at first -- just get the coordinates of the touch event on the ImageView and check if it's within a certain radius of a marker. Despite being a seemingly straight forward task, I found a major issue during testing. Sometimes, the dialog that opened when tapping on a marker did not correspond with the store that the marker represented. This bug seemed to occur completely random at first, with some markers working one minute but not the next. After a few long hours of debugging, I found that the problem began occurring after the map has been zoomed. As the map image was originally set to fill the viewport, the top left-most corner of the map had the coordinates (0, 0) as desired. However, once the map had been zoomed out and is no longer filling the viewport, the coordinates of that particular point changed. The coordinates (0, 0) now represented the start of the ImageView and different coordinates represented the start of the map. In essence, the coordinates obtained were of the ImageView itself, not the image it was displaying. I tried to compensate for this behaviour by processing the numbers using the map zoom level and the screen dimensions but to no success. As time was running out, my team and I decided to disable map zooming altogether to prevent the bug from occurring. This was another Band-Aid fix that I was not proud of, but It was nice to finally move on to refine other parts of the app.

<h2>Wrapping up</h2>
We finally finished our app an hour or so before the submission time. Although several compromises were made during development, we were still surprised that we even got this far. The last few hours of the event was spent on preparing a presentation of our app. It turns out that we were the last team to present to our panel of judges, so we had a lot of time to spare. Unfortunately, when it was our turn to present, the judges didn't seem very interested. It might have been because we were the last of a hundred or so teams they saw that day, or our idea wasn't that interesting in the first place. It was understandable either way; we were novice hackathoners, and we were tired too.

Despite the sheer amount effort devoted to developing WatIsFood, our achievements with our project wasn't what made the event great. What made it great was being part of a community that was motivated for both their own achievements, and to help others reach theirs as well. We were fortunate meet developers from companies such as Instagram and Big Viking Games, who not only gave us insight about their job in the company and future employment opportunities, but also helped us with developing our app. I also enjoyed listening to the many seminars that were offered, including one where we got to do a small Q and A session with the president of Y Combinator, Sam Altman.

With so much to do, it's easy to get lost in it all. Looking out the window of our workspace down at the atrium below, you can see everybody buzzing around like bumblebees. But despite the chaos, you'll never have trouble finding someone that's happy to stop and chat, and this is where the magic comes from at Hack the North.

[*View WatIsFood on ChallengePost*](http://challengepost.com/software/watisfood)