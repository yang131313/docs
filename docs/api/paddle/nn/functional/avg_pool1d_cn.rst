.. _cn_api_nn_functional_avg_pool1d:


avg_pool1d
-------------------------------

.. py:function:: paddle.nn.functional.avg_pool1d(x, kernel_size, stride=None, padding=0, exclusive=True, ceil_mode=False, name=None)

该算子根据输入 `x` , `kernel_size` 等参数对一个输入Tensor计算1D的平均池化。输入和输出都是3-D Tensor，
默认是以 `NCL` 格式表示的，其中 `N` 是 batch size, `C` 是通道数，`L` 是输入特征的长度。

.. note::
   详细请参考对应的 `Class` 请参考：:ref:`cn_api_nn_AvgPool1D` 。


参数
:::::::::
    - **x** (Tensor)：当前算子的输入，其是一个形状为 `[N, C, L]` 的3-D Tensor。其中 `N` 是batch size, `C` 是通道数，`L` 是输入特征的长度。其数据类型为float32或者float64。
    - **kernel_size** (int|list|tuple)：池化核的尺寸大小。如果kernel_size为list或tuple类型，其必须包含一个整数。
    - **stride** (int|list|tuple)：池化操作步长。如果stride为list或tuple类型，其必须包含一个整数。
    - **padding** (string|int|list|tuple)：池化补零的方式。如果padding是一个字符串，则必须为 `SAME` 或者 `VALID`。如果是turple或者list类型，则应是 `[pad_left, pad_right]` 形式。如果padding是一个非0值，那么表示会在输入的两端都padding上同样长度的0。
    - **exclusive** (bool)：是否用额外padding的值计算平均池化结果，默认为True。
    - **ceil_mode** (bool)：是否用ceil函数计算输出的height和width，如果设置为False，则使用floor函数来计算，默认为False。
    - **name** (str，可选) - 具体用法请参见 :ref:`api_guide_Name`，一般无需设置，默认值为 None。



返回
:::::::::
``Tensor``，输入 `x` 经过平均池化计算得到的目标3-D Tensor，其数据类型与输入相同。



代码示例
:::::::::

COPY-FROM: paddle.nn.functional.avg_pool1d