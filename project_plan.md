
## 一、绝地求生（吃鸡）数据提要

数据来源：https://www.kaggle.com/lazyjustin/pubgplayerstats/data

### 1. 数据概述：
数据集内共包含87898名玩家的数据，共有152列特征，前两列为玩家用户名和游戏id，后150列为对战数据。
对战数据按照标签分为三大类：solo（单人赛）、duo（双人赛）、squad（小队赛），每一类包含50个统计项：

| 特征标签 | 含义 |
|------------- | -------------|
| solo_KillDeathRatio | 击杀死亡比 |
| solo_WinRatio | 胜率 |
| solo_TimeSurvived | 存活时间 |
| solo_RoundsPlayed	| 游戏局数 |
| solo_Wins	| 胜利局数 |
| solo_WinTop10Ratio | 胜利占前十局数比 |
| solo_Top10s | 前十局数 |
| solo_Top10Ratio | 前十占比 |
| solo_Losses | 失败局数 |
| solo_Rating | 评分 |
| solo_BestRating | 最高评分 |
| solo_DamagePg | 每局伤害 |
| solo_HeadshotKillsPg | 每局爆头 |
| solo_HealsPg | 每局治疗 |
| solo_KillsPg | 每局击杀 |
| solo_MoveDistancePg | 每局移动距离 |
| solo_RevivesPg | 每局复活次数 |
| solo_RoadKillsPg | 每局开车击杀 |
| solo_TeamKillsPg | 每局团队击杀 |
| solo_TimeSurvivedPg | 每局存活时间 |
| solo_Top10sPg | 每局前十次数 |
| solo_Kills | 击杀人数 |
| solo_Assists | 助攻次数 |
| solo_Suicides | 自杀次数 |
| solo_TeamKills | 团队击杀数 |
| solo_HeadshotKills | 爆头次数 |
| solo_HeadshotKillRatio | 爆头击杀占比 |
| solo_VehicleDestroys | 击毁车辆数 |
| solo_RoadKills | 开车击杀数 |
| solo_DailyKills | 每日击杀 |
| solo_WeeklyKills | 每周击杀 |
| solo_RoundMostKills | 单局最高击杀数 |
| solo_MaxKillStreaks | 最高连杀数 |
| solo_WeaponAcquired | 获得武器数 |
| solo_Days | 游戏天数 |
| solo_LongestTimeSurvived | 最长存活时间 |
| solo_MostSurvivalTime | 最长存活时间 |
| solo_AvgSurvivalTime | 平均存活时间 |
| solo_WinPoints | 胜利点数 |
| solo_WalkDistance | 步行距离 |
| solo_RideDistance | 驾车行驶距离 |
| solo_MoveDistance | 移动距离 |
| solo_AvgWalkDistance | 平均步行距离 |
| solo_AvgRideDistance | 平均驾车行驶距离 |
| solo_LongestKill | 最远击杀距离 |
| solo_Heals | 治疗量 |
| solo_Revives | 复活次数 |
| solo_Boosts | 状态道具使用次数 |
| solo_DamageDealt | 总造成伤害 |
| solo_DBNOs | 被击倒但未被淘汰次数 |

注：
* 1. Top10sPG和Top10Ratio是表现同一特征的不同形式，一个是百分数一个是小数。
 2. LongestTimeSurvived和MostSurvivalTime是同一个数据特征，重复出现。

较为遗憾的一点是数据里全部的WeaponAcquired均为0，这一栏的数据缺失或许会对我们全面分析影响吃鸡胜率的因素和挖掘最佳策略构成一定的影响。

### 2. 针对数据提出有待解决的问题：

数据上传者提出了几个颇具启发性的问题：

* a. Visualizations of player skill vs. specific strategies<br>
 玩家水平和特定策略的可视化<br>
* b. Unsupervised clustering of players based on strategy (for matchmaking or team building)<br>
 依据策略对玩家进行无监督聚类<br>
* c. Prediction of features based on player skill and/or strategies<br>
 对基于玩家技术与（或）策略的特征的预测<br>

可以看出上述问题集中关注玩家策略与玩家水平这两大因素。在这方面，我们还可以基于这些问题提出更具体的研究内容：

