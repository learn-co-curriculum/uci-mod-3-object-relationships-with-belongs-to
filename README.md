# Ruby Intro To Object Relationships with Belongs To

## Outline

We use a single class to represent each singular concept or model needed in our program.

For a music management application, you could imagine having an Artist class to represent the artists in your library and a Song class to represent the songs. Each class would have a name. In the real world, these concepts of an artist and a song relate to eachother, how might we model that relationship through a metaphor in our code.

We know objects have properties. So far we've seen these properties point to simple values like a string or an integer. We call these base types of objects that come with ruby primitives, Integer, Array, Hash, etc.

For simple concepts and properties, these primitives do fine as values. But what about for "complex" property values such as a relationship.

Let's see what we might try and why the following example doesn't work.

```
class Artist
  attr_accessor :name
end

class Song
  attr_accessor :name, :artist
end

kanye = Artist.new
kanye.name = "Kanye West"

runaway = Song.new
runaway.name = "Runaway"
runaway.artist = "Kanye West"
```

the string vs the object. but strings are objects. so are artists. Cant we just assign the object kanye as the value for the artist attribute of a song?

yes.

that example

This relationship is called a belongs to. a song can only have one artist.

it's entirely by convention, if you misuse artist= your song instance will break. you make a contract with the code you create to use it as designed.

why is that better
consistency (changing an artist name)
chaining of methods
relationship behaviors

what about artist.songs/kanye.songs? How do we make that work?
