.. _cn_api_nn_cn_gumbel_softmax:

gumbel_softmax
-------------------------------
.. py:function:: paddle.nn.functional.gumbel_softmax(x, temperature = 1.0, hard = False, axis = -1, name = None)


该OP实现了按Gumbel-Softmax分布进行采样的功能，通过hard可选择是否离散化。
记temperature为t，涉及到的等式如下：

1. 产生gumbel噪声

.. math::

    G_i = -log(-log(U_i)),\ U_i \sim U(0,1)

2. 对输入x添加噪声

.. math::

    v = [x_1 + G_1,...,x_n + G_n]

3. 计算gumbel_softmax

.. math::

    gumbel\_softmax(v_i)=\frac{e^{v_i/t}}{\sum_{j=1}^n{e^{v_j/t}}},i=1,2,3...n


参数
::::::::::
    - x (Tensor) - 一个N-D Tensor，前N-1维用于独立分布batch的索引，最后一维表示每个类别的概率，dtype类型为float，double。
    - temperature (float，可选) - 大于0的标量。默认值：1.0。
    - hard (bool，可选) - 如果是True，返回离散的one-hot向量。如果是False，返回软样本。默认值：False。
    - axis (int，可选) - 按照维度axis计算softmax。默认值：-1。
    - **name** (str，可选) - 具体用法请参见 :ref:`api_guide_Name`，一般无需设置，默认值为 None。

返回
::::::::::
    与 ``x`` 形状相同的符合gumbel-softmax分布的 ``Tensor``。如果 ``hard=True``，则返回的样本将是one-hot。如果 ``hard=False``，则返回的向量将是各维度加起来等于1的概率。

代码示例
::::::::::

COPY-FROM: paddle.nn.functional.gumbel_softmax