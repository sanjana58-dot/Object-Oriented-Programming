# Object-Oriented-Programming
Notes for placements<br>
-----------CLASS-------------<br>
class is a user defined data type that encapsulates  data members and member functions in a single logical entity and serves as a blueprint for creating objects.<br>
-----------Object------------<br>
An object is a runtime instance of a class that has it's own state and can perform behavior defined by the class.<br>
# EXAMPLE<br>
class Student{                 
public:                                                                
  string name;                                                         
  int rollnumber;
  float marks;
                                                         
  void study(){                                                                            
   cout<<"student is studying"<<endl;                                                      
  }                                                                                        
  void Displaydetails(){                                                                     
    cout<<name<<" "<<rollnumber<<" "<<marks;                            
  }                                                                     
}                            
<br>
---------------------------- NOW WE CAN CREATE OBJECT --------------------<br>
 Student S1; <br>
 s1.name="SANJANA";<br>
 s1.rollnumber=102303205  <br>                            
 s1.marks=89;    <br>                          
 s1.study(); s1.Displaydetails(); <br>     

 
   ================================================== FINAL DEFINITION ============================================ <br>
  A class is a user-defined  blueprint that contains data and behavior of an entity . while an object is a runtime instance of a class with it's own state.<br>
  <img width="404" height="206" alt="image" src="https://github.com/user-attachments/assets/39117c10-3c3d-47b1-94c8-a1512b3defa2" />

  --------------DATA MEMBERS & MEMBER FUNCTIONS------------------<br>
  data members are the variables belongs to a class and member function is a function belongs to a class.<br>




  ------------------------------------ACCESS SPECIFIERS--------------------------------<br>
                   PUBLIC  |  PRIVATE  | PROTECTED<br>

  everything under public specifier is accessible from outside the class <br>
  class teacher{
  public:
    string name;
  }

  THEN 
  teacher t1;
  t1.name="mandeep kaur";     THIS IS VALID

  everything under private specifier is accessible only inside the class itself

  class teacher{
  private:
   float salary;
  }

  THEN 
  teacher t1;
  t1.salary=100000 //ERROR 

<br>
  everything under protected specifier is accessible inside the class itself and inside it's child /derived class
  BUT generally not directly through the outside object<br>
  class student{
  protected:
   int value ;
  }

  class child:class student{
  public:
   void show(){
     cout<<value<<endl;           <<---THIS IS VALID
   }
 }<br>
  <img width="553" height="264" alt="image" src="https://github.com/user-attachments/assets/a27e3935-c43c-4f11-b172-b918e1582c48" />


  -------------------------CONSTRUCTOR-----------------------------<br>
  a constructor is a special member function that is automatically invoked when an object is created and is primarily used to initialize the object's state.<br>

  <img width="496" height="295" alt="image" src="https://github.com/user-attachments/assets/d1fc8ec8-3d93-412c-9001-5e7140fe58dd" />


  <img width="506" height="381" alt="image" src="https://github.com/user-attachments/assets/0faad21f-2d92-4e3b-907a-6a93b7831757" />


  <img width="554" height="412" alt="image" src="https://github.com/user-attachments/assets/e28682ad-09b5-4d37-99f6-c077284cdc7a" />


  -------------------------------TYPES OF CONSTRUCTORS-----------------------------------------<br>

  # DEFAULT CONSTRUCTOR <br>
  # PARAMETERISED CONSTRUCTOR<br>
  # COPY CONSTRUCTOR<br>

  #include <iostream>

class Demo {
    int data;

public:
    Demo() {
        data = 0;
    }

    Demo(int val) {
        data = val;
    }

    Demo(const Demo& other) {
        data = other.data;
    }

    void display() {
        std::cout << data << std::endl;
    }
};

int main() {
    Demo d1;
    Demo d2(50);
    Demo d3(d2);

    d1.display();
    d2.display();
    d3.display();

    return 0;
}

