---
title: M0011_IvrjackUHF 组件
---

### M0011_IvrjackUHF 组件

* 支持平台: iOS7.0,Android4.0


#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**open**</font>: ���豸

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: ��ʼ���豸�����豸
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**close**</font>: �ر��豸

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**startScan**</font>: ��ʼɨ��

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: �����豸״̬�룬0��ʾ�ɹ�
- 说明: ɨ���豸��ǩ��ɨ�赽��ǩ�ᴥ��scan�¼�
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stopScan**</font>: ֹͣɨ��

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: �����豸״̬�룬0��ʾ�ɹ�
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**read**</font>: ��ȡ��ǩ����

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **epc** |<font color ='#808000'>**string**</font> |  | 是||��ǩ��ַ���磺'E2005114 59000020 0002A6DA'
  **area** |<font color ='#808000'>**number**</font> | 0 | 否|0|Ҫ��������ȡֵֻ������0�����EPC��1�����USER��2�����RFU��3�����TID��
  **address** |<font color ='#808000'>**string**</font> | 0 | 否|0|��ȡ��ݵ���ʼ��ַ
  **count** |<font color ='#808000'>**string**</font> | 1 | 否|1|��ȡ��ݵĳ��ȣ��� word Ϊ��λ��1word=2byte�����磺1 2�� 01 02��a b��0a 0b��1a ab �Ⱦ�Ϊ 1 �� word��2 �� word �� 11 2a ef 3d���Դ�����
  **password** |<font color ='#808000'>**string**</font> | 00000000 | 否|00000000|���ʿ��8λ���֣������δ������������00000000��
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: ����{��result��:��ȡ���}
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**result**</font>: 

- 返回值类型 : <font color ='#808000'>**Number**</font>
- 返回值描述: �豸����¼���0��ʾ�豸�򿪳ɹ�
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**scan**</font>: 

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: ����һ��ɨ�赽�ı�ǩ�б?{epc:'E2005114 59000020 0002A6DA'}
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


