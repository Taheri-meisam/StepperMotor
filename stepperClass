import time
import RPi.GPIO as GPIO


GPIO.setmode(GPIO.BOARD)
GPIO.setup(22,GPIO.OUT)
GPIO.output(22,GPIO.LOW)


class Motor():
    def __init__(self, DirectionPin, StepPin):
        self.DirectionPin = DirectionPin
        self.StepPin = StepPin
        GPIO.setup(DirectionPin,GPIO.OUT)
        GPIO.setup(StepPin,GPIO.OUT)
        self.p = GPIO.PWM(self.StepPin,500)
        self.p.start(0)
    def MoveRight(self, Dir, St):
        GPIO.output(self.DirectionPin,Dir)
        while St > 0:
            self.p.start(1)
            time.sleep(0.0208)
            St-=1
        self.p.stop()
        return True
    def MoveLeft(self, x = 50, t=0):
        sleep(t)
    def stop(self,t=0):
        sleep(t)

Motor1 = Motor(18,16)

while True:
    direcInput = raw_input(" enter O or C: ")
    numSteps = raw_input("how many steps : ")
    if direcInput == 'c':
        Motor1.MoveRight(1,int(numSteps))
        print("Clock wise")
    else:
        Motor1.MoveRight(0,int(numSteps))
        print("anti clockwise")
GPIO.cleanup()


