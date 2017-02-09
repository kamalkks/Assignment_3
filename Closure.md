Lexical Scoping

function first()
{
  var goal="Hello"      //goal is local variable to first() function that can't be accessed from outside first(), but it can be used by second() function
  
  function second()     //inner function to first()
  {
    console.log(goal);
  }
  second()               // call to inner function, within the parent function
   
}
first()                //call to first() function


OUTPUT    Hello


 CLOSURE
 
 A closure is combination of a function and the lexical environment within which that function is declared. This lexical environment consists of local variables that were in scope at the time the closure was created.
         
         
function first()
{
    var goal="Hello"
    
    function second()
    {
        console.log(goal);
    }
    
    
    return second
}
var third= first()      // third has reference to the instance of the function second() and is a closure
console.log(third)       //Function:second
third();                //Hello

OUTPUT
Function:second
Hello
In the above example,second() the inner function is returned from the outer function before being executed.The third is a reference to the instance of the function second created when function first() runs.
The instance of second maintains a reference to its lexical environment(that has variables names with values that are in its scope).When third is invoked, variable goal becomes accessible to it and hence gives "Hello"
as output.

References:
www.w3schools.com
Eloquent Javascript
Closures in javascript by Kudvenkat(video)