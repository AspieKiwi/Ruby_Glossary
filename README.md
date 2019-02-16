# Ruby Glossary

## Index
Access Control

Array

Ruby


## Access Controls
Ruby gives you three levels of protection at instance methods level, which may be pulbic, private or protected. Ruby does not apply any access control over instance and class variables:

This is a way of protecting the behaviours(methods) defined in a class from being called by other objects not in the same class or inherited from the same class. To limit a method's access, Ruby uses the keywords (actually, they're methods): "private and "protected", to distinguish them from public methods. Below is a quick summary of what these different levels of access are and where/when to use them. [Source](https://blog.joshsoftware.com/2014/01/09/access-control-in-ruby-public-protected-private/)

### Public Methods
Can be called by anyone. Methods are public by default except for initialize, which is always private.
[Source](https://www.tutorialspoint.com/ruby/ruby_object_oriented.htm)

By default, all the methods you define will be public, unless you use the private or protected keyword/metho to make them not public. Public methods describe the outside (outside of the class definition) behaviours of an object and are called with the object as the explicit receiver (thing you're calling the method on: receiver.method). Looking at our Person class below, or # speaker method is publick, so all instances of that class (read: objects) that you create, can call that # speak method. [Source](https://blog.joshsoftware.com/2014/01/09/access-control-in-ruby-public-protected-private/)

``` Ruby
class Person
   def speak
      puts "Hey, Tj!"
   end
end
you = Person.new
you.speak # "Hey, Tj!"
```
Output
```Ruby
Hey, Tj!
```
[Source](https://blog.joshsoftware.com/2014/01/09/access-control-in-ruby-public-protected-private/)

### Private Methods
Cannot be accessed or even viewed from outside the class. Only the class methods can access private members.
[Source](https://www.tutorialspoint.com/ruby/ruby_object_oriented.htm)

### Protected Methods
Can be invoked only by objects of the defining class and its subclasses. Access is kept within the family.
[Source](https://www.tutorialspoint.com/ruby/ruby_object_oriented.htm)

## Access Control Examples

``` Ruby
#!/usr/bin/ruby -w

# define a class
class Box
   # constructor method
   def initialize(w,h)
      @width, @height = w, h
   end

   # instance method by default it is public
   def getArea
      getWidth() * getHeight
   end

   # define private accessor methods
   def getWidth
      @width
   end
   def getHeight
      @height
   end
   # make them private
   private :getWidth, :getHeight

   # instance method to print area
   def printArea
      @area = getWidth() * getHeight
      puts "Big box area is : #@area"
   end
   # make it protected
   protected :printArea
end

# create an object
box = Box.new(10, 20)

# call instance methods
a = box.getArea()
puts "Area of the box is : #{a}"

# try to call protected or methods
box.printArea()
```

Output
``` Ruby
Area of the box is : 200
test.rb:42: protected method `printArea' called for #
<Box:0xb7f11280 @height = 20, @width = 10> (NoMethodError)
```
[Source](https://www.tutorialspoint.com/ruby/ruby_object_oriented.htm)


## Arrays
Literals of Ruby Arrays are created by placing a comma-separated series of object references between the square brackets. A trailing comma is ignored. [Source](https://www.tutorialspoint.com/ruby/ruby_variables.htm)


### Array Examples

``` Ruby
#!/usr/bin/ruby

ary = [ "fred", 10, 3.14, "This is a string", "last element", ]
ary.each do |i|
  puts i
end
```

Output
```
10
3.14
This is a string
last element
```

[Source](https://www.tutorialspoint.com/ruby/ruby_variables.htm)

## Object
Every object is an instance of a class and a class defines the state(variables) and behaviours(methods) of an object. An object is an entity with state and behaviour, as defined by its class. [Source](https://blog.joshsoftware.com/2014/01/09/access-control-in-ruby-public-protected-private/)



## Ruby
A class-based object-oriented programming language. [Source](https://blog.joshsoftware.com/2014/01/09/access-control-in-ruby-public-protected-private/)
