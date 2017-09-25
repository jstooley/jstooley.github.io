---
layout: post
title:  "CLI Gem Project"
date:   2017-09-25 04:03:31 +0000
---


I have now finished my first project on my path of learning to code; and I have to say it was a valuable experience to have.  Looking back the main problem I had will on this project was coming up with an idea for what I wanted my program to do. For me this turned out to be making a program about something I have been hearing a lot about lately. With the recent hurricanes hitting Texas and Florida there has been a focus on the weather. Which is how I decided to make my gem about weather. Once I had decided to make a gem about the weather the rest of the set up seemed straight forward. Every time I need to check the weather I go to weather.com; so that was the first site I looked at scraping and it turned out to be perfect. Next up was to start coding. 
	Setting up the gem was easy thanks to the CLi Data Gem Walkthrough video. I would highly recommend watching at least the part of the video that shows exactly how to start a gem, where to require your files and how to run your program from the bin folder. I’m sure that part alone saved me a an hours or two of searching around on google. 
After setting up the basic skeleton of a gem I started programming the CLI and almost immediately ran into the hardest part of my entire program. Which was to ask for someone’s zip code. The weather_finder gem([GitHub](hhttps://github.com/jstooley/weather_finder.gitttp://),[RubyGems](https://rubygems.org/gems/weather_finderhttp://)) I programed uses a zip code to find the weather in the US, but if an invalid US zip code is given the program would crash. To solve the problem of getting an invalid zip code I decided to get a text file of all valid US zip codes and use it to check the zip code that is entered by the user. I first used the code below to read the file.
```
def zip_code?(zip_code) 
    valid = false
    File.open("lib/weather_finder/all_usa_zip.txt").each do |zip| #read from file to test valid zip
      if zip.to_i == zip_code.to_i
        valid = true
      end
    end
    valid
  end
```
Notice that in the code above I have hard coded the path to the text file. When I tried to release this program as a gem this became a problem. When run as a gem a hard coded path will not find the file. This caused me a lot of confusion at first and because I had no idea why my gem would not work. I did some searching and found out that you need to use a relative path. How to do this is represented in the code below.


```
def zip_code?(zip_code) 
    valid = false
    zip_path = File.join(File.dirname(__FILE__), '/all_usa_zip.txt')
    File.open(zip_path).each do |zip| 
      if zip.to_i == zip_code.to_i
        valid = true
      end
    end
    valid
  end 
```

Such a small change but it was the largest problem I had while making the gem. 
	After the zip code validation problem the rest of programming the gem was straight forward. I made my prompts to the user and a class for scrapping the information from weather.com. All things that I have practiced in labs up to this point.  The only place in the lab that gave me trouble besides the file path was sending my gem to RubyGems.com. This was caused by some code in the gemspec file created by the gem bundler. The code below will stop you from pushing your gem to RubyGems.
```
Prevent pushing this gem to RubyGems.org. To allow pushes either set the 'allowed_push_host'
  to allow pushing to a single host or delete this section to allow pushing to any host.
  if spec.respond_to?(:metadata)
    spec.metadata["allowed_push_host"] = "TODO: Set to 'http://mygemserver.com'"
  else
    raise "RubyGems 2.0 or newer is required to protect against " \
      "public gem pushes."
  End
```
The problem can be easily fixed if you know what is causing it; just commenting the code out.
	At the end of this project I am left with a sense of accomplishment and have learned some valuable lessons about programing. I am already looking forward to my next project.


