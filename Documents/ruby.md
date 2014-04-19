# Ruby

  Ruby is a dynamic, open source programming language with focus on simplicity. It has an elegant syntax that is natural to read and easy to write. ruby has evry thing is object. even data type is an object.

  Ruby is a scripting language.
  
  Scripting language : There is no complier in scripting language. it compile the code on execution time.(in scripting language at the run time code compile line by line and execute)
  
  (in compiler language: compiler compile the program and convert code in to machine language and after that run the obj file)

#### Advantage of ruby

    * It is open source programming language with focus on simplicity.
    * It has an advance array class. - we dont need to define size before compilation
    * It is extensible - we can add external libraries in ruby and c
    * It encourages literate programming - we can add comment with program
    * It uses punctuation and capitalization creatively : for ex: All class names have 1st latter is capital. all instance is start with @. 
    * it has flexible syantax : ex: we can omit parenthese from function. we can omit return from the function
    * It is expressioon orienetes : we can write x= if a<0 then b else c

#### To understand how ruby interpreter works:

    http://coding.smashingmagazine.com/2012/05/24/beginners-guide-ruby/

    To know how interpreter and compiler work -> Documents/compiler-Interpreter
   
   
#### From where ruby script execute?

/home/homeuser/.rvm/bin/ruby at where rvm ruby execution file store

/usr/bin/env ruby at where system ruby, and not any of the rvm rubies.
  
This path is stored in ~/.profile file. and this file is executed autometically by displaymanager during the startup process desktop session

##### If there is no .profile file load in than how can ruby file execute? or how ruby file execute?
      
  for that we should know where our ruby install?
    so for that we find directory of ruby using 'which ruby'
  
  after find that we need to go in ruby directory
    and execute our ruby file.

  Why we need to do above process?

    because there is anhttp://example.com ruby execution file. without that file we can't execute that code.

    for ex: i try some step which is below
    1.  i write one ruby file named hello.rb
          puts "Hello World"
    2.  i try to run that file by command
          ruby hello.rb 
        and this executes the file.
    3.  now i remove the path and try to execute ruby file it isnt..
        why?
          because ruby made from a c language. So it is a execition file of c language. when we try ruby hello.rb we call the obj file of c with one argument and it is try to find the path of ruby execution file.

          ex : #include <stdio.h>
              int main( int argc, char *argv[] )  
              {
                 if( argv[1] != nil )
                 {

                    printf("The sum of the number is= %d", argv[0] + argv[1]);
                 }   
              }
              i write this code in file name addition.c. now when i try to execute this code i need to give arguments two that file
                addition.c 4 5
                and this give the output: The sum of the number is= 9

        same as Whole ruby is written in c language and when we write ruby hello.rb we call execution file of ruby with argument hello.rb. When we try to execute ruby file in another folder in which ruby execution file is nt exist, it is throw an error and we cant execute ruby script.
  
#### Ruby Vs C++

* ruby is scripting language and c++ is compiled language
* In ruby everthing is an object:
```ruby
5.class #=> Integer
Integer.class #=> Class
```
* In ruby you can reopen classes:
```ruby
5.double #=> Error: No such method
class Integer
  def double()
    self * 2
  end
end
5.double #=> 10
```
* Ruby has dynamic typing:
```ruby
x = 5
x.class #=> Integer
x = "lala"
x.class #=> String
```
* Ruby has blocks and a lot of methods that make good use of them:
```ruby
[1,2,3,4].map {|x| x+3} #=> [4,5,6,7]
[5,7,11,8].any? {|x| x>10} #=> true
[5,7,11,8].all? {|x| x>10} #=> false
5.times { puts "Hello world" } # Prints "Hello World" five times.
```

#### What is required to execute Ruby code?
    The file must have executioon permission.
    There must me loaded .profile file

#### How make ruby file executable?
    
    first write this line in the file. This line call ruby executable file from its path
        #!/usr/bin/ruby
    It is called a Shebang. It tells the program loader what command to use to execute the file. if we use RVM, A portable way (working, say, under Cygwin and RVM) would be:
        #!/usr/bin/env ruby Or #!/usr/bin/env ruby -w
    This will use the env command to figure out where the Ruby interpreter is, and run it.
    I think -w refers to enabling verbose mode or simply enabling error reporting.  
    
    Than give executable permission to the file 
      chmod +x hello 

#### Difference between require and load method.
    - The load method includes the named Ruby source file every time the method is executed.
    - require method loads any given file only once.
    - require_relative (introduced in Ruby 1.9) use for the location of the file we're loading is relative to the file we're loading it from - they're both in the same directory.