* 1. 依照吃鸡率、击杀人数、前十率等特征对玩家水平进行分类，并探究其他特征对吃鸡率的影响，比如神枪手和超能苟谁更容易吃鸡。

 2. 通过对玩家进行聚类，探究同一玩家技战术特点在不同模式中的发挥有何差异，比如solo大神是否一定也是团队赛神级队友。

 3. 探究载具在游戏当中的作用，作为飙车老司机是否会对前十率和吃鸡率产生正面影响。

 4. 模拟预测最佳吃鸡策略。




## 二、Grammar and Online Product Reviews数据提要

数据来源：https://www.kaggle.com/datafiniti/grammar-and-online-product-reviews/data

### 1.数据概述：

数据一共包含71044个样本，共25个特征，统计1000个不同产品在电子商务平台中的用户评论文本和评级数据。

| 特征标签 | 含义 |
| -------  | ---- |
| id | 产品编号 |
| brand | 品牌名称 |
| categories | 产品类别 |
| dateAdded | 上架日期 |
| dateUpdated | 更新日期 |
| ean | EAN 条码 |
| keys | 销售关键词 |
| manufacturer | 生产商 |
| manufacturerNumber | 生产商编号 |
| name | 产品名称 |
| reviews.date | 评论日期 |
| reviews.dateAdded | 评论添加日期 |
| reviews.dateSeen | 评论浏览日期 |
| reviews.didPurchase | 是否购买 |
| reviews.doRecommend | 是否推荐 |
| reviews.id | 买家用户id |
| reviews.numHelpful | 认为评论有帮助人数 |
| reviews.rating | 评论评分 |
| reviews.sourceURLs | 评论链接 |
| reviews.text | 评论正文 |
| reviews.title | 评论标题 |
| reviews.userCity | 用户城市 |
| reviews.userProvince | 用户省份 |
| reviews.username | 用户名称 |
| upc | UPC条码 |

其中reviews.didPurchase和review.doRecommend两条数据type均为Boolean，且均存在部分缺失。

### 2.针对数据提出有待解决的问题：

数据上传者在其发布数据的页面提出了几个有参考价值的问题，如下所示：

* Do reviewers use punctuation correctly?<br>
 评论者是否正确使用标点符号？
* Does the number of spelling errors differ by rating?<br>
 拼写错误的数量是否与评价等级相关？
* What is the distribution of star ratings across products?<br>
 产品之间星级评价的分布是什么样的？
* How does review length differ by rating?<br>
 评论长度和评价等级是否相关？
* How long is the typical review?<br>
 一般的评论长度为多少？
* What is the frequency of words with spelling errors by rating?<br>
 依评价等级划分，拼写错误频率如何？
* What is the number of reviews that don’t end sentences with punctuation?<br>
 有多少评论在句尾不加标点符号？
* What is the proportion of reviews with spelling errors?<br>
 有拼写错误的评论占比多少？

这些问题集中关注点在于评论的语法。这符合题目“Grammar and Online Product Reviews”所讨论的方向。基于上述问题的启发，我们可以进一步得出一些值得研究和思考的方面：

* 1. 如何根据评论内容填补“是否购买”和“是否推荐”两栏中的缺失数据。
 2. 根据不同评价等级在评论当中所展现的不同特征单词，比如出现“good”很可能代表用户对产品评价较高，而出现“waste of money”则很可能反应用户对产品的不满，从而对上述缺失数据的填补起到帮助作用，或在新的评论数据引入的时候根据特定单词来推测产品本身的质量。
 3. 不同产品类别对应的目标买家人群也会有所差别，所以不但可以分析评论长度和语法错误与产品质量的相关性，更可以拓展讨论其与产品类别的相关性。
 4. 通过分析同一厂商的不同产品和同一类别不同产品所获好评率的差异，预测之前用户的评论对后续用户购买产品以及评论是否会产生连带影响，比如一个产品前五个人都说不好，很可能第六个人的评论也是差评，即“惯性效应”。
 5. 在好评率较高的产品中出现差评和在差评率较高的产品中出现好评时，是否可能通过检查语法的准确率和用词的一致性来鉴别存在“水军”评论的可能性。

### 3. 挑选有用信息：

