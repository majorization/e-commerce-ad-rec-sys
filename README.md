# e-commerce-ad-rec-sys
## 电商广告推荐系统
该项目数据基于阿里巴巴提供的一个淘宝展示广告点击率预估数据集Ali_Display_Ad_Click.  
数据集下载地址：https://tianchi.aliyun.com/dataset/dataDetail?dataId=56  
### 数据集介绍
- raw_sample.csv：随机抽取的114万用户8天内的广告展示/点击日志（2600万条记录），字段说明如下：  
(1) user_id：脱敏过的用户ID；  
(2) adgroup_id：脱敏过的广告单元ID；  
(3) time_stamp：时间戳；  
(4) pid：资源展示位置；  
(5) noclk：没有被点击；  
(6) clk：被点击  
- ad_feature.csv：涵盖了raw_sample.csv数据中的全部广告信息（约80万条），字段说明如下：  
(1) adgroup_id：脱敏过的广告单元ID；  
(2) cate_id：脱敏过的商品类别ID；  
(3) campaign_id：脱敏过的广告计划ID；  
(4) customer_id：脱敏过的广告主ID；  
(5) brand_id：脱敏过的品牌ID；  
(6) price：商品的价格  
- user_profile.csv：涵盖了raw_sample.csv数据中的全部用户的基本信息（约100多万用户），字段说明如下：  
(1) user_id：脱敏过的用户ID；  
(2) cms_segid：微信群ID；  
(3) cms_group_id：微信群组ID；  
(4) final_gender_code：性别，值为1是男，为2是女；  
(5) age_level：年龄层级（1、2、3、4）；  
(6) pvalue_level：消费档次；  
(7) shopping_level：购物的层级；  
(8) occupation：是否为大学生；  
(9) new_user_class_level：城市等级；  
- behavior_log.csv：涵盖了raw_sample.csv数据中的全部用户22天内的购物行为（共七亿条记录），字段说明如下：  
(1) user_id：脱敏过的用户ID；  
(2) time_stamp：时间戳；  
(3) btag：用户的行为类型，包括四种（浏览|pv、加入购物车|cart、喜欢|fav、购买|buy）；  
(4) cate_id：脱敏过的商品类别ID；  
(5) brand_id：脱敏过的品牌ID；  

### 数据存储
1.先在本地创建一个dataset文件夹，将数据下载到该文件夹下，打开terminal命令行终端，执行如下命令将数据存放到hdfs下：
```
# 先在hdfs创建该项目文件夹recsys，再将数据存放到该目录下
hadoop fs -mkdir /recsys
hadoop fs -put ./dataset /recsys
# 查看是否成功存储
hadoop fs -ls /recsys/dataset
```
