### Abstraction

> Abstraction is a concept that allows you to focus on the essential attributes and behaviors of an object while hiding the unnecessary details. It involves representing only the relevant characteristics of an object, and hiding the complex implementation details from the user.

Let's break this down with a simple example:

Consider a car. When you think about a car, you don't need to know every intricate detail of how the engine works or how the transmission shifts gears in order to drive it. Instead, you focus on the essential features like steering, accelerating, and braking.

In OOP, abstraction allows us to create a `Car` class that encapsulates these essential features without revealing the internal complexities. Here's a basic implementation:

```typescript
abstract class Vehicle {
  private speed: number = 0;

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

We define methods like `accelerate` and `brake` to manipulate the speed of the car.
The user interacts with the car object through these methods without needing to know how they are implemented internally.
So, in essence, abstraction allows us to think about objects at a higher level of understanding, focusing on what they do rather than how they do it.
