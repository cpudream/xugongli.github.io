---
layout:     post
title:      "pandas read_excel IndexError: list index out of range ����취 "
subtitle:   "pandas_read_excel_error_process"
date:       2019-07-15 12:36:05
author:     "soaringsoul"
header-img: "img/posts/default_post.jpg"
catalog: true
tags:
    - ���ݴ���
---





�����ʱ��ͬ�¸��ҷ�����֮ǰд�����п���ˮ����ʶ�������������д����ҿ����´�����ʾ��

```IndexError: list index out of range```

���п���ˮ����ʶ���������� ��Ϊ���������������е����Ŷ�������������һ�����ݲ������Ʒ���������汾��һ��������·����Աʹ�ã�һ����������Ϸ������ƽ̨ʹ�á�

��� ���µķ����Աʹ�õ��ǰ�ͨ����ȡ����excel�ļ�����ʽ����ȡ�ͻ��ĸ�����Ϣ�����п���ˮ���ݡ�����������д�����Ǹ�������·����Աʹ�õİ汾��



��debug���£�������pandas ��read_excelʱ�޷���ȡ��excel�ļ���sheet,�����ڳ����������⡣

ͨ��**Stack Overflow** ���������������Ҳδ�ҵ��𰸡�ֻ���Լ�����ˣ�

��ʹ���ų��������ǲ��Ǵ�����bug:��ͨ�����������excel�ļ��е����ݸ��Ƶ��½�excel�ļ���ȥ����������������������С�



�Ǿ������excel�ļ�����������ˣ��۲�̽����Σ��޹���

������Ϊ������ʽ��ʱ�������������ڣ�

![pandas_read_excel_errror_process1](/img/posts/pandas_read_excel_errror_process1.png)



ԭ������޷���ȡsheet��excel�ļ�����Ϊ`Stirct Open XML ���ӱ��(*.xlsx)`��pandas�޷�ֱ�Ӷ�ȡ����excel�ļ����������Ϊһ���.xlsx�ļ����ɡ�

![pandas_read_excel_errror_process2](/img/posts/pandas_read_excel_errror_process2.png)