default constructor initializes the object with default value <br>
parameterized constructor initializes the object with the parameters given to it<br>
copy constructor copy value of other object to the current object<br>


-----------------------------------------CONSTRUCTOR OVERLOADING-------------------------------------------<br>
constructor overloading means defining multiple constructors in the same class with the same names , but with different parameters list (different number of arguments, different types of arguments, different order )<br>

#include <iostream>

class Box {
    int length;
    int breadth;

public:
    Box() {
        length = 0;
        breadth = 0;
    }

    Box(int side) {
        length = side;
        breadth = side;
    }

    Box(int l, int b) {
        length = l;
        breadth = b;
    }

    void show() {
        std::cout << length << " " << breadth << std::endl;
    }
};

int main() {
    Box b1;
    Box b2(5);
    Box b3(4, 8);

    b1.show();
    b2.show();
    b3.show();

    return 0;
}

<br>
===================================LETS SEE ANOTHER EXAMPLE===============================================================<br>
#include<iostream>
#include<string>
using namespace std;

class student{
 int roll;
 string name;
 public:
   student(int r){
     roll=r;
     name="unknown";
   }
   student(string s){
     roll=0;
     name=s;
   }
   student(int r,string s){
     roll=r;
     name=s;
   }
   student(string s,int r){
      name =s;
      roll = r;
   }
   void show(){
   cout<<"roll "<<roll<<" "<<"name "<<name<<endl;
   }
};

int main(){
  student s1(24);
  student s2("Charlie");
  student s3(22,"Alice");
  student s4("Bob",24);
  s1.show();
  s1.show();
  s3.show();
  s4.show();
  return 0;
}<br>

HENCE A CLASS CAN HAVE MULTIPLE CONSTRUCTORS WITH DIFFERENT PARAMETERS THAT IS CALLED CONSTRUCTOR OVERLOADING<br>

CONSTRUCTOR NAME SHOULD BE SAME AS THE CLASS NAME <br>
CONSTRUCTOR HAS NO RETURN TYPE<br>
<img width="344" height="212" alt="image" src="https://github.com/user-attachments/assets/d9cd4609-2a85-4e3e-9abf-05edf9f77215" />


=================================DESTRUCTOR======================================
a destructor is a special member function that is automatically invoked when an object is destroyed and is used primarily for resource cleanup.<br>
class student{
int marks;
public:
 student(){
 marks =0;
 cout<<"constructor is called"<<endl;
 }
 ~student(){
 cout<<"destructor is called"<<endl;
 }
};

<br>
class Student {

public:

    Student() {
        cout << "Created\n";
    }

    ~Student() {
        cout << "Destroyed\n";
    }
};<br>

<img width="470" height="268" alt="image" src="https://github.com/user-attachments/assets/2c2517ec-877f-4c64-bd47-2f80e28b9f04" />


========================THIS POINTER==========================
if name of data member of object and name parameter of member function is same then this pointer points to data member of current object <br>

class Student {

private:
    int age;

public:

    void setAge(int age) {
        this->age = age;
    }
};
<br>
<img width="200" height="385" alt="image" src="https://github.com/user-attachments/assets/d309c795-c1dd-46ed-870d-ef9f16275a99" />

<br>
<BR>



================================IMPORTANT=======================================================
<BR>
-----------------------------------ENCAPSULATION-------------------------------------------------
<BR>
encapsulation is the process of bundling the variables(data members) and functions(member functions,methods) that operates on the data of a single unit(a class). while restricting the direct access to the internal state from the outside of the class.

Encapsulation ≠ simply making variables private.
<br>
Private members are one mechanism used to achieve encapsulation.<br>
<img width="242" height="154" alt="image" src="https://github.com/user-attachments/assets/c8728b23-0358-41b9-aea2-976d3fdd44d8" />
#include <iostream>

class BankAccount {
private:
    double balance; // Hidden from direct external access

public:
    BankAccount(double initial_balance) {
        if (initial_balance >= 0) {
            balance = initial_balance;
        } else {
            balance = 0;
        }
    }

