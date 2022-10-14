# Introduction to Object-Orinted Programming

## Classes and Objects in OOP

Coined by Alan Kay, **object-oriented programming**, also known as OOP or OO
programming, is a programming language paradigm. Recall that in an object-oriented
program, code should be structured as reusable components, some of which may have
common properties or behavior. Object-oriented programming can improve a programmer’s
ability to quickly prototype software, extend existing functionality, refactor and
fix code throughout the development process.

The basic idea of using an object-oriented language is to provide a programmer
with the means to create new native data types that can be used in the same way
as built-in types. Again, you can argue that structs can be used to create your
own custom data types. But structures are the traditional ways of representing
complex data types in the structured or functional programming paradigm.

In object-oriented programming, data types can contain not only data but also
functions that can work with this data. This data type is a **class**. A class
is an abstraction; it is a user-defined type. Classes are an important component
that makes object-oriented programming a powerful and flexible programming paradigm.

Class - Building
Data members - purpose, ddress, floors_number, wall_material
Methods - getAddress(), setSchedule()

A class declaration begins with the class keyword. The class declares data and
functions that operate on this data (perform their processing). The data that can
characterize an object of a class are called **attributes or data members**. Functions
that can perform any action on the data (properties) of a class are called **methods**.

Each variable of the type "class" is an **object** that is declared as `class_name`
`object_name;`. An object of a class is defined by a specific value of data (fields),
which is called the state of the object. Typically, properties and methods of classes
have access rights, the syntax of which depends on a programming language.

Since C doesn't support OOP, let us program our example in Java, Python, and JavaScript.

### Python

Python does not have access modifiers, but it emulates this behavior using names
that start with underscores:

_var is protected.
__var is private.

Class definitions also begin with the class keyword, followed by the class name
and a colon. The class name is set in PascalCase, i.e. each word starts with an
uppercase letter (as opposed to camelCase where the first word starts with a lowercase).
All the code following the colon constitutes the class body.

The properties that all objects of the Building class must have are defined in a
special method named __init__(). Every time a new Building is created, __init__()
sets the object's properties to values. That is, __init__() initializes every new
instance of the class (works like a constructor in Java). As in a constructor in
Java, the __init__() method can be passed any number of parameters, but the first
parameter is always an automatically created variable named self. The self variable
refers to the newly created instance of the class, due to which the __init__() method
can immediately define new attributes. Attributes created in __init__() are called
the attributes of the instance of the class, i.e. the object attributes. The value
of an object attribute depends on the object definition. All Building objects have
a purpose, an address, a number of floors, and specific wall material, but the values
for all attributes will differ depending on the Building object. Alternatively, you
can create class attributes that have the same value for all objects of the class.
You can define a class attribute by assigning a value to a variable name outside
of __init__(). For example, set wall materials as a class attribute.

Now let us program our example about the buildings. Use the IDLE program (Python
development environment), save the example program code to a file wherever it is
convenient for you, and run the file. In the example, we are using the f-string
formatting technique in Python: f-string is evaluated at runtime of the program.
We can display the object as well as show the output of the variables. It's swift
compared to other methods, for example, the str.format() method. The variables in
the curly { } braces are displayed in the output as a normal print statement.

```Python
class Building:
    wall_material = "brick"

    def __init__(self, purpose, address, floors_number):
        self.purpose = purpose
        self.address = address
        self.floors_number = floors_number

    def __str__(self):
        return f"The purpose is {self.purpose}. Address: {self.address}.
        Number of floors: {self.floors_number} and wall material is {self.wall_material}"

cafe = Building("organization of recreation", "London, Baker Street", 2)
print("Information about the cafe:")
print(cafe)
shop = Building("organization of shopping", "London, Crawford street", 1)
print("Information about the shop:")
print(shop)
```

The result:

Information about the cafe:
The purpose is organization of recreation. Address: London, Baker Street.
Number of floors: 2 and wall material is brick
Information about the shop:
The purpose is organization of shopping. Address: London, Crawford street.
Number of floors: 1 and wall material is brick

When you define a new object, Python itself passes it as a self parameter to
the __init__() method. We only need to be careful with the arguments.
After the objects are created, the recorded data is available as objects attributes.
The behavior of an object when interacting with the print() function can be changed
by defining a special __str__() method.

## Principles of OOP

Consider the main 4 principles of object-oriented programming – 4 main features
that together form an object-oriented programming paradigm. Understanding them
is the key to writing good programming code that can be easily maintained and
modified over time.

