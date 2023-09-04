# Pinhole camera
- Box with hole
- perfect image "point-sized" hole

# Virtual Camera
- Take a pixel on the image in the virtual world
- compute ray through hole and camera centre
- Intersect a ray with a scene

# Ray tracing
To make the image, we have to solve the equation
$E+tD=a+\beta(b-a)+\gamma(c-a)$
![[IMG_4281.jpeg]]
![[IMG_4282.jpeg]]

## Produce final image
- keep the closest intersection point

## Recap
```
For each pixel
	Distance = MAX
	Color = 0
	Ray = computeRay(pixel)
	For each triangle
		(CurrColor, CurrDistance) = computeIntersection(Ray)
		if(CurrDistance < Distance)
			Distance = CurrDistance
			Color = CurrColor
```

### Cost
Stupid implementation
- Ray tracing
- Cost = pixels ** Triangles

- Smart implementation
- Ray tracing
	Cost = pixels x log(triangles) + building a structure


# Rasterisation
![[IMG_4284.jpeg]]
![[IMG_4285.jpeg]]
![[IMG_4286.jpeg]]
![[IMG_4287.jpeg]]

### Cost
cost = triangles + "drawn pixels"

