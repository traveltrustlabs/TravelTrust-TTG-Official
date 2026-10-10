# 合约登记（表 1-01 · 十五台）

**上游：** TravelTrust Web3 发布说明（现行 Canvas / 卫星仓 HTML）· **≠** Phase1 旧简表  
**Mainnet：** 十五台为活名册 · contracts deployed · conversion not open

名册只列新 Web3：**最新 + 可升级 + 准备部署 + 人**。旧钥匙、退役车间见 [Legacy 政策](Legacy-Policy.md)，**不得**当作 Official 活根。

| # | 这台叫啥 | 干什么 | 新不新 | 链上好了没 | 地址 |
|---|----------|--------|--------|------------|------|
| 01 | 治理代币 | 投票、公售、主理人计量用的治理币，不能再印 | V2 | 已广播 | `0xd9965802ff0A9DAB5d0E13392dA797cd6D13ee51` |
| 02 | 投票机 | 持币人约 7 天投票；通过后再进 12 小时门 | V2 | 已广播 · 旧 #1 禁止 queue | `0x69fF62475C3ed36B3B8627BfEC980b3047B3bf42` |
| 03 | 12 小时门 | 最后 12 小时等待门；到期谁都能按执行 | V2 | delay=43200 · 旧 03 禁止 execute | `0x2Cb9f0FD770B50931f0a4cd463113bBA39331acb` |
| 04 | 现在的平台费分账机 | 只分已抽出的平台费（现在默认 5%） | V2 | 活费终点 · 白名单已 execute | `0x4aC011Dd589756fa1C8161733f645660D14A7E79` |
| 05 | 项目美元池 | 公售美元和无席位平台费进这一口 | V2 | 已广播 | `0xD49F33c1f1d806500407550f8e92b0d1b3d725d9` |
| 06 | 公售柜台 | 五轮短窗用美元换 TTG；这五轮产品锁死 | V2 | 已 seed · 买看 UTC 09:00 | `0xaB1D74A62e3fBB1c140a9Dfa9bB5b7Fe3F8C7e46` |
| 07 | 公售币库 | 创世 50% TTG 库；卖剩退回；烧走 12 小时门 | V2 | 12.5T | `0x1c9dBa15eBFB31Dd4BDa608b7b003B3ba4a61287` |
| 08 | 空号（本批不部署） | 编号保留。活费 11→12→13→04 | 不盖 | 不部署 | — |
| 09 | 美元稳定币 | Circle 美元；公售、订金、准入都认它 | 已经是这台 | Circle 已钉 | `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48` |
| 10 | 主理人席位 | 主理人用 TTG 占席；30 万打 14、币锁本台 | V2 | 白名单已 execute | `0x131fa67a38563c99Aa65B4470d568d8aC738D77b` |
| 11 | 开单工厂 | 官网下单时印托管单的工厂 | V2 | 游客确认即放款 | `0x34d5E7eCe5c1638D6F078F0B461277EcDf64bf29` |
| 12 | 放款车间 | 完成单后放本金、抽 5% 交给分账 | V2 | 向导不签放款 | `0x70ea026ce66C884E89b90473AcF5f2780dAE1b47` |
| 13 | 完成单喊分账的接头 | 放款后喊分账并带国家码 | V2 | 04 initialize 已接 | `0x004b6458085aaCC55dedAB52E4B004b69c832b75` |
| 14 | 暂停钥（人钥） | 暂停公售 · 创世 7% · 30 万准入。**不是**项目池运营取款。不是智能合约。 | 按键的人 | 与 7% 同址 | `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` |
| 15 | 预约钥（人钥） | 部署/预约 · 创世 5% · **项目池 90 天≤30% 运营取款打这里**。不是智能合约。 | 按键的人 | 与 5% 同址 | `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` |

打开某一台的 20 栏说明书：卫星仓 [TravelTrust-Web3-发布说明.html](https://github.com/TT-Cc19873/TravelTrust-TTG-Primary-Market/blob/main/TravelTrust-Web3-%E5%8F%91%E5%B8%83%E8%AF%B4%E6%98%8E.html) → 表 1-01 → **打开**。

**11 RETIRED / HISTORICAL：** 更旧 `0xEE0BE3a8a8658E06c44539deD758Fb70A7f3C1C6` 与旧活 `0xcF5E02a81f10f2d6fa7BEbBb5baE3ADf658cFFFE` 只解析旧单，禁止 runtime / default / fallback / 新订单。现行 11 = 上表。书面生产放行尚未作出。Official API + www 已换针。新 11 信封已解锁；链上广播仍关闭。App 安装包 / TestFlight 未换。附属 DAO `0x063174C62A2878eB8E6c033363b8f1bA1aE9cE3b` · Activity `0xAAc1A74d6b76405427102b602a8d7fE320f89de8`（创世 0）。
