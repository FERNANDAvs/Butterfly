import turtle
import math
import colorsys

screen = turtle.Screen()
screen.title("Borboleta — Ambas as Asas Batendo")
screen.bgcolor("black")
screen.colormode(1.0)
screen.tracer(0)

t = turtle.Turtle()
t.hideturtle()
t.pensize(2)

N = 1400
S = 60

def desenhar_borboleta(amplitude):
    t.clear()
    for i in range(N):
        a = i / N * 12 * math.pi
        r = (math.exp(math.cos(a))
             - 2 * math.cos(4 * a)
             - math.sin(a / 12) ** 5)

        x_base = S * r * math.sin(a)
        y = S * r * math.cos(a)

        # Aplica o fator de abertura para AMBOS os lados
        if x_base > 0:
            x = x_base * amplitude   # Asa DIREITA
        elif x_base < 0:
            x = x_base * amplitude   # Asa ESQUERDA
        else:
            x = 0

        t.color(colorsys.hsv_to_rgb(i / N, 1, 1))
        t.goto(x, y)

        if i % 7 == 0:
            t.goto(0, 0)
            t.goto(x, y)
            t.dot(5)
    screen.update()

# Loop animação: abre → fecha → repete
while True:
    # Sequência: normal → bem aberta → normal → fechada → normal
    for amp in [1.0, 1.25, 1.0, 0.75, 1.0]:
        desenhar_borboleta(amp)
        screen.delay(70)
