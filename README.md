# Ruby Glossary

## Index
Access Control
Array


## Access Controls
Ruby gives you three levels of protection at instance methods level, which may be pulbic, private or protected. Ruby does not apply any access control over instance and class variables:

### Public Methods
Can be called by anyone. Methods are public by default except for initialize, which is always private.

### Private Methods
Cannot be accessed or even viewed from outside the class. Only the class methods can access private members.

### Protected Methods
Can be invoked only by objects of the defining class and its subclasses. Access is kept within the family.

## Access Control Examples

``` Ruby
#!/usr/bin/ruby -w

# define a class
class Box
  # constructor method
  def initialize(w,h)
      @width, @height = w, h
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
   def print
```



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
