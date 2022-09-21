### Questions From Russel 9/21

#### Basically you have 1 class (in your .h file). Inside the class you have member functions. You define those member functions in another cpp.

>You can also use .h and .hpp files to declare things, but keeping a header and source implementation separate is usually best, separating out public/private member data.

#### Can those member functions be used inside of each other? Obviously they can, they are apart of the same class.

>You can use any upcasted class member functions if they are public, and some instances private. You cannot be in a grandparent class and use a grandchild class, only upcast or static casting of instances is usually the case. You can also use friend or helper functions within a cpp, you just don’t include class name::function, just do a normal function. But these are local for the class/any instances of derived class objects.

#### But it would be more effective to have one function that does logic to make up for not creating 4 sub functions.

>It is usually best to keep things as straight forward and encapsulated as possible, unless looking at complexity or level. Most cases it is best to take any logic done more than once, and create a helper function for that functionality.

#### So let’s say a move function for example. Instead of making 4 individual functions for moving N,S,E,W, you have only one Move() function that does logic to preform N,S,E,W

>Yeah, for this you could prompt user for a string input NE/SW etc, and then check string[0] for N or S and do - or + to x, and string[1] for E or W and do - or + to y, all in 1 move function, which then returns updated position, and applies it to PlaneObject.SetPos(new pos). Sometimes repeated logic is to be avoided so maybe doing 1 function in the cpp not as a class member function for Vertical movements, and 1 for Horizontal movements just to avoid repeated logic would help. Also worth considering setting S and W to be negatives so you can make the arithmetic easier.
