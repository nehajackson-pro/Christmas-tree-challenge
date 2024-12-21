# Christmas-tree-challenge
import turtle

# Set up the screen
screen = turtle.Screen()
screen.bgcolor("sky blue")

# Create a turtle named "tree"
tree = turtle.Turtle()
tree.color("green")
tree.speed(3)

# Function to draw a triangle
def draw_triangle(size):
    for _ in range(3):
        tree.forward(size)
        tree.left(120)

# Function to draw the Christmas tree
def draw_tree(levels, size):
    for i in range(levels):
        draw_triangle(size)
        tree.penup()
        tree.backward(size / 2)
        tree.right(90)
        tree.forward(size / 2)
        tree.left(90)
        tree.pendown()
        size *= 0.8

# Draw the tree
tree.penup()
tree.goto(0, -200)
tree.pendown()
draw_tree(5, 200)

# Draw the trunk
tree.penup()
tree.goto(-15, -200)
tree.pendown()
tree.color("brown")
tree.begin_fill()
for _ in range(2):
    tree.forward(30)
    tree.right(90)
    tree.forward(60)
    tree.right(90)
tree.end_fill()

# Hide the turtle
tree.hideturtle()

# Keep the window open
turtle.done()
