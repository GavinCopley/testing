---
toc: true
comments: false
layout: base
title: Platforms
description: PLatforms
type: devops
courses: { csse: {week: 3} }
---

<html>
    <head>
        <style>
            .indent {
                text-indent: 40px;
            }
            .space {
                padding-top: 10px;
                padding-bottom: 10px;
                margin-bottom: 10px;
            }
            .nav {
                border: 5px outset lime;
                background-color: white;
                text-align: left;
                color: black;
                padding-top: 5px;
                padding-bottom: 10px;
                padding-left: 15px;
                padding-right: 15px;
                margin-bottom: 10px;
                width: fit-content;
            }
            body {
                background-color: #A9A9A9;
            }
            .div1 {
                border: 5px outset red;
                background-color: white;
                text-align: left;
                color: black;
                padding-top: 5px;
                padding-bottom: 10px;
                padding-left: 15px;
                padding-right: 15px;
                margin-bottom: 10px;
            }
            .div2 {
                border: 5px outset blue;
                background-color: white;
                text-align: left;
                color: black;
                padding-top: 15px;
                padding-bottom: 5px;
                padding-left: 15px;
                padding-right: 15px;
                }
            .button {
                border-color: blue;
                padding-top: 15px;
                padding-bottom: 5px;
                padding-left: 15px;
                padding-right: 15px;
                }
        </style>
        <div class="nav">
            {% include nav_sharedGame.html %} <br>
            You are currently viewing: Platforms
        </div>
        <canvas></canvas>
        <script src="{{site.baseurl}}/assets/js/codeClimbers/game0-1.js" type="module"></script>
    </head>
    <body>
        <div class="space">
        </div>
        <div class="div1">
            <p title="Collision">
                platforms.forEach((platform) => {<br>
                    if (<br>
                    player.position.y + player.height <= platform.position.y && <br>
                    player.position.y + player.height + player.velocity.y >= platform.position.y && <br>
                    player.position.x + player.width >= platform.position.x && <br>
                    player.position.x <= platform.position.x + platform.width<br>
                    ){<br>
                    player.velocity.y = 0<br>
                    console.log("stop")<br>
                    }<br>
                    })<br>
                <br>
                This is the platforms collisions. This detects where the player is if their position is touching the platform. This makes it so the player can stand on the platform while being able to go underneath it.
            </p>
        </div>
        <div class="div2">
            <p title="Player">
                class Platform {<br>
                constructor({ x, y }) {<br>
                        this.position = {<br>
                            x,<br>
                            y<br>
                        }<br>
                        this.width = 200<br>
                        this.height = 20<br>
                    }<br>
                    draw() {<br>
                        c.fillStyle = "blue"<br>
                        c.fillRect(this.position.x, this.position.y, this.width, this.height)<br>
                    }<br>
                }<br>
                const platforms = [<br>
                    new Platform({<br>
                    x: 200, <br>
                    y:100,<br>
                }), new Platform({<br>
                    x: 500,  <br>
                    y: 200,<br>
                }), new Platform({<br>
                    x: -1,<br>
                    y: 416,<br>
                }), new Platform({<br>
                    x: 899,<br>
                    y: 416,<br>
                })<br>
                ]<br>
                <br>
                This is the platform class. This defines a platform and raws them on the canvas. The constant "platforms" makes it so I can add new platforms
            </p>
        </div>
        <div class="button">
            <button id="backBtn">Back</button>
            <button id="nextBtn">Next</button>
        </div>
    </body>
</html>

<script>
    document.getElementById("nextBtn").addEventListener("click", function() {
            window.location.href = "{{site.baseurl}}/2023/10/16/images.html";
    }); 
    document.getElementById("backBtn").addEventListener("click", function() {
            window.location.href = "{{site.baseurl}}/2023/11/04/player.html";
    }); 
</script>