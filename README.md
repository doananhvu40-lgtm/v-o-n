from machine import Pin, PWM
import time

# Khởi tạo PWM cho 3 chân điều khiển màu đỏ, xanh lá, xanh dương
red = PWM(Pin(15))
green = PWM(Pin(14))
blue = PWM(Pin(13))
    
# Đặt tần số PWM phù hợp cho LED (thường là 500Hz)
red.freq(500)
green.freq(500)
blue.freq(500)

# Hàm để tạo màu từ giá trị R, G, B (0 - 255)
def set_color(r, g, b):
    # Chuyển đổi giá trị 0-255 sang giá trị PWM 16-bit (0-65535)
    red.duty_u16(int(r * 257))
    green.duty_u16(int(g * 257))
    blue.duty_u16(int(b * 257))

# Vòng lặp tự động thay đổi màu
while True:
    set_color(255, 0, 0)    # Màu đỏ
    time.sleep(1)
    set_color(0, 255, 0)    # Màu xanh lá
    time.sleep(1)
    set_color(0, 0, 255)    # Màu xanh dương
    time.sleep(1)
    set_color(255, 255, 0)  # Màu vàng
    time.sleep(1)
    set_color(0, 255, 255)  # Màu lơ xanh
    time.sleep(1)
    set_color(255, 0, 255)  # Màu hồng
    time.sleep(1)
    set_color(255, 255, 255)# Màu trắng
    time.sleep(1)
    set_color(0, 0, 0)      # Tắt đèn
    time.sleep(1)
# v-o-n
