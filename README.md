# Week 2 - Distributed class

## Preparation 
### Git 
Set your email and username:

```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```
### Get the code
Fork this repo, then clone your fork locally

### How to update a fork from the original repo
##### Configuring a remote for a fork
To sync changes you make in a fork with the original repository, you must configure a remote that points to the upstream repository in Git.
Learn more: https://help.github.com/articles/configuring-a-remote-for-a-fork/

##### Syncing a fork
First configuring a remote for a fork with the upstream repository - as explained above
Sync a fork of a repository to keep it up-to-date with the upstream repository.
Learn more: https://help.github.com/articles/syncing-a-fork/

Note the tip: Syncing your fork only updates your local copy of the repository. To update your fork on GitHub, you must push your changes.

## Practice ~45 min

What would you like to work on?
* Variables - strings, numbers, etc
* Functions - how do they work, examples
* Classes & Objects
* Handling exceptions - raise, rescue e.t.c.
* Loops
* Arrays and hashes (looping with blocks)
* Blocks - creating your own <- advanced, we can cover them next week

## Reading and Writing to Files ~45 min

#### Writing to a file

Using the File class:

```ruby
file_name = "example.txt"
file = File.open(file_name, "w")
file.puts "This is text"
file.close
```

### Excercises

Use exception handling to make sure that code above always closes the file

### Writing to a file - cont.

Using block notation:

```ruby
file_name = "example.txt"
File.open(file_name, "w"){ |file| file.puts "Contents of the file"}
```
The file is automatically closed when the block ends


### Reading a file

There are a few options to read a file:

```ruby 
file = File.open("example.txt", "r")
contents = file.read
puts contents   
file.close
```

and

```ruby
f = File.open("my/file/path", "r") 
f.each_line do |line| 
  puts line 
end 
f.close
```

Using a block:

```ruby
contents = File.open("sample.txt", "r"){ |file| file.read }
puts contents
```

The file is automatically closed when the block ends

### readlines and readline

A very common approach to reading files:

```ruby
File.open("example.txt").readlines.each do |line|
   puts line
end
```

This is referred when dealing with large files:

```ruby
file = File.open("example.txt", 'r')
while !file.eof?
   line = file.readline
   puts line
end
file.close
```
Note: don't forget to use exception handling in this example

Readline loads the entire file at once into memory. While this is fine for most applications, this is not good practice if the file is very large, especially if it is running on a server that is serving multiple users. - Ref http://ruby.bastardsbook.com/chapters/io/

##### Exercises
Create an audit log for the Bank class
* Each time a transfer happens, write the details to a comma seperated file (csv). 
* Name the file: audit_log.csv
* each row should contain a time stamp, the two account numbers and the value that was transferred

## Refactoring Demo ~45 min

Code refactoring is the process of restructuring existing computer code – changing the factoring – without changing its external behavior. Refactoring improves nonfunctional attributes of the software. Advantages include improved code readability and reduced complexity; these can improve source code maintainability and create a more expressive internal architecture or object model to improve extensibility. Typically, refactoring applies a series of standardised basic micro-refactorings, each of which is (usually) a tiny change in a computer program's source code that either preserves the behaviour of the software, or at least does not modify its conformance to functional requirements.

Reference - https://en.wikipedia.org/wiki/Code_refactoring

In short - refactoring is cleaning up code wihtout changing its behaviour.

##### QI type information
Definitions:
factor - one of the elements contributing to a particular result or situation

factoring - the act or process of separating an equation, formula, cryptogram, etc., into its component parts.

Ref: http://dictionary.reference.com/browse/factoring

In software development, we break up a large problem into smaller ones - this can be called factoring (although it is not a commonly used term). After breaking up the problem and implimenting the solution, we might see ways of improving the solution without changing the functionality - and this is called re-factoring. 

## Practice continued ~45 min

The anagram challange - http://codekata.com/kata/kata06-anagrams/
It would be a good idea to copy the dictionary to your working folder: http://codekata.com/data/wordlist.txt




