# Pytorch useful stuff by me
## Collecting from the [Pytorch Tutorial](http://pytorch.org/tutorials) and the other sources (updating)
### Operations:
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
