def Encoder():
  import random
  
  alfa = ["a","b","c","d","e","f","g","h","i","j","k","l","m","n","o","p","q","r","s","t"]
  a = ""
  ip = str(input("Enter the text here: "))
  nip = ip.split()
  final = []

  number1 = random.randint(1,19)
  number2 = random.randint(1,19)
  number3 = random.randint(1,19)
  number4 = random.randint(1,19)
  number5 = random.randint(1,19)
  number6 = random.randint(1,19)

  for word in nip:
    if(len(word) > 3):
      r1 = alfa[number1] + alfa[number2] + alfa[number3]
      r2 = alfa[number4] + alfa[number5] + alfa[number6] 
      nword = r1 + word[1:] + word[0] + r2
      final.append(nword)

    elif(len(word) <= 3):
      nword = word[::-1]
      final.append(nword)

  for finale in final:
    a = a + finale + " "

  print(a)


  
def Decoder():
  oip = input("Enter the encoded text: ")
  final = [] 
  a = ""
  ip = oip.split()

  for og in ip:

    if(len(og) > 3):
      oword = og[-4] + og[3:-4]
      final.append(oword)

    elif(len(og) <= 3):
      oword = og[::-1]
      final.append(oword)

  for finale in final:
    a = a + finale + " "

  print(a)


mode = input("Which mode would you like to enter ?\n 1) Encode\n 2) Decode\n\n")

if(mode == "1"):
  Encoder()
  
elif(mode == "2"):
  Decoder()

