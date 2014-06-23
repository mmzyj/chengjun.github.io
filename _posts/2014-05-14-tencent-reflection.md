---
layout: post
title: "传播驱动的社交网络数据挖掘"
date: 2014-05-14 09:41
comments: true
categories: 
- blog
tags:
- 传播
- 反思
---


本文试图从传播的角度思考中国社交网站的发展，限于作者的认识，定然有很多不成熟的地方。但是作为一个开端，这是有益的尝试。

#### 社交网站的需求

社交网站基于关系的类型可以分为熟人关系和陌生人关系。人人网、脸书、QQ、微信基本上都是针对熟人关系的，这种关系多数存在线下的关联（似乎至少在两步的距离之内）；陌生人关系则相对宽泛，如陌陌。除了基于社交关系的网站之外，还有基于兴趣和信息的网站，如微博和豆瓣。而如秘密等手机应用，则试图构建熟人之间的陌生关系。

社交网站自身的需求当然是庞大的用户数量、活跃的用户规模、消费的用户行为。究其本质，社交网站主要依赖广告和游戏收入。互联网思维的强悍之处就在于第一步是赔本赚吆喝：扩大用户规模。基于庞大的用户规模，互联网广告就会注入，为网站提供资金源。另外一个方面，网站本身也需要自谋生路，游戏被认为是获取收益的关键。当然，游戏本身也可以搭载广告。

基于机器学习思路建立起来的数据挖掘系统存在一个缺陷：对数据的挖掘并不深入。尤其是在数据本身较为复杂且包含着噪音的情况下。机器学习最重要的一步工作是特征的选取。一个有经验的工程师带着两三个年轻人两到三年就可以把一个项目的主要特征挖得差不多。如何进一步深入，往往是一个问题。大数据时代的到来和深度学习的提出，给出了一种可能的解答。但是这种解答本身却因学习深度的增加而存在着难以解释的困境。这种问题对于社交网站而言，表现尤为明显，所以今天的脸书、人人网、QQ等面临着这个挑战。怎么解决这个问题？

#### 何为传播的角度

社交行为本身而言，是一种传播。从传播网络和传播过程的角度理解社交网络和社交行为可以为社交网站所面临的困境提供一些答案。这就是把传播的角度引入社交网站数据挖掘的原因。那么何为传播的角度？传播驱动的社交网站数据挖掘主要关注什么？有能够提供什么样的结果？我们从社交网络用户的关系的复杂性 （时间、地理、属性）开始谈起。

