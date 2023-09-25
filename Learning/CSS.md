Sizing :
for fonts :  rem  never use px (rem => root em)
for width : percentage it will take the relative of that size of parent tag.
For Margin and Padding : em
Border : px


## CSS Classes 
### Pseudo classes
-  visited
-  hover, focus
-  active
-  nth-child
This is the order which should be followed.
**Examples**  :		
 ```CSS
selector:visited{
/* 	CSS Properties */
}
selector:hover, selector:focus{
/* 	CSS Properties */
}
selector:active{
/* 	CSS Properties */
}
```

## Styling List
- list-style : this property can be used.
- ::marker : for changing the bullet points.

## Display Properties 
- inline elements , Examples : span etc
- block elements , Examples : main, h1 etc
height, margin , width etc properties are not applied on inline elements but by using *inline-block* property we can use them on inline elements.

Examples : 
```CSS
span{
	display : inline-block;
/* 	display : block; */
}
```

If you want to make in page thing like in portfolio set height to 100vh for each section.