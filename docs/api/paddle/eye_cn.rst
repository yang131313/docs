.. _cn_api_paddle_tensor_eye:

eye
-------------------------------

.. py:function:: paddle.eye(num_rows, num_columns=None, dtype=None, name=None)

构建二维Tensor(主对角线元素为1，其他元素为0)。

参数
::::::::::::

    - **num_rows** (int) - 生成2-D Tensor的行数，数据类型为非负int32。
    - **num_columns** (int，可选) - 生成2-D Tensor的列数，数据类型为非负int32。若为None，则默认等于num_rows。
    - **dtype** (np.dtype|str，可选) - 返回Tensor的数据类型，可为float16、float32、float64、int32、int64。若为None，则默认等于float32。
    - **name** (str，可选) - 具体用法请参见 :ref:`api_guide_Name`，一般无需设置，默认值为 None。

返回
::::::::::::
 ``shape`` 为 [num_rows, num_columns]的Tensor。

代码示例
::::::::::::

COPY-FROM: paddle.eye