    // Controlled setter with validation
    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    // Controlled getter
    double getBalance() const {
        return balance;
    }
};

int main() {
    BankAccount account(100.0);

    // account.balance = -500.0; // ERROR: balance is private

    account.deposit(50.0);
    std::cout << account.getBalance() << std::endl; // Prints: 150

    return 0;
}
<br>
<br>
-----------------------------------------------------ABSTRACTION---------------------------------------------------------------------
<br>
Abstraction is displaying essential features to the outside world while hiding the complex background details and internal implementation logic.
<br>
ENCASULATION IS HIDING DATA OR METHODS FOR SAFETY PURPOSE WHEREAS ABSTRACTION IS HIDING COMPLEX IMPLEMENTAION OR INTERNAL LOGIC FROM OUSIDE WORLD 
<BR>
While encapsulation focuses on hiding data for security and containment ("how data is kept safe"), abstraction focuses on hiding complexity behind a clean interface ("what the user can do, not how it's done"). <BR>

#include<iostream>

class car{
public:
  virtual void startengine() = 0; //virtual function
  virtual ~car() {}
  
};

class sedan:class car{
 public:
  void startengine() override{
     injectfuel();
     ignitespark();
     cout<<"sedan engine starts smoothly\n";
  }
  private:
   // Complex background mechanics hidden from the caller
    void injectFuel() {}
    void igniteSpark() {}
};

int main(){
  car mycar* = new sedan();

  mycar->startengine();
  // The driver only needs to know startEngine(), not fuel injection mechanics
  delete mycar;
  return0;
}
<br>

<img width="548" height="197" alt="image" src="https://github.com/user-attachments/assets/fdf40cdc-eb3b-4fc6-906d-3063f751d2fa" />

<br>

<img width="587" height="319" alt="image" src="https://github.com/user-attachments/assets/edf1996b-06e9-410e-914b-47078050453b" />

<img width="577" height="112" alt="image" src="https://github.com/user-attachments/assets/2a025f73-bcb4-4951-b8c7-b8467e38852f" />


<img width="628" height="292" alt="image" src="https://github.com/user-attachments/assets/6719cbcb-7fb8-4c7c-b110-9399c2c387f6" />

<img width="686" height="359" alt="image" src="https://github.com/user-attachments/assets/5a8413da-775c-4bc1-88aa-13b395ccd17b" />
<BR>
SO,<BR>
ENCAPSULATION IS HOW TO PROTECT <BR>
ABSTRACTION IS WHAT TO EXPOSE<BR>
<BR>
                OOP
                 │
        ┌────────┴────────┐
        ↓                 ↓
      Class             Object
        │
        ├── Data Members
        ├── Member Functions
        │
        ├── Access Specifiers
        │       ├── public
        │       ├── private
        │       └── protected
        │
        ├── Constructor
        ├── Destructor
        ├── this pointer
        │
        ├── Encapsulation
        │
        └── Abstraction

<br>

<br>

==================================================INHERITANCE=============================================<BR>
inheritance is an oop mechanism in which a new class (child/derived)  acquires the properties and behavior of parent/existing class <BR>
A CHILD CLASS REUSES AND EXTENDS THE PARENT CLASS.<BR>
#include <iostream>
using namespace std;

class Animal {
public:
    void eat() {
        cout << "Animal is eating" << endl;
    }
};

class Dog : public Animal {
public:
    void bark() {
        cout << "Dog is barking" << endl;
    }
};
<BR>
NOW, <BR>
int main() {

    Dog d;

    d.eat();
    d.bark();

    return 0;
}
<BR>
<img width="551" height="317" alt="image" src="https://github.com/user-attachments/assets/fe1a1c70-a916-4df7-8f73-9cfef522d191" />

<BR>
<img width="555" height="365" alt="image" src="https://github.com/user-attachments/assets/a670498b-384f-44b7-919c-a7aacd31b263" />

