# About
-> My walkthrough of the OSINT Captsone Challenge at the end of the course

## Challenge Scenario
You work for a law enforcement organisation, and you have been assigned to track a person-of-interest, that is believed to be associated with a hacking group that recently compromised a Managed Service Provider (MSP) and are trying to sell the stolen credentials on both the clear net and dark web. Another team is focusing on the dark web lead, so you have been tasked with using OSINT sources to build up a profile on the individual and attempt to locate any evidence that links them to the MSP breach and sale of account details. You have been provided with some information to start your investigation. You should use any of the sources or tools taught in this course, that you deem to be applicable and appropriate. We know that the email address used to register the Twitter account is fake, so do not include this in your report.

Your manager has provided you with the following starting information:

Twitter handle used by actor: @sp1ritfyre

# Investigation Steps
## google search
-> performing a google search of the username `sp1ritfyre` yields a number of interesting results. We get...
- a link to the target's [twitter account](https://twitter.com/sp1ritfyre?lang=en)
- a link to a [blogger website](https://www.blogger.com/profile/08313689826885886832) from someone with the same username

## twitter account
bio: Sec Researcher Gone Bad _//_ Malware Analysis _//_ C&C Infrastructure
mysterious link: https://cmVkaHVudC5uZXQK.xyz
joined 2019

## blogger website
otherwise empty website, contains a table with the following information
```Gender: Female
Location: 68747470733a2f2f73616d6d6965776f6f647365632e626c6f6773706f742e636f6d
```

- The value for the location field is base64 endcoded--decoding us gives us the url `https://sammiewoodsec.blogspot.com`

- contains email address `d1ved33p@gmail.com`

## personal website (blogspot)
- confimrs the target's personal email address ` d1ved33p@gmail.com`
- contains a About Me page with a table containing valuable information

```
Gender: Female

Industry: Technology

Occupation:Junior Penetration Tester

Location: Reading, United Kingdom

Introduction:	Hey, I'm Sam! Welcome to my profile! Be sure to check out my blog, and if you want to get in touch, email me :)

Interests: Security, Programming, Technology, Gaming, Photography, Camping

Favorite Movies: Ready Player One 2018

Favorite Music: The Beatles, Rolling Stones, Queen

Favorite Books: The Hunger Games series
```

- 23 years old

```
Hey everyone, my name is Sam, I'm 23, and currently working within the Cyber Security industry. It's an amazing industry that is ever-changing, so no two days are the same! I wanted to share with you my story about how I jumped into this world.



I studied ICT in college, and really enjoyed it. Learning how applications work, how devices talk to each other. It was all crazy. Eventually our course covered a module focus on Security, and despite being very quick and basic, I found myself wanting to know more. I'd spend some free time researching different hacking groups, such as LizardSquad (I remember them taking down Dyn, and DoSing Xbox Live and PSN as a result, pretty cool!) as well as Anonymous, and started reading about state-sponsored groups such as APT 28, and Turla Team.

I went off to University at Plymouth, and studied for a degree in Cyber Security and Forensics. I passed with a 1st degree, and shortly after I started working at PhilmanSecurityInc. I'm currently a junior pen tester, as I realised I preferred breaking stuff (Responsibly!) rather than fixing it.

I love the team here, and both Zach and Dave are great mentors, and constantly help me to develop and expand on my existing skills.

Lots more blog posts coming soon! :)
~ Sammie
```