---
layout: post
title:      "Objects are just objects"
date:       2018-03-14 12:24:22 -0400
permalink:  objects_are_just_objects
---


Programming involves a whole lot of scary words and acronyms. For every one thing you learn, it seems like that just unveils four or five more scary words that you now need to worry about. It’s funny though, how when something that seems scary or weird or unattainable suddenly clicks, it becomes a big head-slapping, why-was-that-so-hard thing. I felt that way about Object Oriented Programming.

When I first saw or read about the concept, it seemed like this crazy thing that only superhero programmers understood. After learning a little and scratching the surface, I realized that it’d not that tough, and the name perfectly describes whats going on.

Humans operate differently than computers, and that’s one of the underlying challenges when it comes to programming. I can look at a car, and I instantly know what it is, what it does, what it can’t do, and how to use it. I just do. However, it’s far more challenging to explain a car, to define it in perfect detail. There’s so much involved under the hood, in the suspension, etc. So if I’m trying to tell a computer what a car is, I have go from the ground up. This is where objects come into play.

The term ‘object’ is a perfect description because, well, we’re trying to explain real world objects to computers. Everything around us could be thought of as objects. For our computers to help us with whatever it is we’re working on, we need to tell them about any real-world objects that they need to work with.

So lets describe that car. Cars come from factories. In computer-land an object’s factory is called its class. The class describes the important attributes of any car, and how it works.

```class Car

end```

This is just saying “hey computer, there’s a thing(object) called a Car, and this class is the template for every Car.” We can then add all of the things that make up what a car is.

```class Car

	def color
	#sets the color of the car
	end

	def radio
	#set what’s playing
	end	

	def engine
	#stuff about the engine
	end

	def headlights
	#stuff about headlights
	end

	def odometer
	#stores the mileage
	end

end``` 
Obviously there’s much more to a car than an engine, an odometer, and a couple of headlights, this is the basic concept. Anything between def and end is called a ‘method’ and here’s where you can write code that defines the different parts of the car and any functionality they have. Without getting into too much jargon, you can write some code in odometer to alert the driver every 3000 miles to get an oil change. You could write code in the engine method that defines how the engine and all of its parts work. You can even write other methods (think ‘cylinder’, ‘transmission’, or ‘oil_pump’) that tell the computer how the engine works.
So now that all this is in place, you can use the Car class to make new cars:
```prius = Car.new```
This is simply saying “Ok, computer, make a new car, and call that car a prius.” You can then, depending on how it’s set up, assign attributes to the car.
```prius.color = “Blue”
prius.mileage = 0
prius.radio = “Radiohead”```
Here you’re saying “that prius we just built a minute ago is Blue, has 0 miles (it’s brand new after all) and let’s listen to some Radiohead, Ok, computer?” Get it? Terrible.
Now you can make something else…
```jeep = Car.new```
...and keep going until you’ve get all the cars built if you wanted. Every car you made would have all the same attributes that 
Now obviously this is a little bit simpler that how say Toyoda or Jeep actually has their databases set up, but hopefully it takes a little bit of the scary out of the term “object oriented.”
