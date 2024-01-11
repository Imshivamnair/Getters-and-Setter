# Getters-and-Setter

In JavaScript, getters and setters are special methods that allow you to control access to the properties of an object. They provide a way to encapsulate the internal state of an object and enforce certain behavior when getting or setting values. Here's an example:

// Using a constructor function to create an object
function Person(firstName, lastName) {
  // Private variables
  let _firstName = firstName;
  let _lastName = lastName;

  // Getter for the first name
  this.getFirstName = function () {
    return _firstName;
  };

  // Setter for the first name
  this.setFirstName = function (newFirstName) {
    if (typeof newFirstName === 'string') {
      _firstName = newFirstName;
    } else {
      console.error('Invalid input. Please provide a string for the first name.');
    }
  };

  // Getter for the last name
  this.getLastName = function () {
    return _lastName;
  };

  // Setter for the last name
  this.setLastName = function (newLastName) {
    if (typeof newLastName === 'string') {
      _lastName = newLastName;
    } else {
      console.error('Invalid input. Please provide a string for the last name.');
    }
  };
}

// Creating an instance of the Person object
const person = new Person('John', 'Doe');

// Using getters
console.log(person.getFirstName()); // Output: John
console.log(person.getLastName());  // Output: Doe

// Using setters
person.setFirstName('Jane');
person.setLastName('Smith');

// Checking the updated values using getters
console.log(person.getFirstName()); // Output: Jane
console.log(person.getLastName());  // Output: Smith

In this example, the Person constructor function has private variables _firstName and _lastName, and it provides getters and setters to access and modify these values. The use of getters and setters allows for controlled access and modification of the object's properties. Note that the names of the getters and setters do not necessarily have to match the variable names; it's a common convention to use get 