### Abstraction

Abstraction is a way of representing task elements from the real world as objects
in a program. Abstraction is always associated with the generalization of some
information about the properties of objects, so the main thing is to separate
meaningful information from insignificant in the context of the problem being
solved. Moreover, there can be several levels of abstraction. Abstraction and
encapsulation are closely related. Returning to the building example, we only
need to know the number of floors and the address. This is an abstraction. We
are shown only the simplest interface, and irrelevant information for this interface
is hidden. If you recall the history, then you will see that at first people
lived in caves, and then they built small settlements (the material was different,
the number of floors appeared over time, there was no address for a long time). Now
the variety of buildings and their design is amazing.

Now, with the help of abstraction, we can select general information in this hierarchy
of objects: the general abstract type of objects - Building, general characteristics
the year of its construction, the material of the walls, the number of floors.
This is how it looks in Java:

```Java
public abstract class AbstractBuilding {
    private int year;
    private int floors_number;
    private String wall_material;

    public AbstractBuilding (int year, int floors_number, String wall_material) {
        this.year = year;
        this.floors_number = floors_number;
        this.wall_material = wall_material;
    }
    public int getFloors_number() {
        return floors_number;
    }
}
```

Based on this abstract class, we will be able to create new types of buildings in
the program using other basic OOP principles. Simplification of the model (abstraction
from unnecessary details) in relation to a real subject allows you to make it formal,
so that during development, you can clearly identify all the dependencies and
operations on them in the created software system. This simplifies the study (analysis)
and development of models, as well as their implementation on a computer.

### Encapsulation

Encapsulation means restricting access to data and the ability to change it.
Encapsulation allows an object to define an interface with which to interact,
hiding implementation details, and thus, leaving the freedom to change the internal
structure. Think of some building. Most likely you thought of something that resembles
the picture below on the left, not on the right.

We keep all the inside (rough) trim of a building and communications for the interior
design. For example, we protect the electrical wiring from ordinary users (not
electricians) to prevent the possibility of a short circuit. The same can be applied
to the code, we do not want someone outside to interfere with the organization of
the code or important data, and we hide data members and some methods inside the
class, often using access modifiers; an open interface is provided to work with the
object. In the topic "Classes and Objects in OOP", we examined the Java program
example that illustrated what access modifiers there are and how the access to
private data is organized. The task of a programmer is to determine which attributes
and methods will be available for public access, and which are the internal
implementation of the object and should be inaccessible for changes.

### Inheritance

Inheritance allows you to create new classes based on the original class by adding
special data fields and additional methods to the existing classes. At the same time,
the properties and functionality of the parent class are borrowed by the new class
and can be reused. The original class is called a superclass or a parent, new classes
are called its subclasses or descendants. Let us take another look at the building
diagram above. You can see that it is a hierarchy in which the building located below
has all the features located up in the branch, plus its own features. For example,
a cottage refers to residential buildings and buildings in general. In this case,
we can talk about the inheritance of object properties. For example, in Java, creating
a new subclass looks as follows:

```Java
public abstract class ResidentialBuilding extends AbstractBuilding {

    private int parking_floors;

    public ResidentialBuilding(int year, int floors_number, String wall_material,
    int parking_floors) {
        super(year, floors_number, wall_material);
        this. parking_floors = parking_floors;
    }
@Override
    public int getFloors_number(){
        return (super.getFloors_number() + parking_floors);
   }
}
```

When creating a new subclass, you need to add quite a bit of new code, and we get
a new class with new functionality. Using the principle of OOP, inheritance allows
you to significantly reduce the amount of code, and therefore, to facilitate the
work of a programmer.

### Polymorphism

Polymorphism is an OOP concept, which means that objects that belong to the same
branch of the hierarchy and receive the same method can act in different ways.
Polymorphism is about the fact that it is possible to use descendant classes in
the context that was intended for a parent class, that is, there is a guarantee
of preserving the interface (the properties and functionality) of the parent class.
Polymorphism allows us to completely abstract in the client code from what kind of
implementation class we are using by referring to it through the use of the interface
defined in the parent class. This reduces the dependency of code modules. In this
case, the execution of each specific action will be determined by a subclass, if
necessary. Often, a method inherited by a subclass is directly used by it. However,
it is sometimes necessary for the operations in a subclass to be overridden according
to the semantic variations of the subclass. For example, in the previous Java block
of code, we overrode the int getFloors_number(); method, which in the base class
returns the number of floors, and in the subclass, it also adds the number of parking
floors.

