from turtle import *
import math
import colorsys

# ตั้งค่าหน้าต่างและความเร็ว (speed(5) จะทำให้เห็นจังหวะการวาดช้าลงและสวยงามขึ้น)
speed(5)
bgcolor("black")
hideturtle()

total_steps = 600
pensize(2)

for i in range(total_steps):
  t = i / 20
  
  # สมการหัวใจ
  x = 16 * math.sin(t) ** 3
  y = (
      13 * math.cos(t)
      - 5 * math.cos(2 * t)
      - 2 * math.cos(3 * t)
      - math.cos(4 * t)
  )

  # เปลี่ยนสีรุ้งเรื่อยๆ
  hue = i / total_steps
  r, g, b = colorsys.hsv_to_rgb(hue, 1.0, 1.0)
  color(r, g, b)

  penup()
  goto(x * 15, y * 15)
  pendown()

  if i % 10 == 0:
    write("I love you", align="center", font=("Arial", 8, "bold"))

done()
