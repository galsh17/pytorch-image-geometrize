# pytorch-image-geometrize

Based on the idea demonstrated here: https://www.samcodes.co.uk/project/geometrize-haxe-web/

The algorithm approximates a given image using solid colored ellipses

Note that this is experimental and far from optimized code

The optimization algorithm works as follows:
1. generate N random sized ellipses
2. for each ellipse: optimize ellipse parameters - angle, x_scale, y_scale, translation and alpha using gradient decent ( loss = MSE(original image, approximated_image) )
3. add the ellipse if in the end the MSE is indeed lower than before

Gradient decent usage is possible due to kornia warping operations which are differentiable

# Examples
Full optimization:

![image](https://user-images.githubusercontent.com/46653045/177036059-fe9bd7bb-159e-4486-9e3d-cc1fe8edaddf.png)

Random ellipses without scale optimization:

![(2)](https://user-images.githubusercontent.com/46653045/177013188-989a8e19-d156-442c-befa-2705d8b19ca6.png)
![(6)](https://user-images.githubusercontent.com/46653045/177013191-35dcecfd-a513-4004-82a3-94edbf246408.png)

Fixed size circles:

![(3)](https://user-images.githubusercontent.com/46653045/177013190-37660699-ae43-4d55-a4a8-512a998eb88a.png)

High aspect ratio ellipses:

![image](https://user-images.githubusercontent.com/46653045/177024807-8ab9b936-cfb7-46a7-a73e-e23b16aea35f.png)

# Further directions:
1. Gradient decent stopping criteria (i.e. stop if improvement is less than certain threshold) - currently just fixed number of steps
2. Add more shapes
3. Hyperparameter tuning (tune lr per parameter)
4. Support color images
