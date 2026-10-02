# 合约登记（表 1-01 · 十五台）

**上游：** TravelTrust Web3 发布说明（现行 Canvas / 卫星仓 HTML）· **≠** Phase1 旧简表  
**Mainnet：** 十五台为活名册 · contracts deployed · conversion not open

名册只列新 Web3：**最新 + 可升级 + 准备部署 + 人**。旧钥匙、退役车间见 [Legacy 政策](Legacy-Policy.md)，**不得**当作 Official 活根。

| # | 这台叫啥 | 干什么 | 新不新 | 链上好了没 | 地址 |
|---|----------|--------|--------|------------|------|
| 01 | 治理代币 | 投票、公售、主理人计量用的治理币，不能再印 | remint 新台 | 已广播 | `0x01dc2706c4E0F82995d63042c06873d1DC6B3AEa` |
| 02 | 投票机 | 持币人约 7 天投票；通过后再进 12 小时门 | remint 新台 | 已广播 · 旧 #1 禁止 queue | `0xf9D9143bB632096ABeFd943D894c43C04fD16ED4` |
| 03 | 12 小时门 | 最后 12 小时等待门；到期谁都能按执行 | remint 新台 | delay=43200 · 旧 03 禁止 execute | `0xafaee79259c831630E6f7Dc5B8885E0Fbe27fb5F` |
| 04 | 现在的平台费分账机 | 只分已抽出的平台费（现在默认 5%） | remint 新台 | 活费终点 · 白名单已 execute | `0x95E794B6Ed6Ce2547b22b220761De106c5f42515` |
| 05 | 项目美元池 | 公售美元和无席位平台费进这一口 | remint 新台 | 已广播 | `0x55cBeD4460Ad2bCc0a9F2598af5013415B121d61` |
| 06 | 公售柜台 | 五轮短窗用美元换 TTG；这五轮产品锁死 | remint 新台 | 已 seed · 买看 UTC 09:00 | `0xEaB632241C9c93B9012fc60a834d2D771E620130` |
| 07 | 公售币库 | 创世 50% TTG 库；卖剩退回；烧走 12 小时门 | remint 新台 | 12.5T | `0x5Ce1f7A8a9560aFf257B184F012e87B7ee2f3A6A` |
| 08 | 空号（本批不部署） | 编号保留。活费 11→12→13→04 | 不盖 | 不部署 | — |
| 09 | 美元稳定币 | Circle 美元；公售、订金、准入都认它 | 已经是这台 | Circle 已钉 | `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48` |
| 10 | 主理人席位 | 主理人用 TTG 占席；30 万打 14、币锁本台 | remint 新台 | 白名单已 execute | `0x3E7C7b2238d90dea4D31A2ee397068CB2ecF1032` |
| 11 | 开单工厂 | 官网下单时印托管单的工厂 | remint 新台 | 游客确认即放款 | `0x61c459f3fdD61a9194D23B26acA9DDC6Df9839aB` |
| 12 | 放款车间 | 完成单后放本金、抽 5% 交给分账 | remint 新台 | 向导不签放款 | `0xEe34DB838cf40b1C9b2AC2248340eFc8Ea8A1C16` |
| 13 | 完成单喊分账的接头 | 放款后喊分账并带国家码 | remint 新台 | 04 initialize 已接 | `0x4316FeC59EB5dedf66c9948E66BbBaa9d67294F0` |
| 14 | 暂停钥（人钥） | 暂停公售 · 创世 7% · 30 万准入。**不是**项目池运营取款。不是智能合约。 | 按键的人 | 与 7% 同址 | `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` |
| 15 | 预约钥（人钥） | 部署/预约 · 创世 5% · **项目池 90 天≤30% 运营取款打这里**。不是智能合约。 | 按键的人 | 与 5% 同址 | `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` |

打开某一台的 20 栏说明书：卫星仓 [TravelTrust-Web3-发布说明.html](https://github.com/TT-Cc19873/TravelTrust-TTG-Primary-Market/blob/main/TravelTrust-Web3-%E5%8F%91%E5%B8%83%E8%AF%B4%E6%98%8E.html) → 表 1-01 → **打开**。

**11 RETIRED / HISTORICAL：** 更旧 `0xEE0BE3a8a8658E06c44539deD758Fb70A7f3C1C6` 与旧活 `0xcF5E02a81f10f2d6fa7BEbBb5baE3ADf658cFFFE` 只解析旧单，禁止 runtime / default / fallback / 新订单。现行 11 = 上表。书面生产放行尚未作出。Official API + www 已换针。Owner **关 pending** 后新 11 信封开；广播仍关。App 安装包 / TestFlight 未换。附属 DAO `0x6fc3Be4999DE2Ad648C70e72076a66A7cB90a3c1` · Activity `0xAAc1A74d6b76405427102b602a8d7fE320f89de8`（创世 0）。
