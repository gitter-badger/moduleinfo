# moduleinfo

[![Join the chat at https://gitter.im/Ekaterina96/moduleinfo](https://badges.gitter.im/Ekaterina96/moduleinfo.svg)](https://gitter.im/Ekaterina96/moduleinfo?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
Creating a information list
1. A constructor, which generates a Staff instance with initial details of the staff member passed
as arguments (forename, surname, ID, address)
2. A method that takes a single Module instance as an argument, and appends this to the list of
modules that this Staff member lectures on (maintained by the Staff instance).
3. A method that takes a single Module instance as an argument, and removes this module from the list of modules that this Staff member lectures on. If the staff member has not recorded that it lecturers on the module provided, it should return false. Otherwise it should return true when it has successfully removed the module.
4. A method that takes a single Module instance as an argument, and appends this to the list of modules that this Staff member coordinates however it should ensure that it does not generate duplicates, returning false if this is attempted (returning true otherwise).
5. A method that takes a single Module instance as an argument, and removes this from the list of modules that this Staff member coordinates. If the staff member has not recorded that it coordinates the Module provided as an argument, it should return false. Otherwise it should return true when it has successfully removed the Module.
6. A method that returns the total number of modules a lecturer lectures on.
7. A method that returns the total number of modules a lecturer coordinates.
8. An equals method, with the signature: public boolean equals(Object obj). This must return true if the staff details match those of the Object argument, otherwise false.




/**
 * 
 * 
 * @author (Kate Sukhova) 
 * @version (a version number or a date)
 */

 public class Staff  { 
 
  private Object[] list;
  
  String forename = null;// instance variables of staff class (foreanme, surname, Id, adress)
  String surname = null;
  int userID;
  String address = null;

public Staff(){
      this.list = new Object[0];
    }
      
 
  public Staff(String forename, String surname, int userID, String address) {
    this.forename = forename;
    this.surname = surname;
    this.userID = userID;
    this.address = address;
    }
  
public void add(Object module) { 
    Object[] detail = new Object[this.list.length+1];  //adding a module to the staff member
    for (int i=0; i<this.list.length; i++){
        detail[i] = this.list[i];
        detail[this.list.length] = module;
        this.list = detail;
    }

}

public boolean remove(Object module){              //removing the module that the staff member lectures on
    int index  = -1;                          // if the staff member not supposed to lectures on the provided module
    for(int i=0; i<this.list.length; i++){    //  it should return false
        if(this.list[i].equals(module)){           // otherwise return true if the module removed successfully 
            index = i;
            break;
        }
    }
    return this.remove(index);
}

 

class staffCoordinates{
  private Object[] coordinates;

public staffCoordinates(){
   this.coordinates = new Object[0];
        }

    
public boolean add(Object module){
        Object[] mcoord = new Object[this.coordinates.length+1];  //adding a module to the staff member, that he coordinates
    for (int i=0; i<this.coordinates.length; i++){                // if attempted to add similar module return false
        mcoord[i] = this.coordinates[i];                          // otherwise return true
        mcoord[this.coordinates.length] = module;
        this.coordinates = mcoord;
    }
    if (this.coordinates[i].equals(module)){
        i = index;
        break; 
    }
}
}
}

    
