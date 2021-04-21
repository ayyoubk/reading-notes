# CSS Transforms, Transitions, and Animations

***With CSS3 came new ways to position and alter elements. Now general layout techniques can be revisited with alternative ways to size, position, and change elements. All of these new techniques are made possible by the transform property.***

## Transform 

***The transform property comes in two different settings, two-dimensional and three-dimensional. Each of these come with their own individual properties and values.***

1. **2D Rotate**
*The rotate value provides the ability to rotate an element from 0 to 360 degrees.*

```
transform: rotate(20deg);
transform: rotate(-20deg);
```
2. **2D Scale**
*Using the scale value within the transform property allows you to change the appeared size of an element. The default scale value is 1, therefore any value between .99 and .01 makes an element appear smaller while any value greater than or equal to 1.01 makes an element appear larger.*

*It is possible to scale only the height or width of an element using the scaleX and scaleY values.*

*To scale both the height and width of an element but at different sizes, use the scale transform declaring the x axis value first, followed by a comma, and then the y axis value.*
```
transform: scale(.75);
transform: scale(1.5);
transform: scaleX(.5);
transform: scale(.5, 1.15);
```

3. **2D Translate**
*The translate value works a bit like that of relative positioning, pushing and pulling an element in different directions without interrupting the normal flow of the document.*

```
transform: translateX(-10px);
transform: translateY(25%);
transform: translate(-10px, 25%);
```

4. **2D Skew**
*The last transform value in the group, skew, is used to distort elements on the horizontal axis, vertical axis, or both.*

```
transform: skewX(5deg);
transform: skewY(-20deg);
transform: skew(5deg, -20deg);
```

***To combine transforms, list the transform values within the transform property one after the other without the use of commas.***

`transform: rotate(25deg) scale(.75);`


***As previously mentioned, the default transform origin is the dead center of an element, both 50% horizontally and 50% vertically. To change this default origin position the transform-origin property may be used.***

```
transform: scale(.5);
transform-origin: 100% 100%;
```

## Perspective

***In order for three-dimensional transforms to work the elements need a perspective from which to transform. The perspective for each element can be thought of as a vanishing point, similar to that which can be seen in three-dimensional drawings.***

*Using the perspective value within the transform property works great for transforming one element from a single, unique perspective. When you want to transform a group of elements all with the same perspective, or vanishing point, apply the perspective property to their parent element.*

`transform: perspective(200px) rotateX(45deg);`

## 3D Transforms

***there is another axis along which we can transform elements. Using three-dimensional transforms we can change elements on the z axis, giving us control of depth as well as length and width.***

- 3D Rotate `transform: perspective(200px) rotateZ(45deg);`
- 3D Scale `transform: perspective(200px) scaleZ(1.75) rotateX(45deg);`
- 3D Translate `transform: perspective(200px) translateZ(50px);`