对数据做初步人为判断，断言id，date，keys，条码，URL等信息为无效信息，对分析结果的影响可以忽略不计。而用户id，所在地区等信息虽然看似无关，但在一定程度上可能会反应用户的文化和受教育水平，因而不应该完全忽视，但由于我们断言样本趋向于独立同分布，可能这些因素对于分析结果的影响未必会很大，因此这部分信息也可以放到次要的位置去考虑。<br>
而我们研究聚焦点应该主要放在brand，categories，manufacturer，name，reviews.didPurchase，reviews.doRecommend，reviews.rating，reviews.text，reviews.title这几个特征上面。另外注意reviews.numHelpful可能表示虽然一些用户没有自己发表评论，但是赞同了其他用户的评论，所以很可能做出了与发表评论用户相近的购买行为，因而需要考虑为该特征添加一些权重。

### 4.对于基础问题的进一步讨论：

我们有待解决和突破的关键点在于：

1. 如何实现计算机对于“关键词”的自动筛选，例如判断“good”代表好，“waste”代表差<br>
 可能出现的欠拟合：例如出现“not”，”bad”时均判断为差，从而也把“not bad”误判断为差。<br>
 可能出现的过拟合：例如误把一些常见代词、连词比如“it”、“this”、“and”作为判断产品好坏的依据。

2. 如何实现计算机对于“拼写错误”和“标点符号缺失”的判断<br>
 “拼写错误”方面：<br>
 例如：“good”为正确，而“goood”则为错误。<br>
 * 可能出现的欠拟合：例如多次出现类似的拼写错误的时候，将错误误判为正确写法。<br>
 * 可能出现的过拟合：例如当评论中出现“god”作为惊叹用语出现的时候，误将其判断为“good”的错误拼写，从而导致将比如“God, it sucks.”之类的评论误判为一条产生拼写错误的好评。
 
 “标点符号缺失”方面：<br>
 例如：“Terrible”为缺失标点符号，但“Terrible!”则不缺。<br>
 * 可能出现的欠拟合：例如无法很好的分割两个短句，而将其误判为一个长句<br>
 * 可能出现的过拟合：例如由于大量评论均缺失标点符号，而误判断此处不加标点才是正确的语法。<br>
3. （有待进一步补充）


## 三、H-1B Visa Petitions 2011-2016数据提要

（H-1B签证申请2011-2016）

数据来源：https://www.kaggle.com/nsharan/h-1b-visa

### 1. Data Description (CSV)数据概述：
（1）1048575 records<br>
（2）7 Characteristics: （共有1048575个样本，以及7个特征。）<br>

1) Case status: Status associated with the last significant event or decision. <br>
Valid values include "Certified", "Certified-Withdrawn", "Denied” and "Withdrawn".<br>
（签证状态）<br>
2) employer name: Name of employer submitting labor condition application.<br>
（雇主名称）<br>
3) SOC_NAME: Occupational name associated with the SOC_CODE<br>
（根据SOC（标准职业分类）所确定的职业名称）<br>
4) job title: Title of the job<br>
（职务名称）<br>
5) FULL_TIME_POSITION: Y = Full Time Position; N = Part Time Position<br>
（是否全职）<br>
6) prevailing wage: Prevailing Wage for the job being requested for temporary labor condition.<br>
（现行工资）<br>
7) year filed<br>
（申请年份）<br>
8) worksite coordinates: WORKSITE_CITY, WORKSITE_STATE, longitude, latitude<br>
（工作地点）<br>

### 2. Question问题提出:

* 1. Variation trend for all jobs. For example, is the number of petitions with Data Engineer job title increasing over time?<br>
（预测工作变化趋势，例如申请数据工程师职务的人数是否随着时间增长。）<br>

 2. Jobs distribution in different locations/industries. For example, which part of the US has the most Hardware Engineer jobs? Which industry has the most number of Data Scientist positions?<br>
 （获取不同地区或不同行业的职务分布，例如美国什么地区拥有最多的硬件工程师岗位，什么行业对数据科学家的需求最多。）<br>

 3. Which employers file the most petitions each year?<br>
 （每年哪些雇主企业提交最多签证申请？）<br>

 4. Correlation between the case status and other characteristics. What kind of petition is more likely to be certified/certified-withdrawn/denied/withdrawn?<br>
 （签证状态与其他特征之间的相关性。什么样的签证更可能通过认证/认证撤回/被拒绝/被撤回？）


*-by Wang Junpeng & Deng Shujian *<br>
*- May 20th, 2018 *
