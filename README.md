# proyecto2
def identificador(info,lista):
  devuelto1=[]
  devuelto2=[]
  for i in lista: #leer cada archivo
    archivo=open(i,'r')
    contador=0
    for j in archivo: #leer cada linea      
      for k in info: #leer cada palabra de info
        if k.lower() in j: #ver si cada palabra esta en la linea
          contador+=1
    if contador==len(info):
      devuelto1.append(i)
  for i in devuelto1:
    if i not in devuelto2:
      devuelto2.append(i)
  enfermedades=''
  for i in range(0,len(devuelto2)):
    enfermedades+=devuelto2[i]
    if i!=len(devuelto2)-1:
      enfermedades+=','
  return enfermedades
lista=['lupus','cancer','celaquia', "enfermedad de crohn","artritis reumatoide","diabetes tipo 1","anemia perniciosa","vitiligo","enfermedad de addison"]
opcion=''
while opcion!='3':
  opcion=input('Elija una opcion:\n\t1)Informacion de una enfermedad\n\t2)Buscar una enfermedad segun sus datos\n\t3)Detener el programa\n->')
  if opcion=='1' or opcion=='1)':
    info= input('Ingrese el nombre de la enfermedad:\n\t->')
    if info in lista:
      with open(info.lower(), 'r') as f:
        for line in f:
          print(line, end='')
    else:
      print('Esa enfermedad no es valida o aun no esta registrada en este programa')
  if opcion=='2' or opcion=='2)':
    info=input('Ingrese los datos sobre la enfermedad separados por comas(,):\n>').split(',')
    print(identificador(info,lista))
  print('|||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||')