With the right combination of polymorphism, encapsulation, and inheritance, a programmer
can create a programming environment that writes scalable (extensible) programs.
A well-designed class hierarchy will be the basis for reusable code. Encapsulation
allows you to use some blocks of code from project to project without destroying
it, which depends on the public interface of the classes. Polymorphism allows you
to create clear, highly modifiable, and readable code. Although the principles of
object-oriented programming have been discussed separately, they work together.

## Composition, Aggregation, and Association

Inheritance is described by an **"Is - a"** relationship. A cottage is a house,
a garage can be a hangar, but a house will not be a hangar, and you cannot use
inheritance here.

While inheritance is a great tool in the hands of any OO programmer, it is clearly
not enough for all types of problems. Firstly, not all relationships between classes
are defined by an "Is - a" relationship. And secondly, inheritance is the strongest
relationship between two classes that cannot be broken at runtime (this relationship
is static and, in strongly-typed languages, is determined at compile time).

### Association

Association is when one class includes another class as one of the fields. In other
words, association means that objects of two classes can refer to one another and
have some connection with each other. For example, a Buyer can issue an Invoice.
Accordingly, an association arises between a Customer and a Check or a Customer and
a Seller. The idea is quite simple - two objects can be related to each other,
and this must be described somehow. It can be described as a **“Has-a”** relationship
between classes.

In other words, an association is a relationship between classes whose objects
have an independent life cycle, and there is no ownership between the objects.

There are two local cases of association:

- **Composition** (has-a + whole-part + ownership): the life cycle of the child
  object coincides with the life cycle of the parent object. In other words, the
  whole explicitly controls the lifetime of its component part (the object (s) that
  make up or are contained by one object are also destroyed when that object is
  destroyed).

- **Aggregation** (has-a + whole-part): the life cycle of the child object does not
  depend on the life cycle of the parent and can be used by other objects. In other
  words, although the whole contains its component part, their lifetime is not
  connected (for example, the component part is passed through the parameters of
  a constructor).

We can say that an apartment has walls and some furniture. But if you think about
it, there is a significant difference between the objects of walls and furniture.
Walls (especially bearing ones) are built during the construction of an apartment.
Therefore, an object of the Wall class will be created and destroyed, respectively,
when an object of the Apartment class is created and destroyed. This is an example
of **composition**. Before getting into a certain apartment, furniture is produced
somewhere. We can buy different furniture, throw it away, transport it to different
apartments, and so on. That is, when creating the Apartment object, the Furniture
object is passed as a parameter of some method, and when the Apartment object is
destroyed, the Furniture object can be passed to another Apartment object. This is
an example of **aggregation**.

Python

```Python
class Wall:
    def __init__(self, material, height):
        self.material = material
        self.height = height


    def __str__(self):
        return "Material is '{}', height = {} ft.".format(self.material,
        self.height)

class Furniture:
    def __init__(self, name, cost):
        self.name = name
        self.cost = cost


    def __str__(self):
        return "name = '{}', cost = {}$".format(self.name, self.cost)

class Apartment:
    def __init__(self, street, apartment_no, material, height, furniture):
        self.street = street
        self.apartment_no = apartment_no
        self.walls = Wall(material, height)
        self.furniture = furniture

    def __str__(self):
        return "The address is '{} St' {}, walls {}, furniture=[\n{}]".format(
        self.street,
        self.apartment_no,
        self.walls,
        '\n'.join(str(element) for element in self.furniture),
        )

    def get_total_furniture_cost(self):
        total_cost = 0
        for element in self.furniture:
            total_cost += element.cost
        return total_cost

if __name__ == "__main__":
    furniture = [Furniture("bed", 150), Furniture("cupboard", 250),
    Furniture("table", 35), Furniture("armchair", 80)]
    flat1 = Apartment("Bronco", 3050, "brick", 23, furniture)
    print("Information about the first apartment:", flat1)
    print("Total furniture cost is {}$".format( flat1.get_total_furniture_cost()))
```

The result:

Information about the first apartment: The address is 'Bronco St' 3050, walls Material
is 'brick', height = 23 ft., furniture=[
name = 'bed', cost = 150$
name = 'cupboard', cost = 250$
name = 'table', cost = 35$
name = 'armchair', cost = 80$]
Total furniture cost is 515$

