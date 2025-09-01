# CODE-A-POOKKALAM
This project creates a beautiful and vibrant pookkalam(floral design for onam festival in kerala) using python turtle module.

#code

[flower.py](https://github.com/user-attachments/files/22073221/flower.py)
import turtle
import math
screen = turtle.Screen()
screen.title("Code a Pookalam")
screen.setup(width=800, height=800)
screen.bgcolor("brown")  # background

t = turtle.Turtle()
t.speed(0)
t.hideturtle()

COLORS = {
    "center_1": "yellow",
    "center_6": "#AA336A",
    "center_2": "#702963",
    "inner_petals2": "orange",
    "inner_petals3": "green",
    "inner_petals4": "pink",
    "border_dots": "ivory" ,
    "center_4": "gold",
    "center_3": "#770737",
    "outerdot":"red",
    "inner_petals5": "black",
}


# Filled Circle 

def draw_circle(tur, color, x, y, radius):
    tur.penup()
    tur.goto(x, y - radius)
    tur.pendown()
    tur.color(color)
    tur.begin_fill()
    tur.circle(radius)
    tur.end_fill()

# Draw filled Petal 
def draw_petal(tur, radius, angle):
    tur.begin_fill()
    tur.circle(radius, angle)
    tur.left(180 - angle)
    tur.circle(radius, angle)
    tur.left(180 - angle)
    tur.end_fill()

# Function for the Pookalam ---
def create_pookalam():
   
    t.penup() #outerpetal9
    t.goto(0, 0)
    t.pendown()
    t.color(COLORS["center_3"])
    t.setheading(0)
    for _ in range(12):
        t.forward(30)
        draw_petal(t, 227, 85)
        t.backward(30)
        t.right(30)

    t.penup() #petal8
    t.goto(0, 0)
    t.pendown()
    t.color(COLORS["inner_petals4"])
    t.setheading(0)
    for _ in range(12):
        t.forward(30)
        draw_petal(t, 220, 85)
        t.backward(30)
        t.right(30)

    draw_circle(t, COLORS["center_2"], 0, 0, 280) #circle7
    
    #petal7
    t.penup()
    t.goto(0, 0)
    t.pendown()
    t.color(COLORS["center_1"])
    t.setheading(0)
    for _ in range(12):
        t.forward(30)
        draw_petal(t, 190, 85)
        t.backward(30)
        t.right(30)

    t.penup() #petal6
    t.goto(0, 0)
    t.pendown()
    t.color(COLORS["inner_petals5"])
    t.setheading(0)
    for _ in range(12):
        t.forward(30)
        draw_petal(t, 217, 55)
        t.backward(30)
        t.right(30)
    draw_circle(t, COLORS["center_2"], 0, 0, 178) #circle6
    draw_circle(t, COLORS["inner_petals4"], 0, 0, 160) #circle5

    draw_circle(t, COLORS["inner_petals2"], 0, 0, 169.5) #circle4

    #petal5
    t.penup()
    t.goto(0, 0)
    t.pendown()
    t.color(COLORS["outerdot"])
    t.setheading(0)
    for _ in range(12):
        t.forward(30)
        draw_petal(t, 145, 85)
        t.backward(30)
        t.right(30)

    t.penup() #petal4
    t.goto(0, 0)
    t.pendown()
    t.color(COLORS["center_3"])
    t.setheading(0)
    for _ in range(12):
        t.forward(30)
        draw_petal(t, 128, 85)
        t.backward(30)
        t.right(30)

    t.penup() #petal3
    t.goto(0, 0)
    t.pendown()
    t.color(COLORS["center_6"])
    t.setheading(0)
    for _ in range(12):
        t.forward(30)
        draw_petal(t, 117, 85)
        t.backward(30)
        t.right(30)
   
    draw_circle(t, COLORS["center_3"], 0, 0, 140) #circle3
  
    # Layer 1: The Center Circle
    
    draw_circle(t, COLORS["center_2"], 0, 0, 129) #circle2
  
    #petal2
    t.penup()
    t.goto(0, 0)
    t.pendown()
    t.color(COLORS["center_1"])
    t.setheading(0)
    for _ in range(12):
        t.forward(30)
        draw_petal(t, 60, 60)
        t.backward(30)
        t.right(30)
    draw_circle(t, COLORS["outerdot"], 0, 0, 30) #circle1
    
    t.penup() #petal1
    t.goto(0, 0)
    t.pendown()
    t.color(COLORS["outerdot"])
    t.setheading(0)
    for _ in range(12):
        t.forward(30)
        draw_petal(t, 30, 60)
        t.backward(30)
        t.right(30)

    # white Border Dots
    angle = 0
    radius = 100
    for _ in range(45):
        # Calculate x and y coordinates on the circle's edge
        x = radius * math.cos(math.radians(angle))
        y = radius * math.sin(math.radians(angle))
        draw_circle(t, COLORS["border_dots"], x, y, 7)
        angle += 8 # angle for the next dot
        
    #pink borderdots   
    angle = 23.6
    radius = 290
    for _ in range(14):
        # Calculate x and y coordinates on the circle's edge
        x = radius * math.cos(math.radians(angle))
        y = radius * math.sin(math.radians(angle))
        draw_circle(t, COLORS["border_dots"], x, y, 7)
        angle += 30 # angle for the next dot

create_pookalam()
screen.update()
turtle.done()
