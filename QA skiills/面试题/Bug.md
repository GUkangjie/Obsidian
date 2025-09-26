**【RTB】召回漏斗by tag_id 配置采样比例测试[Bug]使用的随机数生成函数有误（Intn 为左闭右开）无法取到右边的边界值**
**若命中此逻辑则为全量打印，不符合按采样比例配置打印策略**
![[Pasted image 20250926164251.png]]
**offer入库测试时发现icon_url和icon_192存入数据库为空**
**入库的icon地址点击后看不到上传的图片**
![[Pasted image 20250926164431.png]]

**表suggestion_ad_new不使用delivery_store和app_store这两个字段**
当时的需求是表 `suggestion_offer_new` 新增字段 `delivery_store` 和 `app_store`，接口需做兼容，保证写入时正确处理这两个字段。
根据接口逻辑，`addAD` 无论何种参数，都会向 `suggestion_offer_new` 表写入数据；当参数 `only_offer = 1` 时，还会执行向 `suggestion_ad_new` 的写入逻辑。
我在设计验证case时，发现 `offer_new表` 写入正常，但 `ad_new表` 未插入或更新。初步判断是 `only_offer = 1` 分支下逻辑异常，可能在执行 SQL 前报错了。  
我通过打印调试，确认代码逻辑能正常进入 SQL 执行阶段，怀疑问题出在 SQL 本身,我打印出实际执行的 SQL，并在数据库中手动执行，发现报错：
Unknown column ‘appstore’
进一步排查确认，suggestionadnew 表并未新增 deliverystore、appstore 这两个字段。经与开发和产品确认，该表实际上不需要增加这两个字段，是兼容逻辑误加导致 SQL 执行失败。
最终，开发移除冗余字段写入逻辑后，复测通过。

