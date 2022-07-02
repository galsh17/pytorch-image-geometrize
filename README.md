# pytorch-image-geometrize

This is based on the idea presented here: https://www.samcodes.co.uk/project/geometrize-haxe-web/

The optimization algorithm works as follows:
1. generate N random sized ellipses
2. for each ellipse: optimize angle, translation and alpha using gradient decent (on MSE with original image)
3. add the ellipse if in the end the MSE is indeed lower than before

gradient decent usage is possible due to kornia warping operations which are differentiable

![הורדה (2)](https://user-images.githubusercontent.com/46653045/177013188-989a8e19-d156-442c-befa-2705d8b19ca6.png)
![הורדה (3)](https://user-images.githubusercontent.com/46653045/177013190-37660699-ae43-4d55-a4a8-512a998eb88a.png)
![הורדה (6)](https://user-images.githubusercontent.com/46653045/177013191-35dcecfd-a513-4004-82a3-94edbf246408.png)
