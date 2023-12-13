---
layout: post
title: Mario Platforms Lesson
description: A lesson designed to help you create your own platform for your game
courses: {'csse': {'week': 8}}
type: ccc
author: Gavin Copley, Zafeer Ahmed, Ryan Nguyen
---

<a href="https://ryann96.github.io/Team-Project/mariogame">Mario Platforms</a>

### Using OOP
- We use Object Orientated Programming to complete this task. OOP uses objects, classes, variables, and includes a plethora of other items to create, in this case, a developed and fully functional javascript game! Follow along as we go through the steps to make 3 of the following additions: A platform, a coin, and a scoreboard.

## Making A Platform
- First, we need to make a new .js file to store our information
- We named ours PlatformO.js
- Include the following code to make sure that it runs with the rest of the game


```python
import GameEnv from './GameEnv.js';
import GameObject from './GameObject.js';

export class PlatformO extends GameObject {
    constructor(canvas, image) {
        super(canvas, image, 0);
    }

    // Required, but no update action
    update() {
    }

    // Draw position is always 0,0
    draw() {
        this.ctx.drawImage(this.image, 0, 0);
    }

    // Set platform position
    size() {
        // Formula for Height should be on constant ratio, using a proportion of 832
        const scaledHeight = GameEnv.innerHeight * (60/832);
        // Formula for Width is scaled: scaledWidth/scaledHeight == this.width/this.height
        const scaledWidth = 150;
        const platformX = .1 * GameEnv.innerWidth;
        const platformY = (GameEnv.bottom - scaledHeight) - 150;

        // set variables used in Display and Collision algorithms
        this.bottom = platformY;
        this.collisionHeight = scaledHeight;
        this.collisionWidth = scaledWidth;
    
        //this.canvas.width = this.width; 
        //this.canvas.height = this.height;
        this.canvas.style.width = `${scaledWidth}px`;
        this.canvas.style.height = `${scaledHeight}px`;
        this.canvas.style.position = 'absolute';
        this.canvas.style.left = `${platformX}px`;
        this.canvas.style.top = `${platformY}px`; 

    }
}

export default PlatformO;
```

### Constructor and Super
- Constructor is used to initialize an object and to set it's values
- Super is used to inherit traits from a parent object.

- Most of the values are changeable; we can change the position, size, and so on for the platform. Be sure to experiment!


