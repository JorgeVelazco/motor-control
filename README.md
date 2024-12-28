

try:
    print("Motor B alternando dirección cada 2 segundos. Presiona CTRL-C para salir.")
    while True:
        
        Giro_Favor_Reloj_MotorB()
        pwm_b.ChangeDutyCycle(100)  
        print("Motor B: CW (sentido horario)")
        time.sleep(2)  # Espera 2 segundos

        Giro_Contra_Reloj_MotorB()
        pwm_b.ChangeDutyCycle(100) 
        print("Motor B: CCW (sentido antihorario)")
        time.sleep(2)  # Espera 2 segundos

except KeyboardInterrupt:
    pwm_a.stop()
    pwm_b.stop()
    GPIO.cleanup()
    os.system('clear')
    print("Programa terminado por el usuario.")
