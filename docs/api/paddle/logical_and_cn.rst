.. _cn_api_fluid_layers_logical_and:

logical_and
-------------------------------

.. py:function:: paddle.logical_and(x, y, out=None, name=None)

逐元素的对 ``x`` 和 ``y`` 进行逻辑与运算。

.. math::
       Out = X \&\& Y

.. note::
    ``paddle.logical_and`` 遵守broadcasting，如您想了解更多，请参见 :ref:`cn_user_guide_broadcasting` 。

参数
::::::::::::

        - **x** （Tensor）- 输入的 `Tensor`，支持的数据类型为bool, int8, int16, in32, in64, float32, float64。
        - **y** （Tensor）- 输入的 `Tensor`，支持的数据类型为bool, int8, int16, in32, in64, float32, float64。
        - **out** （Tensor，可选）- 指定算子输出结果的 `Tensor`，可以是程序中已经创建的任何Tensor。默认值为None，此时将创建新的Tensor来保存输出结果。
        - **name** (str，可选) - 具体用法请参见 :ref:`api_guide_Name`，一般无需设置，默认值为 None。

返回
::::::::::::
 ``Tensor``，维度``x`` 维度相同，存储运算后的结果。

代码示例
::::::::::::

COPY-FROM: paddle.logical_and