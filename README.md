# Input text(numbers) PYGAME

Add a field to your application in which you can type a number and use it.

![example](example.png)

## Basic example

```python
import pygame

pygame.init()
pygame.font.init()
screen = pygame.display.set_mode((300, 100))

#We create the text field
text = textInput(screen,20,30,200,50,maxdigit=15)

while True:

	pygame.display.update()

	events = pygame.event.get()
	for event in events:
		if event.type == pygame.QUIT:
			pygame.quit()
			exit()
	mouse = pygame.mouse.get_pos()
	x = mouse[0]
	y = mouse[1]

	#We update the text
	text.update(events,x,y)
```

## Functions

* __textinput.textInput(args)__
	create a text type object in which we will be able to type numbers
	the mandatory parameters are the app window, the position of the field and its size
* __textinput.textInput.update(args)__
	Update the content of the field based on events and mouse position
* __textinput.textInput.getValue()__
	receive the content of the field in float

## Hyperparameters of the functions

### textinput.textInput(args)

Required parameters : 
- screen = screen of your game/app (created with pygame.display.set_mode)
- axex = position x of the top left corner of the box
- axexy = position y of the top left corner of the box
- length = length of the box
- height = height of the box

Optional hyperparameters :
- maxdigit = number of digits allowed in the content (incl. point)
- textsize = size of the text
- textcolor = color of the text display
- bordercolor = color of the outer edge of the field
- bordercolor_click = color of the outer edge of the field when you click on
- fontcolor = field background color

### textinput.textInput.update(args)

Required parameters : 

- events : list of the events (get with pygame.event.get())
- posx = position x of the mouse
- posy = position y of the mouse

## AZERTY keyboard

La touche pour le point sur le clavier correspond à la touche [: /]

