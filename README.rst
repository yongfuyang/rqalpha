..  image:: https://raw.githubusercontent.com/ricequant/rqalpha/master/docs/source/_static/logo.jpg

===============================
RQAlpha
===============================

..  image:: https://img.shields.io/travis/ricequant/rqalpha/master.svg
    :target: https://travis-ci.org/ricequant/rqalpha/branches
    :alt: Build

..  image:: https://coveralls.io/repos/github/ricequant/rqalpha/badge.svg?branch=master
    :target: https://coveralls.io/github/ricequant/rqalpha?branch=master

..  image:: https://readthedocs.org/projects/rqalpha/badge/?version=stable
    :target: http://rqalpha.readthedocs.io/zh_CN/stable/?badge=stable
    :alt: Documentation Status

..  image:: https://img.shields.io/pypi/v/rqalpha.svg
    :target: https://pypi.python.org/pypi/rqalpha
    :alt: PyPI Version

..  image:: https://img.shields.io/pypi/l/rqalpha.svg
    :target: https://opensource.org/licenses/Apache-2.0
    :alt: License

..  image:: https://img.shields.io/pypi/pyversions/rqalpha.svg
    :target: https://pypi.python.org/pypi/rqalpha
    :alt: Python Version Support


RQAlpha 从数据获取、算法交易、回测引擎，实盘模拟，实盘交易到数据分析，为程序化交易者提供了全套解决方案。RQAlpha 具有灵活的配置方式，强大的扩展性，用户可以非常容易地定制专属于自己的程序化交易系统。

RQAlpha 所有的策略都可以直接在 `Ricequant`_ 上进行回测和实盘模拟，并且可以通过微信和邮件实时推送您的交易信号。

`Ricequant`_ 是一个开放的量化算法交易社区，为程序化交易者提供免费的回测和实盘模拟环境，并且会不间断举行实盘资金投入的量化比赛。

特点
============================

*   易于使用: RQAlpha让您集中于策略的开发，一行简单的命令就可以执行您的策略。
*   完善的文档: 您可以直接访问 `RQAlpha 文档`_ 或者 `Ricequant 文档`_ 来获取您需要的信息。
*   活跃的社区: 您可以通过访问 `Ricequant 社区`_ 获取和询问有关 RQAlpha 的一切问题，有很多优秀的童鞋会解答您的问题。
*   稳定的环境: 每天都有会大量的算法交易在 Ricequant 上运行，无论是 RQAlpha，还是数据，我们能会做到问题秒处理，秒解决。
*   灵活的配置: RQAlpha 提供了一系列的配置选项，用户可以通过简单的配置来构建适合自己的交易系统。
*   强大的扩展性: RQAlpha 定义了一系列的 Mod Hook 接口，开发者可以基于 Mod 的开发模式，扩展 RQAlpha，无论是做实时监控，还是归因分析，RQAlpha 都可以通过扩展来实现。

快速指引
============================

*   `RQAlpha 介绍`_
*   `安装指南`_
*   `10分钟学会 RQAlpha`_
*   `策略示例`_

RQAlpha API
============================

*   `参数配置`_ : 启动 RQAlpha 参数配置
*   `API`_ : RQAlpha API 文档

机构版
============================

..  image:: https://raw.githubusercontent.com/ricequant/rqalpha/master/docs/source/_static/rqalpha_plus.png

目前 RQAlpha 开源版仅开放了日级别的历史数据和日回测功能，如果您是机构用户，需要做算法交易亦或是量化研究，都可以联系我们的机构端产品销售获得机构端产品功能支持。「销售电话」：0755-33967716 「QQ」：4848371

机构端产品功能：

*   可以本地部署，使用pycharm、anaconda等工具做本地策略研发、模拟以及实盘交易，效率大大加强，本地管理自己的策略提高保密性
*   极速调取经过清洗处理的历史数据接口服务，包括了：400多项指标的财务数据，股票、期货、ETF、LOF、分级基金等等10年+的日和分钟、tick级别的历史数据以及每日更新，股票、期货的实时数据支持，指数以及构成，板块分类，股本、换手率、融资融券等，天猫等电商销量数据，公募基金数据，舆情、公告类
*   股票、期货的实盘交易订单管理系统以及实盘下单支持，从回测到实盘交易的一条龙系统以及服务支持
*   策略的管理以及实盘的收益、风险计算等
*   交易数据的保存以及提取分析
*   业绩分析和风险管理系统
*   技术支持及定制化开发

