# tianchi_businessforecast
天池IJCAI-17 口碑商家客流量预测大赛
## 塞题目的
[此次赛题](https://tianchi.aliyun.com/competition/introduction.htm?spm=5176.100065.200879.4.5Q90ZO&raceId=231591)要求选手根据官方给出的历史数据
预测2000家商家在在未来14天（2016.11.01-2016.11.14）内各自每天（00:00:00-23:59:59）的客户流量。</br>
[比赛数据下载地址](http://yunpan.taobao.com/?redirect=/s/Bq35eEB4ew?spm=5176.100068.555.4.zogxYD)
## 比赛成绩
loss 0.09072917 排名/总参赛队伍 419/4058
## 代码说明
merge_generate生成merge_info.txt 其信息为每家商户历史每一天的客户流量</br>
train_generste根据merge_info.txt构建训练集生成train.txt</br>
test_generate构建未来14天每家商户与训练集相同结构的特征 生成test.txt</br>
train使用随机森林用train.txt训练模型,并用训练出的模型与test.txt生成预测结果prediction.csv</br>
prediction_generate检测预测结果是否完整,并将预测结果四舍五入为整数,最后生成final_prediction.csv</br>
