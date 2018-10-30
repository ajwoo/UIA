# FWHT2

Fast Walsh–Hadamard transform

## Command

You can perform the Fast Walsh–Hadamard transform by using the command `./img.exe fwht2 imgin.pgm imgout.pgm`. This will perform the same operation that fwht(Matrix, Matrix_Size, 'hadamard') in matlab would perform.

### MatLab Output

![matlab](./screenshots/matlaboutput.png)

### UIA Output

#### Input Image

![imgpgm](./test/imgpgm.png)

#### Output Image

![imgpgm2](./test/imgpgmout.png)

## Image Loss

### Orignal Image

![lena](./lena/lena.png)

### First Transformation Performed

![lenaout](./lena/lenaout.png)

### Second Transformation Performed

![lenaout2](./lena/lenaout2.png)

## Code

```c
        for(int col = 0; col < cols3; ++col)
	    {
            double buffer[cols3];
            for(int row = 0; row < rows3; ++row)
            {
                buffer[row] = *(img_array1 + row*rows3 + col);
            }

            double* fwht = fwhtOneD(buffer, cols3);
            for(int row = 0; row < rows3; ++row)
            {
                *(img_array3 + row*rows3 + col) = (fwht[row])/rows3;
            }
        }
```

![idea](./idea.png)
