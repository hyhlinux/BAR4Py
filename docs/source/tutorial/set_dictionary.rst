自定义字典内容
=======================

现在我们来设置字典内容，值得注意的是这里的字典并不是 `python` 当中的字典数据类型，\
而是 **bar4py** Web 模块当中用于设置标记物对应模型的工具。

创建一个字典文件
----------------------

字典文件是一个 json 类型的文件，我们参考 WebARPlayer 默认的字典文件::


    {
        "701": {
            "type": "obj",
            "content": null,
            "opath": "/static/model/",
            "oname": "rocket.obj",
            "mpath": "/static/model/",
            "mname": "rocket.mtl",
            "visibleTag": 5
        }
    }

其中 ``"701": {`` 当中的 ``"701"`` 指的是标记物的名称，和标记物目录当中指定的标记物图片的名称一致，\
注意是不含扩展名的。如果你的标记物图片有多个可以用如下方式编写字典内容::

    {
        "701": {
            "type": "obj",
            "content": null,
            "opath": "/static/model/",
            "oname": "rocket.obj",
            "mpath": "/static/model/",
            "mname": "rocket.mtl",
            "visibleTag": 5
        },
        "801": {
            ...
        }
        ...
    }

下面我们来详细说说其中的一些配置项的含义´ ▽ ` )ﾉ

"type" —— 模型类型
^^^^^^^^^^^^^^^^^^^^^^^

目前有如下可选值:

* cube 立方体
* plane 平面
* sphere 球面
* cylinder 圆柱
* torus 圆环
* obj 第三方模型文件

"content" —— 模型内容
^^^^^^^^^^^^^^^^^^^^^^^^^^

一般情况设定为 ``null`` 。

"opath" —— 模型 obj 文件的目录路径
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

如果 ``"type"`` 的值为 ``"obj"`` 那么你才需要设置该属性。\
值得注意的是该目录路径应该设置在默认生成的 ``./static`` 目录下。

"oname" —— 模型 obj 文件的文件名
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

你需要载入的 obj 文件的文件名，注意带上扩展名。

"mpath" —— 模型 mtl 文件的目录路径
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

如果 ``"type"`` 的值为 ``"obj"`` ，且你的模型文件具有 mtl 文件，那么你才需要设置该属性。\
值得注意的是该目录路径应该设置在默认生成的 ``./static`` 目录下。

"mname" —— 模型 mtl 文件的文件名
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

你需要载入的 mtl 文件的文件名，注意带上扩展名。

"visibleTag" —— 初始可视标识
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

一般默认是5或者5以上的整数

在 ``CONFIG`` 中指定你的字典文件
----------------------------------------

设置 ``dictionary_file`` 的值，指定你的字典文件，代码如下::

    # Configs.
    CONFIG = {
        ...

        'dictionary_file': './static/dictionary/dictionary.json',

        ...

好了，现在我们已经完成字典文件自定义操作了´ ▽ ` )ﾉ！！！
