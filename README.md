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
//Vehicle Rental Management System
//Build a simple command-line application that manages a fleet of vehicles. You'll create a base class vehicle and exten it into specific types like Car and Bike. Additionally, You'll define two interfaces.
/*
Insurable : Provides a method to calculate an insurance premium.
Rentable : Provides a method to compute rental costs based on the number of days.
 */

//Base class for vehciles
open class Vehicle(val brand: String, val model: String) {
    open fun startEngine() {
        println("Starting engine of $brand $model")
    }

    open fun getDetails(): String {
        return "$brand $model"
    }
}

//Interface for insurance-related functionality
interface Insurable{
    fun getInsuranceRate(): Double
}

//Interface for rental-related functionality
interface Rentable {
    fun getRentalCost(days: Int): Double
}

//Car class inherits from vehicle and implements insurable and Rentable
class Car(brand: String, model: String, private val baseRentalRate: Double): Vehicle(brand,model), Insurable, Rentable {

    override fun startEngine() {
        println("$brand $model roars to life with a powerful engine!")
    }

    // Dummy calculation for insurance rate
    override fun getInsuranceRate(): Double {
        return 300.0 + baseRentalRate*0.05
    }

    // Calculate rental cost based on days
    override fun getRentalCost(days: Int): Double {
        return baseRentalRate * days
    }
}

//Bike class inherits from vehicle and implements rentable
class Bike(brand: String, model: String, private val baseRentalRate: Double): Vehicle(brand, model), Rentable {
    fun getEngine(){
        println("$brand $model starts with a smooth kick-start!")
    }

    override fun getRentalCost(days: Int): Double {
        return baseRentalRate * days
    }
}

//Main function to simulate the rental system
fun main() {
    // Create a fleet of vehicle
    val fleet = listOf<Vehicle> (
        Car("Toyata","Corolla",50.0),
        Car("Honda","Civic",55.0),
        Bike("Yamaha","RTS",30.0),
        Bike("Suzuka","Gixxer",25.0)
    )

    println("Welcome to the Vehicle Rental Management System!")
    println("-------------------------------------------------")

    //Simulate operations on each  vehicle in the fleet
    for (vehicle in fleet) {
        println("\n Vehicle: ${vehicle.getDetails()}")
        vehicle.startEngine()

        //Check  if the vehicle is insurable
        if (vehicle is Insurable) {
            println("Insurable Rate: ${vehicle.getInsuranceRate()}")
        }

        //Check if the vehicle is rentable and calculate cost for 3 days
        if (vehicle is Rentable) {
            println("Rental cost for 3 days : ${vehicle.getRentalCost(3)}")
        }
    }
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


