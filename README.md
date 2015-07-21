# java-minimalist-convention

By default:

 1. Do not use primitives, use wrapper classes 
    * Forget about equals, and == problem. Equals will be used everywhere.
    * Forget about 0 and null problem for primitives.
    * Everything is an object. Right?
    * Scala does not have primitives.
    
 2. Do not use checked exceptions, use objects and Optional class
    * Less noisy to read
    * Do not violate OCP
    * In java 8 you cannot map, filter etc on function with checked exception, this leads to rethrowing, and noisy code
    * C# (and any other language) does not have checked excptions
    * Check Effective Java Item 59: Avoid unnecessary use of checked exceptions 
    
 3. If you want to extend a class..
    * Try to decouple class, use composition over inheritance
    * Use Interface (starting from java 8, they are awesome)
    * If you cannot two mention options, then use abstract class, and only then ordinary class (probably this is poor design)
    * Learn Strategy pattern, and maybe factory
    * Go(golang) does not have classes, only interfaces
    
 4. Do not use arrays, use collections
    * In long term, you will reach the point when you will convert array to list
    * There is no clause when to use array, except optimization
    * Array is primitive (watch point 1)
    * Array is not used in many higher order languages
    
 5. Do not use switch construct
    * Switch is big and ugly
    * Remember when you forgot to add break? Do not write code which leads to errors
    * If construct offers totaly same functionality
    * Use construct
      * public Animal returnWhithoutSwitch(String animalString){
      *   if(someString.equals("wolf")) return new Wolf();
      *   if(someString.equals("rabbit")) return new Rabbit();
      *   if(someString.equals("fox")) return new Fox();
      * }
      
 6. Do not use for and foreach construct
    * Use collections streams, learn how they work and how do the labmdas work.
    
 7. Readability over OOP sophistication and code size.
    * Work towards DSL, code you write must be human readable and intuitive
    * If you want to choose some design pattern over readability, then you are probably doing a mistake
    * If you want to insert a hack or make variable name shorter, which makes code unreadable, then you are probably doing a mistake
    * If you have to choose between very small hack and introducing desing pattern (or chain of desing patterns), 
      then personally, I would choose hack, because overengineered solution is harder to read(probably you will introduce more classes). IMHO
    * If desing pattern eases the readability of complex class, then introduce it.  
    * Learn SOLID and desing pattens. Readability does not mean that you should not be an expert in OOD.
    
 8. Do not use interfaces for testing purposes (only for polymorphic calls)
    * This bloats the code.
    * You have mockito for that
    * For example, extracting DAO interface only for testing is plain stupid.
  
 9. Testing.
    * Tests should be fast.
    * As less mocking as possible
    * Mocking is a smell of bad design.
    * Unit tests for business logic
    * Integration tests to speak with external stuff (database)
   
Not sure (may skip):
  
 1. Do not use protected keyword (same for default accessability)
    * Never had a situation where I have need it.
    * Most of the languages does not have such accessability modifiers
    * Internal and external presentation, why should I need some messy hacks? Class is a unit of sth, it is a black box, nothing more.
    
    
(they bloat the code, make it hard to read + usually you will end with flow based on exceptions)
