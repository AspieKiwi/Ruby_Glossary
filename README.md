# Ruby Glossary

## Index
Access Control

Array


## Access Controls
Ruby gives you three levels of protection at instance methods level, which may be pulbic, private or protected. Ruby does not apply any access control over instance and class variables:

### Public Methods
Can be called by anyone. Methods are public by default except for initialize, which is always private.
[Source](https://www.tutorialspoint.com/ruby/ruby_object_oriented.htm)

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
