**UML**

*Class* is formed by class name, attribute, operation and relationships. object is going to be an instance and
we try to classify all these instances together as a single class. A class ia a "factory" for creating objects.
A good class should capture one and only one abstraction. 

 - attribute: name(unique within a class); type(the domain values; string, integer, money, etc.); visibility(+public,-private, #protected)
 
  - operation (op. instance is a method): signature(name(parameters): result-type); visibility(+public,-private, #protected); visibility(+public,-private, #protected)
  
 *Association*(classifier) describe a collection of links(single istance of ass) between classes. Associations can be
 bidirectional. Two different classes can be several associations, for example Person and University can have two 
 associations Attended and WorksFor. here all type of associations
![association_degree.png](images%2Fassociation_degree.png)
Within an association, you also need to specify what we call multiplicities. Multiplicity specify a restriction
on the number ~~of~~ optics in a class that may be related to an optic in another class

Bank (1..1) ----IsWith---- (0..*) Account

Bank can have many accounts (from 0 to infinity)
an account can be associated with only one bank (from 1 to 1)
the first term has to be 0 or 1..1 because before the UML we have to relax the requirement.

in unary association we need to define the role, in our example we need to add on worker on one 
hand of the link and boss on the other hand

![association_aggregation.png](images%2Fassociation_aggregation.png)
![exampleUML.png](images%2FexampleUML.png)


*associations class*
![associations_class.png](images%2Fassociations_class.png)

*generalization*
An attribute of enumeration type that indicates which property of a
class is used to create a generalization relationship
![generalization.png](images%2Fgeneralization.png)

- An abstract class is used, for modeling purposes, as a container
for definitions, but no instances of the class are of interest. 
- overlapping - A superclass object can be a
member of more than one subclass.
- disjoint A superclass object is a member of at
  most one subclass.
- complete All superclass objects must be
  members of some subclass.
- incomplete Some superclass object is not a
  member of any subclass.

*constraint* is an assertion about properties of model
elements that must be satisfied by the system. {balance > 1000}
![constraint.png](images%2Fconstraint.png)
*summary*
Relationships
- association describes links among object instances (only relationship
that relates object instances) (Linea continua)
- generalization relates a more general class (superclass) to a more
specific kind of the general class (subclass) (Linea con triangolo alla fine)
- dependency relates classes whose behaviour or implementation
affect other classes (Linea trattegiata)
  - flow relates two versions of an object at successive times
  - usage shows that one class requires another class for its correct functioning
- realization relates a specification to its implementation (e.g., an
  interface to the classes that implement it(Linea trattegiata triangolo alla fine)

*common model*
![static_model.png](images%2Fstatic_model.png)
![dynamic_model.png](images%2Fdynamic_model.png)

**Steps to define model domain**
- Captures the most important classes and their associations.
  - classes appear as nouns/noun phrases
  - associations appear as verbs/verb phrases
  - Attributes usually correspond to nouns followed by possessive
    phrases (e.g., password of student; student's address)
  - Adjectives usually represent specific enumerated values
    (e.g., Fall term; PhD degree.)
- Evaluating classes
  - Are any classes irrelevant to the domain model? → eliminate
    ☞A class should represent persistent data, not transient data.
  - Are any classes vague (ill-defined)? → make specific or eliminate
    ☞A class should be specific and well-defined.
  - Are any classes redundant? → keep most descriptive
  - Should any classes really be attributes? → consider application requirements
    ☞Is the concept dependent or independent?
  - Do any class names describe a role?
    ☞Roles also appear as nouns!
  - Do any classes describe an operation/action? → eliminate
  - Do any classes describe implementation constructs? → eliminate
- Evaluating associations
  - Are any associations irrelevant to the domain model? → eliminate
  - Do any associations describe an operation? → eliminate
    ☞ Should describe a structural property, not a transient event.
  - Can ternary associations be decomposed into binary associations?
   decompose
    ☞Should try to keep the model as simple as possible.
  - Are any associations derived associations? → eliminate
    ☞Introduces redundancy into the mode
  - Do any associations describe implementation constructs? → eliminate
- EVALUATING ATTRIBUTES
  - Are attributes closely related to the class they are in?
  ☞ A class should be simple and coherent.
  - Should any attributes really be classes?
  ☞ The concept should be dependent on the class.
  - Should any attributes be in an association class?
  ☞ Does the attribute depend on the existence of an association?
  - Have object identifiers been included as attributes?
  ☞ Object identifiers should not be included in the domain model!