加入开发
============================

*   `如何贡献代码`_
*   `基本概念`_
*   `RQAlpha 基于 Mod 进行扩展`_

其他
============================

*   `FAQ`_
*   `History`_
*   `TODO`_

获取帮助
============================

关于RQAlpha的任何问题可以通过以下途径来获取帮助

*  查看 `FAQ`_ 页面找寻常见问题及解答
*  可以通过 `索引`_ 或者 `搜索`_ 来查找特定问题
*  在 `Github Issue`_ 中提交issue
*  RQAlpha 交流群「487188429」

Current Working
============================

我们的开发工作最后会汇总到 `develop 分支`_，完成测试后发布并合并到 `master 分支`_。

目前我们正在进行如下的开发工作，会在下一次release版本中提供相应功能的支持

*   规范 Event 的生成和相应逻辑, 使用 :code:`Event` object 来替换原来的 Enum
*   解决通过代码调用 :code:`update_bundle` 函数报错的问题
*   RQAlpha 提供基于当前Bar和下一个Bar的撮合引擎，但有一些业务场景下(比如跟单，仓位同步等)，策略下单只是一个信号，不需要进行撮合，希望能够按照下单价格直接成交，因此 RQAlpha 提供了这种业务场景的支持。只需要在启动策略的时候传入 `--signal` 即可。
*   标准化 broker 对接接口，规范实盘接口对接流程，新的实盘接口对接只需要按照统一的接口层规范即可实现。
*   基于 vnpy 完成CTP实盘交易接口的对接开发: 我们在 `rqalpha-mod-vnpy`_ 项目中以 Mod 的形式，通过vnpy 完成CTP的对接，具体的对接工作正在进行中，目前还不稳定，等待下一个版本的发布，会完全实现 RQAlpha 和 CTP 的全链路打通，届时您通过RQAlpha进行回测后的策略可以直接连接实盘进行交易。

.. _Github Issue: https://github.com/ricequant/rqalpha/issues
.. _Ricequant: https://www.ricequant.com/algorithms
.. _RQAlpha 文档: http://rqalpha.readthedocs.io/zh_CN/stable/
.. _Ricequant 文档: https://www.ricequant.com/api/python/chn
.. _Ricequant 社区: https://www.ricequant.com/community/category/all/
.. _FAQ: http://rqalpha.readthedocs.io/zh_CN/stable/faq.html
.. _索引: http://rqalpha.readthedocs.io/zh_CN/stable/genindex.html

.. _RQAlpha 介绍: http://rqalpha.readthedocs.io/zh_CN/stable/intro/overview.html
.. _安装指南: http://rqalpha.readthedocs.io/zh_CN/stable/intro/install.html
.. _10分钟学会 RQAlpha: http://rqalpha.readthedocs.io/zh_CN/stable/intro/tutorial.html
.. _策略示例: http://rqalpha.readthedocs.io/zh_CN/stable/intro/examples.html

.. _参数配置: http://rqalpha.readthedocs.io/zh_CN/stable/api/config.html
.. _API: http://rqalpha.readthedocs.io/zh_CN/stable/api/base_api.html

.. _如何贡献代码: http://rqalpha.readthedocs.io/zh_CN/stable/development/make_contribute.html
.. _基本概念: http://rqalpha.readthedocs.io/zh_CN/stable/development/basic_concept.html
.. _RQAlpha 基于 Mod 进行扩展: http://rqalpha.readthedocs.io/zh_CN/stable/development/mod.html
.. _History: http://rqalpha.readthedocs.io/zh_CN/stable/history.html
.. _TODO: http://rqalpha.readthedocs.io/zh_CN/stable/todo.html
.. _develop 分支: https://github.com/ricequant/rqalpha/tree/develop
.. _master 分支: https://github.com/ricequant/rqalpha
.. _rqalpha-mod-vnpy: https://github.com/ricequant/rqalpha-mod-vnpy