# Objectives
1. Gain more experience creating and working with classes
2. Gain experience creating and working with classes with inheritance

# Technologies Used
- VSCode

# Part 1
Complete [Lab 6](https://pozawa1.github.io/cit281-lab6/)

# Part 2
Complete [Lab 7](https://pozawa1.github.io/cit281-lab7/)

# Part 3
Create p6.js in the cit281/p6 folder.

# Part 4
Create a Shape class that returns the perimeter value. 
```
class Shape {
    constructor(sides = []) {
        this.sides = sides;
    } 
    perimeter = () => (this.sides.length > 0 ? this.sides.reduce((sum, side) => sum + side, 0) : 0);
}
```

# Part 5
Create a Rectangle class that inherits from the Shape class and returns the area value. 
```
class Rectangle extends Shape {
    constructor(length = 0, width = 0) {
        super([length, width, length, width]); 
        this.length = length;
        this.width = width;
    }
    area() {
        return this.length * this.width;
    } 
}
```

# Part 6
Create a Triangle class that inherits from the Shape class and returns the area value. 
```
class Triangle extends Shape {
    constructor(sideA = 0, sideB = 0, sideC = 0) {
        super([sideA, sideB, sideC]);
        this.sideA = sideA;
        this.sideB = sideB;
        this.sideC = sideC;
    }
    area() {
        let s = (this.sideA + this.sideB + this.sideC) / 2;
        return Math.sqrt(s * (s - this.sideA) * (s - this.sideB) * (s - this.sideC));
    }
}
```

# Part 7
Create a generic block of code for processing the following array of sides arrays.
```
const data = [ [3, 4], [5, 5], [3, 4, 5], [10], [] ];

// Check if values of array are the same 
const equalValues = data => data.every( num => num === data[0]);

for (let i = 0; i < data.length; i++) {
    let numbers = data[i].toString();
    switch(data[i].length) {
        case 2:
            if (equalValues(data[i]) === true) {
                console.log(`Square with sides ${numbers} has perimeter of ${new Rectangle(...data[i]).perimeter()} and area of ${new Rectangle(...data[i]).area()}`)
            } else {
            console.log(`Rectangle with sides ${numbers} has perimeter of ${new Rectangle(...data[i]).perimeter()} and area of ${new Rectangle(...data[i]).area()}`);
            } break;
        case 3:
            console.log(`Triangle with sides ${numbers} has perimeter of ${new Triangle(...data[i]).perimeter()} and area of ${new Triangle(...data[i]).area()}`);
            break;
        default:
            console.log(`Shape with ${data[i].length} side unsupported`);
            break;
    }
}
```

Output:

![p6-01](https://user-images.githubusercontent.com/83732149/120240274-00e45d80-c215-11eb-8c9c-87d174e365f1.png)

[Source Code](https://github.com/pozawa1/cit281-p6/blob/main/source-code-p6)

[Return to Homepage](https://pozawa1.github.io/)
