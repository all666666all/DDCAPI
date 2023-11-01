# API接口

## 注意事项
- 提交方式全部为Form表单
- 所有请求必须带auth_secret参数
- 正常请求速率最高5次/秒
- 返回格式统一为JSON格式
- 可查询字段类型:
  - 姓名
  - 身份证
  - 性别
  - 银行卡
  - 邮件地址
  - 密码
  - 各类用户名
  - 微博UID
  - 微信原始ID(WXID)

## General Search


### 默认查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/5500C1337F79BEC6.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | query | String | true | 任意查询内容   | 张雪 |





### 姓名-省市县查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/6825576C29BE17B3.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | province | String | true | 省市县   | 河南省郑州市 |





### 姓名-省市县-性别-年龄范围查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/477B937628A5555D.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | province | String | true | 省市县   | 河南省郑州市 |
  | sex | String | true | 性别   | 女 |
  | startAge | int | true | 开始年龄(大于)   | 18 |
  | endAge | int | true | 结束年龄(小于)   | 20 |
  > 开始年龄会自动大于开始年龄并小于结束年龄，如果需要包含开始年龄和结束年龄则需要手动为开始年龄-1并且结束年龄+1





### 姓名-省市县-性别查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/65B4A9BE43F2A8CB.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | province | String | true | 省市县   | 河南省郑州市 |
  | sex | String | true | 性别   | 女 |




### 姓名-省市县-年龄范围查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/A033EBC91A698419.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | province | String | true | 省市县   | 河南省郑州市 |
  | startAge | int | true | 开始年龄(大于)   | 18 |
  | endAge | int | true | 结束年龄(小于)   | 20 |
  > 开始年龄会自动大于开始年龄并小于结束年龄，如果需要包含开始年龄和结束年龄则需要手动为开始年龄-1并且结束年龄+1





### 模糊姓名查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/63028169E057AC78.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | wildcardName | String | true | 模糊姓名   | 张x雪 |




### 模糊姓名-性别-生日范围查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/D13F8553B30CBE01.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | wildcardName | String | true | 模糊姓名   | 张雪 |
  | sex | String | true | 性别   | 女 |
  | startBirthday | int | true | 开始出生日期(大于)   | 19000000 |
  | endBirthday | int | true | 结束出生日期(小于)   | 20011231 |




### 姓名-模糊身份证查询(该接口速度可能会很慢,取决于模糊身份证号码的参数量)
#### Request
- Method: **POST**
- URL:  ```/api/v1/09B219F8177F9B68.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | wildcardIDCard | String | true | 模糊身份证号   | 6101xx19920810xxxx |





### 姓名-精确身份证号后四位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/AF5F2A9EF703E427.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | end_four | String | true | 身份证号后四位   | 001X |





### 模糊姓名-模糊身份证号查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/AA3B29725AF2BFDF.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | wildcardName | String | true | 模糊姓名   | 张xx |
  | wildcardIDCard | String | true | 模糊身份证号   | 6101xx19920810xxxx |




---


## Name Mobile Search



### 姓名-手机号前3位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/A6CB1D9EA4BB29EA.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | mobilePrefix | String | true | 手机号前3位   | 136 |




### 姓名-手机号后4位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/448DA50144B70064.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | mobileSuffix | String | true | 手机号后4位   | 0024 |




### 模糊姓名-手机号前3位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/92E9244750001D39.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | wildcardName | String | true | 模糊姓名   | 张x雪 |
  | mobilePrefix | String | true | 手机号前3位   | 136 |




### 模糊姓名-手机号后4位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/12317AA0341AF956.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | wildcardName | String | true | 模糊姓名   | 张x雪 |
  | mobileSuffix | String | true | 手机号后4位   | 0024 |




### 姓名-模糊手机号前三位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/0F22A86FF729A059.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | wildcardMobilePrefix | String | true | 模糊手机号前3位   | 13x |




### 姓名-模糊手机号后四位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/3574EF7792D53B67.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | wildcardMobileSuffix | String | true | 模糊手机号后4位   | 0xx4 |




### 模糊姓名-模糊手机号前三位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/5AE30CBA83152548.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | wildcardName | String | true | 模糊姓名   | 张x雪 |
  | wildcardMobilePrefix | String | true | 模糊手机号前3位   | 13x |




### 模糊姓名-手机号后四位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/1DC25E0155A2CC12.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | wildcardName | String | true | 模糊姓名   | 张x雪 |
  | wildcardMobileSuffix | String | true | 模糊手机号后4位   | 0xx4 |




### 姓名-手机号前三位-手机号后四位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/81D6124D13B31606.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | mobilePrefix | String | true | 手机号前3位   | 136 |
  | mobileSuffix | String | true | 手机号后4位   | 0024 |




### 姓名-手机号前三位-模糊手机号后四位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/DADD36A5EFA9C351.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | mobilePrefix | String | true | 手机号前3位   | 136 |
  | wildcardMobileSuffix | String | true | 模糊手机号后4位   | 0xx4 |




### 姓名-模糊手机号前三位-模糊手机号后四位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/2BC85B614C15DBBB.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | name | String | true | 精确姓名   | 张雪 |
  | wildcardMobilePrefix | String | true | 模糊手机号前3位   | 13x |
  | wildcardMobileSuffix | String | true | 模糊手机号后4位   | 0xx4 |




### 模糊姓名-模糊手机号前三位-模糊手机号后四位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/EB909B2B51F9B8ED.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | wildcardName | String | true | 模糊姓名   | 张x雪 |
  | wildcardMobilePrefix | String | true | 模糊手机号前3位   | 13x |
  | wildcardMobileSuffix | String | true | 模糊手机号后4位   | 0xx4 |




### 模糊姓名-模糊手机号前三位-手机号后四位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/3AE3DB8E4741A0D3.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | wildcardName | String | true | 模糊姓名   | 张x雪 |
  | wildcardMobilePrefix | String | true | 模糊手机号前3位   | 13x |
  | mobileSuffix | String | true | 手机号后4位   | 0024 |




### 模糊姓名-手机号前三位-手机号后四位查询
#### Request
- Method: **POST**
- URL:  ```/api/v1/96F2E894538019AD.php```
- POST Form
  | 请求参数 | 类型 | 必填 | 参数说明 | 示例 |
  | :---: | :---: | :---: | :---: | :---: |
  | auth_secret | String | true | 身份验证 | Your Secret Key |
  | wildcardName | String | true | 模糊姓名   | 张x雪 |
  | mobilePrefix | String | true | 手机号前3位   | 136 |
  | mobileSuffix | String | true | 手机号后4位   | 0024 |



