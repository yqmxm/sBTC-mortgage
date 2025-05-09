# sBTC-mortgage
a sBTC mortgage smart contract using granite protocol to do long-term loan for Bitcoin.

Clarity 智能合约
使用 Clarity 语言编写你的抵押贷款合约

支持用户：

锁定 sBTC 作为抵押品

借出 BTC（或者借出Stacks链上的BTC衍生资产，如xBTC、wrapped BTC等）

合约基本功能
lock-collateral ：用户锁定sBTC

borrow-btc ：基于抵押品比例发放贷款

repay-loan ：用户偿还贷款

liquidate ：当抵押率不足时触发清算逻辑

2. 连接 Granite Protocol
Granite Protocol 现在主要负责 sBTC的铸造和赎回，你需要：

调用 Granite 的公共接口（如sbtc-mint, sbtc-burn）

获取当前 sBTC / BTC 的汇率信息

确保你的贷款逻辑和 Granite 的sBTC资产池打通


3. 实现长期贷款机制
目标：允许用户6个月、12个月、24个月这样的时间窗口借BTC

在合约中实现定期贷款逻辑

对不同期限设置不同的利率模型（比如短期利率低，长期利率高）

采用过度抵押机制（比如150%抵押率）


4. Interface 界面开发
推荐你使用：

Stacks.js SDK 连接你的Clarity合约

React + Next.js 开发前端

Hiro Wallet 支持用户登录并签名交易

界面核心功能
📥 用户连接钱包、存入sBTC

📊 显示抵押率、借贷利率、贷款期限

💸 操作：抵押 → 借贷 → 偿还 → 提取

🛠️ 技术栈建议
模块	技术选型
智能合约	Clarity (Stacks链)
前端开发	Next.js + React
钱包集成	Hiro Wallet
SDK & API	Stacks.js, Granite API
测试网络	Stacks Testnet

