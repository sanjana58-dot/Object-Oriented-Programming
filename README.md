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

