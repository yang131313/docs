.. _cn_api_paddle_incubate_autograd_Hessian:

Hessian
-------------------------------

.. py:class:: paddle.incubate.autograd.Hessian(func, xs, is_batched=False)

计算函数 ``func`` 在 ``xs`` 处的海森矩阵。

其中，函数 ``func`` 的输入可以为Tensor或Tensor序列，输出要求为只包含单个元素的Tensor, 
``is_batched`` 表示是否支持batch, ``True`` 表示支持并默认第零维作为batch维。

在计算海森矩阵时，所有输入Tensor会沿着batch维外的其它维度进行展平，且当输入为Tensor序列时，
所有展平后的Tensor会被拼接成一个新的Tensor。因此，``Hessian`` 最终的输出为一个二维(不包含
batch)或三维(包含batch，第零维为batch)的Tensor。

例如，假设 ``is_batched=True``，输入Tensor经过展平并拼接后的形状为 ``(B, M)``，输出
Tensor形状为 ``(B, 1)``，则最终输出海森矩阵形状为 ``(B, M, M)``。其中，``B`` 为batch
维大小，``M`` 为展平并拼接后的输入大小。

可以通过对 ``Hessian`` 对象多维索引获取整个矩阵或子矩阵的实际结果，子矩阵会以惰性求值方式计算，
并且已经计算结果会被缓存，详细参考 :ref:`cn_api_paddle_incubate_autograd_Jacobian` 。

.. note::
  当前暂不支持省略号索引。

.. warning::
  该API目前为Beta版本，函数签名在未来版本可能发生变化。

参数
:::::::::

- **func** (Callable) - Python函数，输入参数为 ``xs``，输出为只包含一个元素Tensor，即
  如果 ``is_batched=True``，输出形状为 ``(B, 1)`` , ``B`` 表示batch大小，
  ``is_batched=False``，输出形状为 ``(1)`` 。
- **xs** (Tensor|Sequence[Tensor]） - 函数 ``func`` 的输入参数，数据类型为Tensor或
  Tensor序列。
- **is_batched** (bool) - ``True`` 表示包含batch维，且默认第零维为batch维，``False`` 
  表示不包含batch。默认值为 ``False`` 。

返回
:::::::::

用于计算海森矩阵的 ``Hessian`` 实例。

代码示例
:::::::::

COPY-FROM: paddle.incubate.autograd.Hessian
