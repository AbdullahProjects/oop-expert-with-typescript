### Abstraction

> Abstraction is a concept that allows you to focus on the essential attributes and behaviors of an object while hiding the unnecessary details. It involves representing only the relevant characteristics of an object, and hiding the complex implementation details from the user.

Let's break this down with a simple example:

Consider a car. When you think about a car, you don't need to know every detail of how the engine works or how the transmission shifts gears in order to drive it. Instead, you focus on the essential features like steering, accelerating, and braking.

In OOP, abstraction allows us to create a `Car` class that encapsulates these essential features from a vehicle without revealing the internal complexities. Here's a basic implementation:

```typescript
abstract class Vehicle {
  protected speed: number = 0;

  // Abstract methods (no implementation)
  abstract accelerate(): void;
  abstract brake(): void;

  // Shared behavior
  getSpeed(): number {
    return this.speed;
  }
}

class Car extends Vehicle {
  accelerate(): void {
    this.speed += 20; // Cars accelerate faster
  }

  brake(): void {
    this.speed -= 20;
  }
}

class Bike extends Vehicle {
  accelerate(): void {
    this.speed += 10; // Bikes accelerate slower
  }

  brake(): void {
    this.speed -= 10;
  }
}

// Usage
const vehicle: Vehicle = new Car();

vehicle.accelerate();
console.log("Speed:", vehicle.getSpeed());
```

In this example:

We create abstract class of `Vehicle` and create abstract methods only `accelerate` and `brake` without any implementation.
Then, we create a `Car` class and inherit Vehicle inside it. Now, Car will need to implement all the abstract methods defined in the abstract class of `Vehicle`.
So, in essence, abstraction allows us to think about objects at a higher level of understanding, focusing on what they do rather than how they do it.
