# Bonk!

Bonk is a short and simple Lua library for collisions.

It's currently in early stages, and as such only does AABB collisions with rectangles.

It was made during the development of Moth Warrior, mostly because I wanted to use as little libraries as possible.

## How To Use

Bonk is made with simplicity in mind.

Here's an example:

```
objectPlayer = {x = 50, y = 64, img = imageClass}

createCollisionBox(objectPlayer, 64, 64)

objectThing = {x = 100, y = 64, img = imageClass}

createCollisionBox(objectThing, 64, 64)

function update()
    bonkUpdate()
    
    if checkOverlap(objectPlayer.bbox, objectThing.bbox) then
        doStuff()
    end
    
end
```

But what does each function do?

| Command     | Description | Use     |
| :---        |    :----:   |          ---: |
| createCollisionBox(gameObject, width, height)      | Creates a bounding box (or bbox for short) and appends it to the provided game object.       | createCollisionBox(player, 64, 64)   |
| checkOverlap(box1, box2)   | Checks if the provided boxes are overlapping        | checkOverlap(player, enemy)      |
| advancedOverlap(x1,x2,y1,y2,w1,w2,h1,h2) | Checks if the provided x, y, width, and height values are overlapping | advancedOverlap(player.x + 1, wall.x, player.y + 1, wall.y, 64, 64, 64, 64) |
