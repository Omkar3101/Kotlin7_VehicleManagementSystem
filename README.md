# Vehicle Management System

A basic Vehicle Management System built using Kotlin that allows users to view vehicle details. This project is part of my Kotlin learning journey and focuses on OOP concepts like classes, inheritance, and interfaces.

## Features
1. Display vehicle information using object-oriented principles.
2. Demonstrates inheritance (Car, Bike, Truck extending a base Vehicle class).
3. Beginner-friendly Kotlin project that helps understand OOP in action.


## Technologies Used
1. Kotlin
2. IntelliJ IDEA


## How to Run the Project?

* Clone the Repository
https://github.com/YourGitHub/VehicleManagementSystem.git

* Open in IntelliJ IDEA

* Select Open Project and navigate to the cloned repository
  
* Run the Project
Open Main.kt file
Click on Run or use Shift + F10

* Add and Manage Vehicles
Enter vehicle details when prompted.
System will display vehicle-specific attributes using OOP principles.

* Code Overview

``` kotlin
// Base Vehicle class  
open class Vehicle(val name: String, val speed: Int) {  
    open fun displayInfo() {  
        println("Vehicle: $name, Speed: $speed km/h")  
    }  
}  

// Car class inheriting from Vehicle  
class Car(name: String, speed: Int, val fuelType: String) : Vehicle(name, speed) {  
    override fun displayInfo() {  
        println("Car: $name, Speed: $speed km/h, Fuel: $fuelType")  
    }  
}  

// Bike class inheriting from Vehicle  
class Bike(name: String, speed: Int, val hasGear: Boolean) : Vehicle(name, speed) {  
    override fun displayInfo() {  
        println("Bike: $name, Speed: $speed km/h, Gear: $hasGear")  
    }  
}  

// Main function to test the system  
fun main() {  
    val car = Car("Tesla", 200, "Electric")  
    val bike = Bike("Yamaha", 150, true)  

    car.displayInfo()  
    bike.displayInfo()  
}
``` 
## Future Improvements
🔹 Database integration for persistent vehicle storage
🔹 User input validation for real-world applications
🔹 Graphical UI version instead of console-based

## License
This project is licensed under the MIT License – see the LICENSE file for details.

## Let's Connect
LinkedIn
GitHub


