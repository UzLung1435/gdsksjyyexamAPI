# 广东省考试教育院成绩查询API

### Token获取
  Url： https://aiexam-yun.pingan.com.cn/v1/auth/acctoken
  需要提供的数据： 
   - x-aep-oac-bsid: ********************************   
   - x-aep-request-id: ********7a1711eb92340123456789ab   
   - x-aep-user-id: ***********   
   - 数据样式 : application/json   
   - 方法：Get   
注意，这些只是示例。请不要用于真实的开发中。   

### 获取考试list
  Url： https://aiexam-yun.pingan.com.cn/v1/scorequery/get/score/query/list/type   
   - Headers中的数据：X-Jwt-Token: （用你上面的Token）    
   - 正文数据：{"data":{"page":"1","num_per_page":"10"},"info":"","request_id":"xxxxxxxe7a1711eb92340123456789ab"}   
   - 方法：POST   
   - 返回格式json，发送格式同上（均为application/json）。   

### 获取考试list中的详细信息
   Url：https://aiexam-yun.pingan.com.cn/v1/scorequery/get/score/query/list/type/加上上面返回的其中一个考试列表的code（exam_type_code)   
   - Headers中的数据：X-Jwt-Token: （用你上面的Token）   
   - 正文数据：{"data":{"page":"1","num_per_page":"100"},"info":"","request_id":"xxxxxxxe7a1711eb92340123456789ab"}   

### 获取考试成绩
注：这里有所不同，需要仿照上面详细信息中的格式来编写对应的json   
   Url： https://aiexam-yun.pingan.com.cn/v1/scorequery/query/score   
   - Headers中的数据：X-Jwt-Token: （用你上面的Token）   
   - 文本以JSON格式发送，包含data和info两个值。   
  示例：{"request_id":"xxxxxxe79c311eb92340123456789ab","info":{"plat":"aa","device":"ios"},"data":{"id_score_query":"70","input_param_value":["考生号","密码"]}}   

 解释：id_score_query是考试的id，在详细信息中有，甚至还有一个人的账号密码供调试用。input_param_value有时会有多项，记得看详细信息里面的示例，需要填什么里面都有。
