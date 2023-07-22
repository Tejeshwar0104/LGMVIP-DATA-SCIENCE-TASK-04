# LGMVIP-DATA-SCIENCE-TASK-04

CODE:

import cv2
from google.colab.patches import cv2_imshow

image = cv2.imread('/content/IMG_20230709_143935.jpg',cv2.IMREAD_COLOR)
cv2_imshow(image)

gray_scale = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2_imshow(gray_scale)

Neg_img = 255-gray_scale
cv2_imshow(Neg_img)

invert_gray = cv2.bitwise_not(gray_scale)
cv2_imshow(invert_gray)

Blur_img = cv2.GaussianBlur(Neg_img,(21,21),0)
cv2_imshow(Blur_img)

invert_blur = cv2.bitwise_not(Blur_img)

Pencil_img = cv2.divide(gray_scale, invert_blur, scale = 256.0)
cv2_imshow(Pencil_img)
