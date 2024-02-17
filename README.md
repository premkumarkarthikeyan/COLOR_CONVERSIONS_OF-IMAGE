# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By:prem
### Register Number: 


## Output:

### i) Read and display the image
```
import cv2
image=cv2.imread('flower.jpg',1)
image=cv2.resize(image,(200,325))
cv2.imshow('prem',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### output:
![dip 1](https://github.com/premkumarkarthikeyan/COLOR_CONVERSIONS_OF-IMAGE/assets/119476243/5f3fd8cf-b1c1-42b3-8439-501e193234a6)

### ii)Write the image
```
import cv2
image=cv2.imread('flower.jpg',0)
cv2.imwrite('demos.jpg',image)
```
### output:
![dip2](https://github.com/premkumarkarthikeyan/COLOR_CONVERSIONS_OF-IMAGE/assets/119476243/3754b5a4-8cf0-4168-83a2-b12a92e4962c)

### iii)Shape of the Image
```
import cv2
image=cv2.imread('flower.jpg',1)
print(image.shape)
```
### output:
![dip3](https://github.com/premkumarkarthikeyan/COLOR_CONVERSIONS_OF-IMAGE/assets/119476243/89a6d490-b2dd-4ef4-9520-d30b6e4d9e75)

### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('flower.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                    random.randint(0,255),
                    random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### output:
![dip 4](https://github.com/premkumarkarthikeyan/COLOR_CONVERSIONS_OF-IMAGE/assets/119476243/cba8827b-ee7e-469f-93a6-a17dc5690820)

### v)Cut and paste portion of image
```
import cv2
image=cv2.imread('flower.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### output:
![dip 5](https://github.com/premkumarkarthikeyan/COLOR_CONVERSIONS_OF-IMAGE/assets/119476243/e8bcde2d-4f92-4988-a457-5e835824f045)

### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('flower.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### output:
![6](https://github.com/premkumarkarthikeyan/COLOR_CONVERSIONS_OF-IMAGE/assets/119476243/2c0837f8-d52b-497f-9a15-18953c770eb7)

### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('flower.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### output:
![dip7](https://github.com/premkumarkarthikeyan/COLOR_CONVERSIONS_OF-IMAGE/assets/119476243/77e7337b-0fa2-4fa8-a6a8-f033e8c5596e)


### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('flower.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### output:
![dip 8](https://github.com/premkumarkarthikeyan/COLOR_CONVERSIONS_OF-IMAGE/assets/119476243/210d14cb-7d10-42d4-a018-4f413c9afd3f)

### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('flower.jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### output:
![dip9](https://github.com/premkumarkarthikeyan/COLOR_CONVERSIONS_OF-IMAGE/assets/119476243/482853d3-75cc-4e7a-bbbc-a55a73403a2a)

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("flower.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### output:
![image](https://github.com/premkumarkarthikeyan/COLOR_CONVERSIONS_OF-IMAGE/assets/119476243/ac8aa2cc-0c9e-476e-9acb-941eee96654b)
## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







