# Homework

Downsampling is the process of reducing the size of an image. For example, Downsampling by a factor of 2 would reduce a 10 by 10 image to a 5 by 5 image. One way to do this is to divide the image into 2 x 2 blocks and calculate the average of each block as in {numref}`downsampling-fig`.

```{figure} downsampling.jpg
---
height: 150px
name: downsampling-fig
---
Downsampling a 4 by 4 array by a factor of 2 by averaging 2 by 2 blocks.
```

1. Write code which downsamples the falling cat image by a factor of 2.
2. Write a function `downsample(x, k)` which downsamples the array `x` by a factor `k`. Test your function against the falling cat image for various values of `k`.

Upsampling is the reverse process. For example, upsampling by a factor of 2 would increase a 10 by 10 image to a 20 by 20 image. This can be achieved by repeating each element in 2 by 2 blocks as in {numref}`upsampling-fig`.

```{figure} upsampling.jpg
---
height: 150px
name: upsampling-fig
---
Upsampling a 4 by 4 array by a factor of 2 by repeating each element in 2 by 2 blocks.
```

3\. Write a function `upsample(x, k)` which upsamples the array `x` by a factor `k`. Test your function against the falling cat image for various values of `k`.

