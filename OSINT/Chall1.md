>Author: @Gary#4657  
>  
>Head over to [https://osint.golf](https://osint.golf) and select **`chall1` under the NahamCon2023** category. Make sure to read the directions if you are unfamiliar with Geosint/Geoguessr!
----------------------------------------------
First challenge places us on a golf course, at some kind of ceremony/speech.
The first object of interest is the large event banner, containing the phrase "all Thailand Premier Championship". There is more text, Road to (something), that I was unable to accurately read. 

![[Pasted image 20230615163821.png]]

Searching for `all Thailand`, we quickly see a webpage for a [golf tour org](https://www.allthailandgolftour.com/). It seems like the right track. One common word that I found appearing was Singha, which might be matching in our image's banner: "Road to Singha (something)". The final word was still not readable for me, but this is enough to go on. Searching the golf tour website, I found [all Thailand Premier Championship - Road to Singha Masters](https://www.youtube.com/embed/-HSBJw_06XQ?rel=0&wmode=transparent&autoplay=1) located on the media page. Following the link takes us to a video, and right away in the video we are given a location--Singha Park in Khon Kaen.

![[Pasted image 20230615164252.png]]

![[Pasted image 20230615164335.png]]
I found the tolerance to be rather strict, so I ended up locating the same exact capture on Google Maps as well.

![[Pasted image 20230615164520.png]]
Finally with the pinpointed location, we get the flag.

`flag{3e3d01a002db29fec2a5e10ec758b852}`