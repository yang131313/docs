.. _cn_api_paddle_nn_functional_common_linear:

linear
-------------------------------


.. py:function:: paddle.nn.functional.linear(x, weight, bias=None, name=None)


**线性变换OP**。对于每个输入Tensor :math:`X`，计算公式为：

.. math::

    Out = XW + b

其中，:math:`W` 和 :math:`b` 分别为权重和偏置。

如果权重 :math:`W` 是一个形状为 :math:`[in\_features, out\_features]` 的2-D Tensor，输入则可以是一个多维Tensor形状为 :math:`[batch\_size, *, in\_features]`，其中 :math:`*` 表示可以为任意个额外的维度。
linear接口可以计算输入Tensor与权重矩阵 :math:`W` 的乘积，生成形状为 :math:`[batch\_size, *, out\_features]` 的输出Tensor。
如果偏置 :math:`bias` 不是None，它必须是一个形状为 :math:`[out\_features]` 的1-D Tensor，且将会被其加到输出中。


参数
:::::::::

- **x** (Tensor) – 输入Tensor。它的数据类型可以为float16，float32或float64。
- **weight** (Tensor) – 权重Tensor。它的数据类型可以为float16，float32或float64。
- **bias** (Tensor，可选) – 偏置Tensor。它的数据类型可以为float16，float32或float64。如果不为None，则将会被加到输出中。默认值为None。
- **name** (str，可选) - 具体用法请参见 :ref:`api_guide_Name`，一般无需设置，默认值为 None。


返回
:::::::::

Tensor，形状为 :math:`[batch\_size, *, out\_features]`，数据类型与输入Tensor相同。


代码示例
::::::::::

COPY-FROM: paddle.nn.functional.linear