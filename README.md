# evaluacion2D

import matplotlib.pyplot as plt
import numpy as np


plt.axis([0,350,350,0])
plt.axis('on')


#_____________CIRCULO
xc=150
yc=150

r=7*5  #EL ULTIMO DIGITO DE MI NUMEOR DE CONTROL * 5
p1=0*np.pi/180
p2=360*np.pi/180
dp=(p2-p1)/100

xlast=xc+r*np.cos(p1)
ylast=yc+r*np.sin(p1)

for p in np.arange(p1,p2+dp,dp):
    xp=xc+r*np.cos(p)
    yp=yc+r*np.sin(p)
    plt.plot([xlast,xp],[ylast,yp],color=(0,.1,.7),linewidth=2) 
    #COLOR SON LOS ULTIMOS 3 DIGITOS DEL NUMERO DE CONTROL(0,1,7)SOBRE 10 ->(0/10, 1/10,7/10)
    xlast=xp
    ylast=yp

#______________PRIMER RECTANGULO__________
xc=150#centro
yc=150

#----------PUNTOS DE LAS ESQUINAS DEL RECTANGULO
"""xp=np.array([70,0,0,70])  #EL LADO MAS LARGO DEL RECTANGULO ES EL DOBLE DEL RADIO DEL CIRCULO
yp=np.array([0,0,35,35])"""
#Si ocupamos estos numeros la figura no queda como la imagen, por lo que opte por utilizar 
# el doble del diamtero del circulo como el lado mas largo del rectangulo radio=35 diametro =70 lado =2*diametro=140

xp=np.array([140,0,0,140])  
yp=np.array([0,0,105,105])

xg1=xc+xp[0] #coordenadas en Xg, Yg -->sistema global
yg1=yc+yp[0] 
xg2=xc+xp[1] 
yg2=yc+yp[1] 
xg3=xc+xp[2] 
yg3=yc+yp[2] 
xg4=xc+xp[3] 
yg4=yc+yp[3] #coordenadas en Xg, Yg -->sistema global

xg=[xg1,xg2,xg3,xg4,xg1]
yg=[yg1,yg2,yg3,yg4,yg1]
plt.plot(xg,yg,color=(.7,0,.1)) #COLOR SON LOS ULTIMOS 3 DIGITOS DEL NUMERO DE CONTROL(0,1,7)SOBRE 10


#_____________SEGUNDO RECTANGULO
xc=220 #CENTRO
yc=202.5

xp=np.array([-150,0,0,-150])  
yp=np.array([0,0,-105,-105])

xg1=xc+xp[0] #coordenadas en Xg, Yg -->sistema global
yg1=yc+yp[0] 
xg2=xc+xp[1] 
yg2=yc+yp[1] 
xg3=xc+xp[2] 
yg3=yc+yp[2] 
xg4=xc+xp[3] 
yg4=yc+yp[3] #coordenadas en Xg, Yg -->sistema global

xg=[xg1,xg2,xg3,xg4,xg1]
yg=[yg1,yg2,yg3,yg4,yg1]

plt.plot(xg,yg,color=(.1,.7,0)) #COLOR SON LOS ULTIMOS 3 DIGITOS DEL NUMERO DE CONTROL(0,1,7)SOBRE 10

plt.axes().set_aspect('equal') 
plt.show()
