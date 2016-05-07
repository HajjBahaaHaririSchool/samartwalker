# samartwalker
import RPi.GPIO as GPIO

from time import sleep

GPIO.setmode(GPIO.BOARD)
GPIO.setwarnings(False)
GPIO.setup(26,GPIO.OUT)
GPIO.output(26,GPIO.HIGH)

Motor1A=16
Motor1B=18
Motor1C=22

Motor2A=23
Motor2B=21
Motor2C=19

GPIO.setup(13,GPIO.IN,pull_up_down=GPIO.PUD_DOWN)
GPIO.setup(10,GPIO.IN,pull_up_down=GPIO.PUD_DOWN)
GPIO.setup(11,GPIO.IN,pull_up_down=GPIO.PUD_DOWN)
GPIO.setup(15,GPIO.IN,pull_up_down=GPIO.PUD_DOWN)

GPIO.setup(Motor1A,GPIO.OUT)
GPIO.setup(Motor1B,GPIO.OUT)
GPIO.setup(Motor1C,GPIO.OUT)

GPIO.setup(Motor2A,GPIO.OUT)
GPIO.setup(Motor2B,GPIO.OUT)
GPIO.setup(Motor2C,GPIO.OUT)
while True:
    if(GPIO.input(13)==1):
       GPIO.output(Motor2A,GPIO.HIGH)
       GPIO.output(Motor2B,GPIO.LOW)
       GPIO.output(Motor2C,GPIO.HIGH)
       GPIO.output(Motor1A,GPIO.HIGH)
       GPIO.output(Motor1B,GPIO.LOW)
       GPIO.output(Motor1C,GPIO.HIGH)
    elif(GPIO.input(10)==1):
       GPIO.output(Motor2A,GPIO.LOW)
       GPIO.output(Motor2B,GPIO.HIGH)
       GPIO.output(Motor2C,GPIO.HIGH)
       GPIO.output(Motor1A,GPIO.LOW)
       GPIO.output(Motor1B,GPIO.HIGH)
       GPIO.output(Motor1C,GPIO.HIGH)
    elif(GPIO.input(11)==1):
       GPIO.output(Motor2A,GPIO.HIGH)
       GPIO.output(Motor2B,GPIO.LOW)
       GPIO.output(Motor2C,GPIO.HIGH)
       GPIO.output(Motor1A,GPIO.LOW)
       GPIO.output(Motor1B,GPIO.HIGH)
       GPIO.output(Motor1C,GPIO.HIGH) 
    elif(GPIO.input(15)==1):
       GPIO.output(Motor2A,GPIO.LOW)
       GPIO.output(Motor2B,GPIO.HIGH)
       GPIO.output(Motor2C,GPIO.HIGH)
       GPIO.output(Motor1A,GPIO.HIGH)
       GPIO.output(Motor1B,GPIO.LOW)
       GPIO.output(Motor1C,GPIO.HIGH)      
    elif(GPIO.input(13)==0):
        GPIO.output(Motor1C,GPIO.LOW)
        GPIO.output(Motor2C,GPIO.LOW)
    
