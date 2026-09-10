# Object-Oriented-Programming
Notes for placements
-----------CLASS-------------
class is a user defined data type that encapsulates  data members and member functions in a single logical entity and serves as a blueprint for creating objects.
-----------Object------------
An object is a runtime instance of a class that has it's own state and can perform behavior defined by the class.
# EXAMPLE
class Student{                 ----------------------------------------|
public:                                                                |  
  string name;                                                         | 
  int rollnumber;
  float marks;
                                                       NOW WE CAN CREATE OBJECT ---------   Student S1;  
  void study(){                                                                             s1.name="SANJANA";
   cout<<"student is studying"<<endl;                                                       s1.rollnumber=102303205
  }                                                                                         s1.marks=89;
  void Displaydetails(){                                                                     s1.study(); s1.Displaydetails();
    cout<<name<<" "<<rollnumber<<" "<<marks;                            | 
  }                                                                     |
}                            -------------------------------------------|

                                FINAL DEFINITION 
  A class is a user-defined  blueprint that contains data and behavior of an entity . while an object is a runtime instance of a class with it's own state.
  <img width="404" height="206" alt="image" src="https://github.com/user-attachments/assets/39117c10-3c3d-47b1-94c8-a1512b3defa2" />

  --------------DATA MEMBERS & MEMBER FUNCTIONS------------------
  data members are the variables belongs to a class and member function is a function belongs to a class.




  ------------------------------------ACCESS SPECIFIERS--------------------------------
                   PUBLIC  |  PRIVATE  | PROTECTED

  everything under public specifier is accessible from outside the class 
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


  everything under protected specifier is accessible inside the class itself and inside it's child /derived class
  BUT generally not directly through the outside object
  class student{
  protected:
   int value ;
  }

  class child:class student{
  public:
   void show(){
     cout<<value<<endl;           <<---THIS IS VALID
   }
 }
  <img width="553" height="264" alt="image" src="https://github.com/user-attachments/assets/a27e3935-c43c-4f11-b172-b918e1582c48" />

