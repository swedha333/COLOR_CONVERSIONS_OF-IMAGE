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
### Developed By: Sudhakar K
### Register Number: 212222240107


## Output:

### i) Read and display the image
```python
    import cv2
    image=cv2.imread('sudhax.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('sudhax',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
## Output:
![Screenshot 2024-02-19 230600](https://github.com/swedha333/COLOR_CONVERSIONS_OF-IMAGE/assets/118622513/7dbebea8-9f35-4b39-8c65-762774031609)


### ii)Write the image
```python
    import cv2
    image=cv2.imread('sudhax.jpg',0)
    cv2.imwrite('test.jpg',image)
```
## Output:
![Screenshot 2024-02-19 230835](https://github.com/swedha333/COLOR_CONVERSIONS_OF-IMAGE/assets/118622513/05b78413-ba11-49fe-81ad-87a0e96dd911)


### iii)Shape of the Image
```python
    import cv2
    image=cv2.imread('sudhax.jpg',1)
    print(image.shape)
```
## Output:
![Screenshot 2024-02-19 230932](https://github.com/swedha333/COLOR_CONVERSIONS_OF-IMAGE/assets/118622513/1535b019-28a2-44e8-91d8-ec95f3a91fb4)


### iv)Access rows and columns
```python
import random
import cv2
image=cv2.imread('sudhax.jpg',1)
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
## Output:
![Screenshot 2024-02-19 231054](https://github.com/swedha333/COLOR_CONVERSIONS_OF-IMAGE/assets/118622513/39d2b7ed-64a7-4213-8e20-f575af1626de)


### v)Cut and paste portion of image
```python
import cv2
image=cv2.imread('sudhax.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![Screenshot 2024-02-19 231303](https://github.com/swedha333/COLOR_CONVERSIONS_OF-IMAGE/assets/118622513/195b7ab5-3a21-40ff-aa75-4d988f9fd52d)


### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('sudhax.jpg',1)
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
## Output:
![Screenshot 2024-02-19 231532](https://github.com/swedha333/COLOR_CONVERSIONS_OF-IMAGE/assets/118622513/c9115a25-9d3a-4937-9201-ddfca22ef549)


### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('sudhax.jpg')
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
## Output:
![Screenshot 2024-02-19 231650](https://github.com/swedha333/COLOR_CONVERSIONS_OF-IMAGE/assets/118622513/aa0f2a6b-671d-4ee9-b864-2ad1aef6a003)


### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('sudhax.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![Screenshot 2024-02-19 231833](https://github.com/swedha333/COLOR_CONVERSIONS_OF-IMAGE/assets/118622513/fe0359cc-dede-44ba-8953-1753e27ae277)


### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('sudhax.jpg',1)
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
## Output:
![Screenshot 2024-02-19 232018](https://github.com/swedha333/COLOR_CONVERSIONS_OF-IMAGE/assets/118622513/409dfe98-db58-4ca6-9904-58f5d0d1eeb4)


### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("sudhax.jpg",1)
img = cv2.resize(img,(200,200))
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
## Output:
![Screenshot 2024-02-19 232257](https://github.com/swedha333/COLOR_CONVERSIONS_OF-IMAGE/assets/118622513/12a6f007-b93b-402c-a01f-465361a9e487)



## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







