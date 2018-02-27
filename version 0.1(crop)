# Python 3.4
# -*- coding: utf-8 -*-
"""création du premier programme, utile pour la syntaxe im montre comment apporter des modifs simples à l'image donnée et surtout 
intègre la fonction crop qui nous servira à modifier notre BD d'image pour tout uniformiser"
# importation du module Image de la librairie PIL

from PIL import Image

def crop(im, top, left, bottom, right):
    taille=( right-left-1 ,bottom-top-1)
    im2 = Image.new('RGB',taille) 
    pixel=im.load()
    pixel2=im2.load()
    
    for x in range (taille[0]):
        for y in range(taille[1]):
            pixel2[x,y]=pixel[left+x,top+y]
    return im2       
    pass
# ouverture de l'image

img = Image.open('lena30.jpg')
# affichage de l'image
img.show()
# affichage de la taille de l'image (en pixels)
print (img.size)
# conversion au format PPM (en couleur) et enregistrement de l'image
img.save('photo.ppm','PPM')
img.show()
# conversion en niveau de gris (pour obtenir le format PGM)
img0 = img.convert('L')
# enregistrement dans le fichier image.pgm
img0.save('image.pgm')
img0.show()

# retournement de l'image
img1 = img0.rotate(180)
# affichage et enregistrement de l'image retourn�e
img1.show()
img1.save('image_retourne.pgm')

# miroir horizontal
img2 = img0.transpose(Image.FLIP_LEFT_RIGHT)
img2.show()
img2.save('image_miroir_horizontal.pgm')

# miroir vertical
img3 = img0.transpose(Image.FLIP_TOP_BOTTOM)
img3.show()
img3.save('image_miroir_vertical.pgm')

# d�coupage de l'image au format saisi 

bas = int(input('bas de l\'image (en pixels) ? '))
Hauteur = int(input('Hauteur de l\'image (en pixels) ? '))
gauche = int(input('gauche de l\'image (en pixels) ? '))
droite = int(input('droite de l\'image (en pixels) ? '))
img4 = crop(img,Hauteur,gauche,bas,droite)
img4.show()
img4.save('lacrope.pgm')
