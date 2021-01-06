有需要的加qq：2651626675

     基于JSP的班级综合管理系统

摘 要

随着学校规模的不断扩大，学生数量急剧增加，有关学生的各种信息也成倍增长。面对如此庞大的信息量，开发班级综合管理系统来提高学生管理工作的效率就成为必然。通过该系统，可以做到信息的规范管理、科学统计和快速查询，从而减少管理方面的工作量。

本文主要介绍了班级综合管理系统的主要任务，阐述了开发该系统用到的关键技术，如采用B/S结构，使用JSP编程、利用SQLServer2000建立数据库、采用HTML，JavaScript等编程技术。

本系统是采用B/S模式进行开发的，系统的用户权限有两种：学生和系统管理员，不同权限用户登入到不同的操作界面。该系统主要由学籍维护、选课管理、成绩查询等功能模块组成，本文具体介绍了各功能模块所包含的小模块的功能，学籍维护模块主要是对学生的基本信息进行添加、查询、修改、删除；选课管理模块主要是对选修的课程进行添加、删除、统计选修人数，以及学生进行选课和更改选课；成绩查询模块主要是对必修课进行添加、删除、录入成绩，以及学生进行查询成绩等功能。

关键字：班级综合管理，B/S，JSP，Script，SQLServer2000。





目 录

摘 要... I

引 言... 1

第一章  绪论... 2

1.1 选题的背景和意义... 2

1.2 国内外研究现状及发展趋势... 2

1.3 本课题研究内容... 2

1.4 本课题研究的目标及主要特色... 3

第二章  系统设计使用技术介绍... 4

2.1 JSP（Java Server Pages）和Java Bean技术介绍... 4

2.1.1 JSP概述... 4

2.1.2 JSP工作原理... 4

2.1.3  JavaBean技术介绍... 4

2.2 B/S体系结构介绍... 5

2.3 JavaScrit技术介绍... 6

2.4 SQL Server 2000 数据库... 6

2.4.1 数据库介绍... 6

2.4.2 ODBC数据访问接口... 7

2.4.3 JDBC数据访问接口... 7

第三章  系统设计... 9

3.1 需求分析... 9

3.1.1 运行环境... 9

3.2 系统总体设计... 9

3.2.1 系统目标设计... 9

3.2.2 系统设计思想... 9

3.2.3 系统功能描述... 10

3.2.4 系统用例图... 12

3.2.5 系统UML活动图... 13

第四章  数据库设计... 14

4.1 总体表设计... 14

4.2 数据库表的结构... 14

4.3 实体及ER图... 16

4.3.1 实体介绍... 16

4.3.2 实体的ER图以及各实体之间联系的ER图... 16

4.4 数据库表的关系图... 19

4.5 数据库表的视图... 20

4.6 数据库连接... 20

第五章  系统具体实现... 23

5.1 登入界面... 23

5.2 学生界面... 25

5.3 学生界面功能实现... 26

5.3.1 查看公告页面... 26



5.3.2 学生修改密码页面... 26

5.3.3 学生学籍维护页面... 28

5.3.4 成绩查询... 30

5.3.5 查看学修课表并进行选修... 30

5.4 管理员界面... 32

5.5 管理员界面功能实现... 33

5.5.1 查看学生基本信息... 33

5.5.2 添加新学生和选修课... 35

5.5.3 查看学修课表和必修课表... 36

5.5.4 查看学生选课情况和学生成绩... 37

5.5.5 添加必修课表和学生成绩... 40

第六章  全文总结... 44

致 谢... 45

参考文献... 46

引 言

班级综合管理系统(SMIS)是大学信息管理系统建设的重要组成部分，是提高教学管理的质量和效益乃至建设知名高水平大学的关键环节。学生信息处理的电脑化、网络化，也是实现学校管理现代化和信息化的重要内容。

班级综合管理系统的内容对于学校的决策者和管理者来说都至关重要, 所以班级综合管理系统应该能够为用户提供充足的信息和快捷的查询手段。但一直以来人们使用传统人工的方式管理文件档案，这种管理方式存在着许多缺点,如:效率低、保密性差,另外时间一长,将产生大量的文件和数据,这对于查找、更新和维护都带来了不少的困难。

随着科学技术的不断提高,计算机科学日渐成熟,其强大的功能已为人们深刻认识,它已进入人类社会的各个领域并发挥着越来越重要的作用。

作为计算机应用的一部分,使用计算机对学生信息进行管理,具有手工管理所无法比拟的优点。例如:检索迅速、查找方便、可靠性高、存储量大、保密性好、寿命长、成本低等。这些优点能够极大地提高学生档案管理的效率,也是进行科学化、正规化管理，与世界接轨的重要条件。

随着进入二十一世纪，计算机技术迅速向着网络化、集成化方向发展。传统的单机版应用软件正在逐渐退出舞台，取而代之的是支持网络、支持多种数据信息（多媒体）的新一代网络版应用软件，而目前网络版软件中似乎存在着两种不同的趋势，一种是称为客户端——服务器的C/S结构应用系统，另一种是称为浏览器——服务器的B/S结构应用系统。而后者的特点是在客户端直接采用了功能强大的浏览器软件作为界面，其优点在于软件开发效率高，客户端不受操作平台的限制、也不受地域的限制，网络传输量少，即适用于局域网，更适用于Internet，而且投资小、见效快，用户可以不必进行服务器方面的投资，而是去租用，甚至是免费使用ISP的服务器资源，因而受到越来越多中小型单位的青睐。

因此，开发一套采用B/S结构的班级综合管理系统就成为必要的事情。本系统正是采用B/S结构开发的，该系统主要由学籍维护、选课管理、成绩查询等功能模块组成，实现学生基本信息管理、学生选修课程管理以及学生成绩查询管理等。本文将在后面一一加以详细阐述。

<img src="https://img-blog.csdnimg.cn/20210106163117516.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMxMjkzNTc1,size_16,color_FFFFFF,t_70">
<img src="https://img-blog.csdnimg.cn/20210106163117479.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMxMjkzNTc1,size_16,color_FFFFFF,t_70">
<img src="https://img-blog.csdnimg.cn/20210106163117190.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMxMjkzNTc1,size_16,color_FFFFFF,t_70">
<img src="https://img-blog.csdnimg.cn/20210106163117396.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMxMjkzNTc1,size_16,color_FFFFFF,t_70">
<img src="https://img-blog.csdnimg.cn/20210106163117230.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMxMjkzNTc1,size_16,color_FFFFFF,t_70">
<img src="https://img-blog.csdnimg.cn/20210106163117563.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMxMjkzNTc1,size_16,color_FFFFFF,t_70">
<img src="https://img-blog.csdnimg.cn/20210106163117474.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMxMjkzNTc1,size_16,color_FFFFFF,t_70">
