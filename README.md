# Pytorch useful stuff by me
## Collecting from the [Pytorch Tutorial](http://pytorch.org/tutorials) and the other sources (updating)
### [Torch Operations](http://pytorch.org/docs/stable/torch.html):
I have been listing some useful and common operations here to easily keep traces when coding
- Tensor:
  + Given x and y are Tensor matrices : Add operation:
  ```python
    x + y
    torch.add(x,y, out=result)
    y.add_(x)
  ```
  > Any operations that mutates a tensor in-place is post-fixed with and ' _ '. For example: `x.copy_()y`

  + More than 100 operations of torch in this [doc](http://pytorch.org/docs/stable/torch.html)
  + Converting Torch Tensor to Numpy and versa
  ```python
    # torch tensor to numpy
    a = torch.ones(5)
    b = a.numpy()
    # numpy to torch tensor
    a = np.ones(5)
    b = torch.from_numpy(a)
  ```
  + Resize/reshape: use `torch.view()`-`z = x.view(-1, n) #the size -1 inferred from other dimensons`
  + Tensors can be moved onto GPU using `.cuda()` method
  ```python
    if torch.cuda.is_available():
      x = x.cuda()
      y = y.cuda()
      x + y
  ```
  + `torch.mm(mat1, mat2, output=None)` multiplies two matrix `mat1` and `mat2`
  + `torch.mv(mat1, vec1, output=None)` multiplies a matrix `mat1` and `vec1`
  + `torch.clamp(input, min, max, output)` clamp all elements in `input` into the range `[min, max]` and return a resulting tensor

### Autograd: Automatic differentiation
The `autograd` package provides automatic differentiation for all operations on Tensors
- Variable: `autograd.Variable` is a wrapper of almost operations defined on Tensor. After all computation, call `backward()` to get all gradients computed automatically. Access the raw tensor through `.data` attributes and gradients through `.grad`
- ![Variable](http://pytorch.org/tutorials/_images/Variable.png)