<br>
<img width="578" height="147" alt="image" src="https://github.com/user-attachments/assets/14610e2d-e3d6-4294-8cae-aba00d12301d" />

<br>
<img width="560" height="311" alt="image" src="https://github.com/user-attachments/assets/1218cb3b-f021-4d84-a530-2d06704ba89c" />

<br>
<img width="565" height="93" alt="image" src="https://github.com/user-attachments/assets/94ffeef2-0629-4e10-bc0c-8cae9bc960c6" />


<br>
<img width="506" height="400" alt="image" src="https://github.com/user-attachments/assets/4fe67029-da27-4d52-8e54-5a78d60625ea" />
<br>
<img width="505" height="413" alt="image" src="https://github.com/user-attachments/assets/df61135c-572f-43be-82df-c304327d2770" />

<br>
<img width="485" height="408" alt="image" src="https://github.com/user-attachments/assets/d138a74b-41a5-41fd-b56e-b35078b0a57b" />
<br>
<br>
=============================TYPES OF INHERITANCE=============================================
1) Single<br>
2) Multilevel<br>
3) Hierarchical<br>
4) Multiple <br>
5) Hybrid<br>
<br>
--------------------------SINGLE INHERITANCE---------------------------------------------------<br>
one parent one child <br>
class Animal {
};

class Dog : public Animal {
};
<br>
<br>
------------------------MULTILEVEL INHERITANCE-----------------------------------------------<br>
Inheritance happens in a chain.<br>
class Animal {
};

class Mammal : public Animal {
};

class Dog : public Mammal {
};
<br>
Dog
 ↑
Mammal
 ↑
Animal

<br>
dog indirectly derives from Animal
<br>
<br>
-----------------------HIERRARCHICAL INHERITANCE-------------------------------------------<br>
One parent → multiple children.<br>
          Animal
          /    \
        Dog    Cat

class Animal {
};

class Dog : public Animal {
};

class Cat : public Animal {
};

<br>
Both Dog and Cat inherit from Animal.
<br>
<br>
--------------------------------MULTIPLE INHERITANCE-----------------------------------------<BR>
One child → multiple parents.
    Father       Mother
       \           /
        \         /
          Child
class Father {
public:
    void fatherFeature() {
        cout << "Father";
    }
};

class Mother {
public:
    void motherFeature() {
        cout << "Mother";
    }
};

class Child : public Father, public Mother {
};
<BR>
<img width="523" height="155" alt="image" src="https://github.com/user-attachments/assets/9dcbb8de-3f99-423b-b7d9-b8573dddb107" />
<BR>
<BR>
--------------------------------HYBRID INHERITANCE----------------------------------------
Combination of multiple types 
<img width="557" height="256" alt="image" src="https://github.com/user-attachments/assets/d439adbd-bddf-4a21-8154-5302d194a6f5" />
<br>
<img width="557" height="373" alt="image" src="https://github.com/user-attachments/assets/63a18e14-f315-44bb-b2d3-d2fc0da4305c" />
<br>
<img width="380" height="134" alt="image" src="https://github.com/user-attachments/assets/7083aa33-7ed2-40db-88f2-2db55ff8ce8c" />
<br>
<img width="387" height="389" alt="image" src="https://github.com/user-attachments/assets/0b843e17-12cd-4edd-a61b-81f6b1575ed4" />
<br>
<img width="573" height="376" alt="image" src="https://github.com/user-attachments/assets/e7123949-7c1c-40dc-9d7a-f1897af3b8a9" />
<br>
<img width="590" height="329" alt="image" src="https://github.com/user-attachments/assets/92779bc7-44ce-42ce-ac25-0f15c368a666" />
<br>
Child object creation
        ↓
Parent constructor
        ↓
Child constructor
<br>
<img width="618" height="379" alt="image" src="https://github.com/user-attachments/assets/c9cecc34-c066-4c6f-bf4a-79eef87f576c" />
<br>