![](https://farm3.staticflickr.com/2922/14182501955_724dba9e82_o.png)

图：邓巴数与关系的层次  /来源： [知乎](http://www.zhihu.com/question/20132322)

是关系就有强有弱，线上关系也是一样。强的关系是相对较少的，弱的关系是相对较多的。强关系的社会意义是情感性的、生活方式的捆绑（bonding），因而被认为有着非常重要的作用。弱关系则具有传递信息的功能，因而反而对个人的很多选择具有重要影响。弱关系之所以具有传递有效信息的功能就是因为你的弱关系多与你处于不同的社会群体和社交圈子里，大家所处的环境不同，接触到的人和事不同，因而在信息共享方面具有很强的互补性。古语云：兼听则明偏信则暗。其实不是说数量，而是说要听取不同群体的意见。你的弱关系往往发挥着链接不同的群体的作用，这种作用又被称为桥接（bridging）的功能。

很重要的一点是社交关系的流动，被封存起来的关系因为时间和地理的隔离而逐渐丧失了影响力。Dr.Thinker很明确地指出了这一点。如下图所示，我们有儿时的玩伴，中学同学、大学同学、工作同事、自己的家人。这些关系在我们人生中的每一个阶段而有所不同。社交网络帮助人们以较低的成本更好地去维持过去时空里的关系 （maintaining relationships）。因而，现实就是沉淀在社交网络里的关系具有时空的异质性。不同的人的影响权重并不相同。

![](https://farm8.staticflickr.com/7336/14179201871_42eeac5e9a_o.png)

图：社交网络的流动  /来源： [知乎](http://www.zhihu.com/question/20132322)

社交圈子（social circle）是过去几年里比较火的概念。有一本书就叫《小圈子大社交：利用圈子引爆流行》，英文名为`Grouped: How small groups of friends are the key to influence on the social web` 。作者是Paul Adams，他先后供职于谷歌和脸书。据说在谷歌的时候，他就写完了一本书，书名叫《Social Circles: How offline relationships influence online behavior and what it means for design and marketing 》。因为谷歌的限制，这本书从未出版，后来其主要的思想应用到了google plus 的设计中。由书名可以知道这本书的核心是要实现关系从线下到线上的迁移，以及如何利用这种真实关系在虚拟空间的重现来设计网站和营销活动。
 
从时间的角度还可以对关系进行进一步的划分：一周联系一次，一个月联系一次，几个月联系一次，一年联系一次，数年不联系的人。这从更深入的细节上揭露了网络的特点。有时候，不联系的关系也许是线下的非常重要的关系，但是并没有实现这种关系向线上的迁移。基于这种认识，Paul给那种不经常联系的关系称之为暂时性关系（temporal relationship）。

![](http://www.thinkoutsidein.com/blog/wp-content/uploads/2012/01/Screen-Shot-2012-01-28-at-10.18.50-AM.png)
图：社会网络结构 /来源： [Paul Adams](http://www.thinkoutsidein.com/blog/2012/01/grouped-chapter2/)

社区是现实社会的基本单位。在进行网络研究的时候，也可以进行类似的社区划分（community detection，也称为社团划分）。

![](https://farm3.staticflickr.com/2925/14179867392_2299e4a9a3_o.png)
图：社交圈子  /来源： [知乎](http://www.zhihu.com/question/20132322)

当然了，这种理解还是不够深入，因为它依然停留在对于中心个体给朋友贴标签的层面上。Paul Adams 所设想的景象如下图所示，我们不仅仅要能抓住个人中心网络当中的圈子，还要能够把握朋友的圈子。在一个slides当中，Paul更加详细地展现了自己的想法，见[How Your Customers' Social Circles Influence What They Buy, What They Do and Where They Go](http://www.slideshare.net/padday/how-your-customers-social-circles-influence-what-they-buy-what-they-do-and-where-they-go) 

![](http://www.thinkoutsidein.com/blog/wp-content/uploads/2011/05/grouped087.png)
图：深入到朋友的社交圈子？  /来源： [Paul Adams](http://www.thinkoutsidein.com/blog/2011/05/small-connected-groups/)

正是因为网络中个体和节点的复杂性，Paul认为社交网站当务之急是需要围绕人来重新建设社交网络（rebuild the social web around people）！这样做的好处是：便于人们以更低成本迁移线下关系到线上网络；同时，可以剔除噪音，减小计算复杂性。相反，如果无法剖析出哪些关系是有效关系，哪些关系是沉睡的关系，对于所有的计算使用相同的权重，就会使我们陷入纯粹计算的层层迷雾。以下，我将试图谈一些社交网站最关心的业务，帮助我们来思考`传播驱动的数据挖掘`。

#### 产品推荐
要扩大用户的规模，第一步当然是产品的推广。说到产品的推荐，人们的第一印象是推销员、促销活动、广告等。社交网站的推广也有类似的道理。如何还没有使用某一款产品的人使用它呢？社交网络有自己的回答：人际作用（interpersonal effect），也可以表达为社交影响（social influence）。当然了，创新者总会很早就采纳创新，并将产品介绍给周围的人。基于引爆点（tipping point）的理论，一旦系统中有足够的人使用是，该创新就可以迅速扩散。网络的作用是具有传染性，入网的用户会将网外的用户拉进来，并产生滚雪球的作用。这是社交特性本身的特点。可以基于ABX模型来解释，AB是两个人，B喜欢X产品，那么A喜欢X产品的概率就很高。网络偏爱具有传递性的三角形。

但是在实际的产品推荐的时候，需要考虑的事情很多。尤其针对社交网络而言，因为用户已经有了线下的社交系统，为什么还要使用线上的系统联系呢？这个时候要考虑用户迁移（由线下到线上）的成本，并尽可能降低这种成本。最简单的方法就是将新产品嫁接在一个强大的传播渠道上。什么传播渠道具有如此强的搭载能力？传播渠道要具有一些特点，例如它必须可以对应到每一个人。每一个人都强烈的依赖于它。显然，它是个体化的媒介产品。其次它必须积累了你的其它社交关系。有哪些这种记录了你的社交关系的个人媒介呢？它就是电子邮箱和手机号码。每个电子邮箱都记录了你的联系人，同样是手机的电话薄。有了这些东西，病毒传播就可以展开了。现在微博的发展非常好，购物网站纷纷寻求与其合作。为什么呢？因为微博同样记录了人的社交关系。

linkedin发展强烈的依赖于获取电子邮箱中的通讯录，并向通讯录中的朋友发送加入邀请。事实上，很多其它网站也采用这种方式。

**App的推荐**

多数社交网站并无掌控手机App入口的能力。手机互联网的发展，催生了手机App的应用市场。App使得入口变得炙手可热。苹果手机以一种独占的形式，试图控制所有的应用安装入口。这给那些试图进一步做大的社交网站门户提出了挑战。例如，以往在腾讯游戏网站可以轻易安装的各种游戏，在手机上只能通过苹果的APP STORE安装。一些互联网公司只好试图发展超级APP, 即那些使用用户很多的APP，例如微信的手机APP和百度地图的手机App。App是搭载广告的良好载体。事实上，也许只有少数小众App才对用户收费。有实力有野心的超级APP是绝对不会牺牲用户数量来赚取那有限的收入的，他们的目标是广告商。

于是，基于超级APP推广App也成为一个市场。本文关注社交网络（social web），主要想看如何从传播的角度来理解app在社会网络的扩散。通过社交网络推广App的的基本假设是线上的人际作用一样具有线下的人际作用所拥有的影响力。但是，这也许只是幻想：并不是说有了网络的形式就一定会有社交影响。因为社交影响基于有效地传播行为，而不仅仅是几年前就存在而并不活跃的朋友关系。问题就转变为激活线上人际关系！或者至少是找到那些被激活的人去传播。如何激活线上的人际关系？要**引入局部信息**。使得局部网络的信息可见化。

不要太天真，因为可见化局部信息违背了用户的隐私。用户也许并不想让他的朋友的朋友也知道他的行为。所以，就不要公开了；甚至说用户也只是想让一些用户知道他的行为！怎么解决？**只公布汇总的局部信息**，将信息通过汇总而匿名化。其实，这提供了一个新的做产品的思路，即个性化的个人数据idata。他可以帮助社交网络用户迅速了解自己朋友的整体动态：都有多少人看了什么电影，在玩什么游戏。甚至说，可以在此基础上做一个社交网络的秘密app。即用户可以匿名化的发布一些信息，也可以有选择地浏览他们公布的信息。

如何进一步激活？要**在app中引入互动性**！比如允许用户选择是否在好友网络中公布自己玩某个app的成绩，或者允许用户去挑战他的一个的好友（其实是邀请新用户）。

#### 朋友推荐

朋友的推荐的主要目的则是给用户推荐一些他还没有加的朋友。这个其实发展比较成熟，主要是将链路预测的算法应用到这个场景中来。这种推荐一般而言是有风险的。因为一些用户之所以不加一些人实际上是出于回避的目的，这个时候推荐给他们，就会适得其反。怎么办呢？基于时空信息做新关系的推荐。尤其是当用户更换地理位置时，往往要带来一批新的人际关系进来。

微信刚开始普及的时候，就抓住了手机电话薄的作用。当我把自己的skype登记的手机号码从香港号码改成北京移动的号码之后，一个小时之内，很多我以前经常联系的研究生同学就向我发来了好友邀请。我的第一感觉是我正要去找你们，你们自己就来了。但是这个故事也说明了问题所在：微信依然默认一个人只有一个邮箱、只有一个手机号码。这恰恰是其产品没有完全做好的一个表现。

- 应该允许用户填写多个电子邮箱！
- 应该允许用户填写多个手机号码！
- 应该允许用户填写其它网络账号！


#### 为什么无效？

- 为什么会失效，为什么什么不能发现有效的影响，因为网络也是有噪音的。解决方法就是要提取出有效网络。这里存在一个有效网络假设，因为我们要剔除沉睡链接，剔除暂时性链接，专注于此时此刻的强关系。为什么要专注于有效网络假设呢？因为只有它们才有影响力。**影响力网络**是我们首先要挖掘的。中国的乡土社会还是按照实际强关系的影响力展开的。

但这里有风险，来自于信息型网络的风险。因为，弱关系里隐含着信息力量。如何规避这种风险？这时候可以采用自下而上的策略：分析**扩散网络**。扩散网络不同于社交关系网络，因为它首先是行为的传递。根据历史信息的传递网络（例如app的使用）可以与影响力网络相互印证，这也是从另外一个角度构建影响力网络。

- 为什么传播会失败， 因为与用户的安全相抵触，例如**QQ圈子的提出与用户的隐私冲突**。这里要注意维护用户价值。用户对于隐私冲突的反弹，说明了腾讯用户的转变：保护自我价值的意识。人是QQ的核心，没有了节点，就没有了链接，做[连接一切的公司](http://baixiaosheng.net/4318)就成了梦幻泡影。

腾讯一开始就专注于从人的欲望本身设计产品，满足人的表达、倾诉、和分享的欲望。但是一度依赖，QQ的用户的用户倾向于被认为是低龄的低端用户。这这一定程度上会让产品设计者进一步误解用户的需求：不要把用户当傻子。如果一个程序可以自我迭代，一个人就不会自我成长吗？所以，不要把用户当傻子，不要满足于眼前的成功。尊重用户的价值，让用户自己选择，让用户自己构建。

- 为什么产品会失败，因为没有展示的空间， 以QQ为例，狭窄的面板根本挤不下那么多的产品。QQ上的产品有的独立了出来，有的还要寄人篱下。所谓独立是指拥有自己独立的王国，如游戏和微信。

手机互联网的发展，进一步提出了更苛刻的挑战：因为手机屏幕更小。如何才能生长出独立的产品来？说到底还是要靠APP。从App的角度思考，手机互联网对整个腾讯而言是一次巨大的机遇：因为如果你坚信一个子产品足够出色，做出一个独立的APP来展现它。通过累积的巨大的社交网络来传播它。

#### 如何盘活QQ圈子？

我想整个问题见仁见智，我这里也主要是按照传播的逻辑提供一些思路：

1. 尊重用户价值：让用户自己选择
2. 用户数据统计&好友汇总数据统计：了解但不越界
3. 挑战好友：游戏pk
4. 提问好友：困惑解答
5. 匿名表达：秘密倾诉
6. 自我记录：自我成长
7. 独立的手机APP

### 激活社交网络

#### 比较QQ和微信的差别
QQ当然是一款成功的社交软件。它让人们可以有效地保存既有社交资源并允许群组讨论。但沉淀下来社交关系后如果随着时间失去活跃性，其本身的价值就很有限。人总是在不同人生阶段认识不同的人，对于添加的好友须按照时间序列进行组织，例如手工分组。社交软件可以辅助好友分组，例如自动推荐组名。QQ另一功能是QQ群，它満足了人们在一群人当中讨论的需求；除了一对一和群组讨论之外，人还有一对多地发表自我感想的强烈需求，后者通过QQ zone得以实现。

#### 动态的关系：活在当下

微信的崛起在于对有效网络的组织方面。首先，激活有效网络，其次在于厘清前台与后台的界限。关系本身并不一定有效果，只有动态中的关系才能抓住用户。上文已经谈论过关系的类别。QQ中沉淀的大多数关系其实对于用户当下生活并无直接影响。这会让用户产生一种错觉：这里仅是关系的档案馆，平时并无使用的必要。其实人人网正面临这种困境，即当好友加完之后怎么吸引用户。这方面微信具有天然的优势，因为作为手机APP它是建筑在手机通讯录上面的。手机号码与QQ号码相比，更接近线下动态的社交关系。同样道理，QQ中的群组则落后很多，因为它具有太明显的静态性。微信群则可因时因地随时结成。

手Q是微信前身，然而背负着QQ产品沉重的历史包袱，所以其发展被多方掣肘。比如QQ一直以来面临定位低端产品形象不够专业的问题。但为了保持与PC端一致性所以难以改良，造成用户流失。微信从产品名称定位以及其他设计方面则具有较高灵活性，例如其开机画面就很有意思。

当然了，如此定位的两种产品有竞争也有辅助。动态关系的支柱是强关系，静态关系则包括大量弱关系。这样一方面二者在不同关系层面有所侧重，另一方面，作为新产品，微信更容易抢走QQ中的动态关系。

### 参考文献

Paul Adams (2011) Grouped: How small groups of friends are the key to influence on the social web. New Riders