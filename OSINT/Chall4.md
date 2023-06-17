>Author: @Gary#4657  
>
>Head over to [https://osint.golf](https://osint.golf) and select **`chall4` under the NahamCon2023** category. Make sure to read the directions if you are unfamiliar with Geosint/Geoguessr!  
>_NOTE:_ The integrated compass direction is inconsistent with the actual panorama representation.
---------------------------------------
In the final Geosint challenge, we are given a drone shot of what seems to be a suburban area setting. We are too far away do identify anything such as the language on signs or country flags, but we can note the very large number of train track lanes. Some buildings in the distance appear to have uncommon architecture, but not enough for me to draw any conclusions. My first guess is to take the most eye-catching building and see what image searches can do for me.

![Screenshot from 2023-06-15 17-16-51.png](https://github.com/spencerja/NahamConCTF_2023_Writeup/blob/main/OSINT/Images/Screenshot%20from%202023-06-15%2017-16-51.png)

From this image, it was quickly identified as Bratislava Castle of Bratislava, Slovakia. This location does not match geographically, but the building's design and colors match very well. The second building I searched for is the neighboring church-like building.

![Screenshot from 2023-06-15 17-27-17.png](https://github.com/spencerja/NahamConCTF_2023_Writeup/blob/main/OSINT/Images/Screenshot%20from%202023-06-15%2017-27-17.png)

There were several identical matches for seemingly different buildings. However, one in particular mentions a castle with it in combination. [this web posting](https://www.komoot.com/highlight/3217858) seems to be reviewing it as a bike trail. Examining the geography in a google map search for `Schloss Ebenfurth`, it instantly became clear that this is the same location as the challenge.

![Pasted image 20230615173152.png](https://github.com/spencerja/NahamConCTF_2023_Writeup/blob/main/OSINT/Images/Pasted%20image%2020230615173152.png)

![Pasted image 20230615173224.png](https://github.com/spencerja/NahamConCTF_2023_Writeup/blob/main/OSINT/Images/Pasted%20image%2020230615173224.png)

I was unable to find the same capture on Google Maps, but since this is an arial view, we can get a pretty good idea where it might be without too much trouble.


`flag{2e57cfe16d7e1c5431aa3b99d0e713cb}`
