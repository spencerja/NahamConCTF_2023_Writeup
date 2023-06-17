>Check out our museum of artifacts! Apparently, soon they will allow public submissions, just like in Animal Crossing!  
>
>Retrive the flag out of `/flag.txt` in the root of the file system.
-------------------------------
### Note, this challenge was not completed during the competition.
Entering the site, we are shown several boxes for museum artifacts, and a button to submit our own.

![Pasted image 20230617140807.png](https://github.com/spencerja/NahamConCTF_2023_Writeup/blob/main/Web/Images/Pasted%20image%2020230617140807.png)

Visiting the submission page, we are told submissions are not open to the public. Perhaps there is a way to impersonate an admin for submitting? There is no cookie token associated with this site and no visible admin page, so this route seems very unlikely. For an extra measure, I checked a POST request on the page to see the response:
```bash
$ curl -X POST http://challenge.nahamcon.com:30726/submit   
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 3.2 Final//EN">
<title>405 Method Not Allowed</title>
<h1>Method Not Allowed</h1>
<p>The method is not allowed for the requested URL.</p>
```
`POST` and `PUT` methods are both not allowed, so this is likely unimplemented.

Visiting the pages for existing artifacts, the url style immediately jumps out to me:
`http://challenge.nahamcon.com:30726/browse?artifact=angwy.jpg`

It immediately looks like an arbitrary read vulnerability might be possible. To check for this, I looked for the classic /etc/passwd.
`http://challenge.nahamcon.com:30726/browse?artifact=../../../../../../../../etc/passwd`
Unfortunately the artifact is not found.

After checking a number of different potential filter bypasses, nothing works well. Viewing the image source shows that the folder paths are `/public/<image>`, but even attempting `artifact=../public/angwy.jpg` was failing. I was able to define from current directory, but any other directory movements was met with an error:
`http://challenge.nahamcon.com:30726/browse?artifact=./angwy.jpg`

![Pasted image 20230617140639.png](https://github.com/spencerja/NahamConCTF_2023_Writeup/blob/main/Web/Images/Pasted%20image%2020230617140639.png)

Reviewing curl headers showed that the server is utilizing Python, so I also found that the python comment mark # was also being recognized.
`http://challenge.nahamcon.com:30726/browse?artifact=./cat.jpeg#asdfasdf`
