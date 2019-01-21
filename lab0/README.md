# Lab 0 - Booking System for a Movie Theater

## Important Dates

* Release Date: January 23, 2019


## Objectives

For this lab, you will:
* Get you started with the programs and systems in the lab
* Gain practice with the syntax of Java
* Gain exposure to how to design a Java program with multiple classes
* Gain exposure to the basic principles of object-oriented programming


## Set-up

Even though many of you have used Eclipse before, please follow the introductory steps below carefully.
Correcting configuration errors is not impossible, but it is time-consuming and distracting. Although this is not a graded lab, it is a good idea to practice turning in your code so that you will know how to do it with the regular labs and projects.

### What we will need

You should all have your accounts and passwords for the CS lab system. Log into one of the computers
in the classroom. Among the icons in the dock at the bottom of the screen are three that will be
important for the class: Terminal, Eclipse, and Safari or Chrome, depending on your browser preferences. We will use all three today.

Open a terminal window and type the following commands. They will create a (private) folder for this
class and a workspace within that folder.

``` 
cd ~/Documents
mkdir cs062
chmod 700 cs062
cd cs062
mkdir workspace
```

### Explanation

The command `mkdir` makes a directory, and `cd` changes to that directory. The `chmod`
command makes the directory private, so that only you can see its contents. A few other commands
for your information: `ls` lists the contents of the current directory, `cd` changes the directory to one directory lower, `rm` removes a specified file and you can type `man <command>` for any command and it
will give you more information (short for "manual").

Note that much of this could have been accomplished using the mouse and interacting with menus in Finder. However, one goal of this class is to get you used to using the terminal to accomplish tasks. All of the
commands you are typing into the terminal window are UNIX commands, as the Macintosh operating system is a variant of UNIX (BSD UNIX, to be exact). These same commands will generally work with other flavors of UNIX, like LINUX. However, Windows computers use a different operating system, with slightly different commands to accomplish the same tasks.

In this optional lab, you will create a program that models a booking system for a movie theater. As we saw in class, Java follows the object-oriented programming (OOP) paradigm. Most languages that follow the OOP are built around the idea of *objects* and *classes*. 

*Classes* allow us to organize concepts that share a *state* (fields or variables) and *behavior* (methods or functions). *Objects* are instances of classes, therefore classes are often considered as blue-prints of objects.

## STOP

Once you have reached this point, raise your hand to let the instructor know. We will spend some time working on a creating a class to represent the animal kingdom. If we have time, we will proceeed with the remaining part of the lab that you can finish on your own.


## Classes

Now let's go back to the movie theater booking system. There are many ways to model this problem, but we have chosen a design that uses the following classes: `Movie`, `Screen`, `MovieTheater`, `User`, `Ticket`, and `TicketingSystem`. For all classes, create the appropriate constructors, getters and setters, and `toString()` methods.


### `Movie`

Create a class `Movie` that has the following fields: a title (`String`). age limit (`int`). 

### `Screen`

Create a class that will correspond to a screen (room) in our movie theater. Potential fields to consider: id (`int`), an array of 10 seats (of type boolean, by default false as none has been booked, all rooms have 10 seats), price for the movie that is screened (`double`), , a movie (`Movie` object, we will assume that a screen projects only one movie), and a showtime (`int`, let's assume that there will only be one screening of the movie and it has to start on the top of the hour e.g., 14 for 2pm). You should also create a `pickNextAvailableSeat()` method that will return `boolean` (true if there was an available seat, false if all 10 seats are taken).

### `MovieTheater`

Create a class that will represent our movie theater. It should have a name, an array of 10 screens and an array of 5 movies. 

### `User`

Create a class that represents a user that wants to buy a ticket. Potential fields are: `numberOfUsers` (think static and start at 0), userID (`long`, which you can set to the `numberOfUsers`), age (`int`). It should also have a `buyTicket(Movie movie, MovieTheater movieTheater, int time)` method that returns a `Ticket` based on the screening times that the movieTheater shows that particular movie. Make sure to check that the user can watch this movie based on their age.

### `Ticket`

This class will represent a ticket that will link a user with a specific screening of a movie. It might be a good idea to give it an id (`long`) which will be set through a static counter (`numberOfTickets`) and connect it to a user object and a screen object. You can also have a boolean that corresponds to whether the ticket was issued successfully, which could translate to different versions of the `toString()`.


### `TicketingSystem`
This class will be responsible for the operation of our movie theater.
Start by creating an array of five movies (google a local theater and pick five movies. Choose at least one that is PG-13). Now create an array of 10 screens (make sure to use the array of movies you just created). It's time to create a movie theater with these movies and screens. Once you do this, experiment with creating users of different ages and have them try to buy tickets. How can you check whether you code is correct?

