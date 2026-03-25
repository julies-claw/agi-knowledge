# Agent Payments & Identity Research
*Generated: 2026-03-25 | Private*

---

## 1. Agent支付协议全景（截至2026年3月）

三个主要协议在竞争：

### x402（Coinbase + Cloudflare，开源）
- **机制**：复用HTTP 402状态码。agent请求资源 → server返回402 + 支付指令 → agent用USDC on-chain支付 → 凭收据重试
- **优势**：无需账号，5行代码接入，payment receipt即credential
- **劣势**：每笔请求一笔链上交易；无合规/退款/反欺诈；动态路由v2引入收款人操纵风险
- **实际数据**：日均~131,000笔交易，~$28K价值，均价$0.20；约一半是测试/游戏化
- **MCP集成**：Vercel `x402-mcp`，`paidTool` primitive，极简

### Stripe MPP（Machine Payments Protocol，2026年3月18日上线）
- **机制**：Session-based。agent预授权spending limit，然后流式支付，无需每次链上广播
- **优势**：内置Stripe Radar反欺诈、税务合规、KYC；支持USDC+信用卡（SPTs）；高频场景高效
- **劣势**：需要Stripe账号；对Tempo链有依赖；刚上线，无真实volume数据
- **合作伙伴**：Anthropic、OpenAI、Shopify、Visa、Mastercard、DoorDash等（部分是LOI级别）

### Google AP2（Agents Payment Protocol，2025年9月）
- **机制**：Mandate-based。用户预授权agent特定商户/金额范围内的支付权限
- **定位**：更偏向consumer shopping场景（Google Shopping agent）
- **补充**：Google 2026年1月又发了UCP（Universal Commerce Protocol），专门针对retailer

### 怎么选（实用建议）
| 场景 | 选择 |
|------|------|
| 一次性/低频API调用 | x402（零摩擦，permissionless） |
| 高频streaming agent会话 | MPP（session聚合，无需每次on-chain） |
| 面向消费者的购物代理 | Google AP2/UCP |
| 人类客户（订阅/发票） | Stripe传统billing |
| 都要 | 混合middleware，三路验证 |

---

## 2. Agent Identity：你的ENS subdomain想法 vs HLOS

### HLOS.ai是什么
- "Universal Identity Layer for AI Agents"
- STAAMP协议（Secure Trust Agent Access Management Protocol）：agent在MCP/A2A之上的credential隔离层
- **核心价值**：agent请求能力 → HLOS代理去调Twilio/AWS/MongoDB → agent只收到确认，从不看到原始credential
- **商业模式**：Universal Wallet，HLOS做所有vendor的merchant of record，统一账单
- **产品感**：`agent.send_sms(...)` 这种接口，agent不知道背后是Twilio

### 你的ENS Subdomain想法
- ENS subdomain本质是：去中心化的命名空间 + 可解析的记录 + 所有权链上可验证
- 作为"Decentralized IAM Role"：
  - ✅ 天然去中心化：不依赖任何中心化权威
  - ✅ 可组合：子域名可以代表不同权限层级（`admin.agent.julie.eth` vs `readonly.agent.julie.eth`）
  - ✅ 跨链可验证：ENS解析器可以指向任意链上身份
  - ⚠️ Gas成本：每次注册/更新需要链上操作
  - ⚠️ 没有内置的credential broker功能（HLOS有）
  - ⚠️ 没有spending limit/session管理（x402/MPP有）

### ENS vs HLOS对比
| 维度 | ENS Subdomain | HLOS |
|------|---------------|------|
| 去中心化程度 | 完全去中心化 | 中心化（HLOS是intermediary） |
| Setup | 需要链上注册 | API接入 |
| Credential隔离 | 需自建 | 内置 |
| 支付集成 | 无内置 | Universal Wallet |
| 可组合性 | 极高（任意subdomain结构） | 有限 |
| 适合场景 | 去中心化原生，web3 agent生态 | 企业级agent，快速集成 |

**你的想法的独特角度**：
ENS + x402的组合是目前没人做全的：
- ENS subdomain = agent的去中心化身份（谁是这个agent）
- x402 = agent的支付能力（agent能花钱）
- 两者合并 = agent的"护照"：有身份 + 有钱包 + 去中心化可验证

ENS DAO Newsletter #107（2026年3月）明确提到："NIST AI Agent Standards Initiative正在寻求公众意见，ENS有机会定义AI agent identity的基础层。"时间点对。

---

## 3. Agent Marketplace / "AI Upwork"想法分析

### 你的想法
一个marketplace，大家bring in自己的agent，像AI Upwork一样。

### GTM创意（你提到的那个）
不知道实际用途 → "让别人onboard agent，然后和他的agent说话，说服他的agent就赢奖池"
- 这是个**游戏化的agent能力评估机制**
- 本质是：Agent Arena + Bounty System
- 优点：立刻有趣，有传播性，解决了"不知道实际用途"的冷启动问题

### 竞争格局
- **Moltbot（OpenClaw前身）**：你提到想做得和它一样简洁
- **Agent marketplaces**：目前大多数太重（需要复杂集成）或太轻（纯目录）
- **关键缺失**：没有一个marketplace把agent identity（谁是这个agent）+ payment（agent可以被付费雇用）+ 可信执行（结果可验证）整合在一起

### 你的优势切入点
你同时有：
- awesome-ai-auth（知道安全/identity怎么做）
- goat系列代码（x402 + ERC-8004实际跑通过）
- ENS subdomain经验（去中心化身份）

这三个加起来，你可以做一个**有credibility层的agent marketplace**，而不只是个目录。

---

## 4. Agent Runtime成本对比：Compute-State解耦的商业逻辑

### 主流Agent Runtime现状（2026年3月）

| 平台 | 定位 | 隔离方式 | State持久性 | GPU支持 | 价格 |
|------|------|----------|------------|---------|------|
| **E2B** | AI agent专用sandbox | Firecracker microVM（硬隔离） | Ephemeral；session pause/resume，Hobby最长1h | ❌ | Hobby免费($100 credit)；Pro $150/mo起，按秒计费 |
| **Modal** | Serverless ML基础设施 | gVisor（用户空间内核） | Session-based，可配timeout；支持网络存储 | ✅ NVIDIA A100/H100 | Starter免费($30 credit/mo)；CPU $0.00003942/core/sec；GPU另计 |
| **Fly.io Sprites** | 持久化Linux VM | Firecracker microVM | **永久持久**：filesystem跨session存活；checkpoint/restore <1秒 | ❌ CPU only | 按VM资源计费，inactive时停计费但fs保留 |
| **Cloudflare Durable Objects** | Edge stateful compute | V8 isolates | 强一致性KV存储，geo-distributed | ❌ | 按请求+存储计费，极低延迟 |
| **Letta（原MemGPT）** | Agent memory层 | N/A（应用层） | 持久化memory，跨session | ❌ | 开源自部署；cloud版本pricing未公开 |

### 关键成本对比（典型agent工作负载）

**场景：一个24小时持续运行的coding agent，2 vCPU / 4GB RAM**

| 方案 | 月成本估算 | 说明 |
|------|-----------|------|
| E2B Pro | ~$150/mo + usage | 1 sandbox 24h/day会超出Pro包含的500h/mo |
| Modal serverless | ~$6-15/mo | 按实际active时间计费，idle不收费；2 vCPU × $0.00003942 × 3600s = $0.28/h |
| Fly.io Machine (shared-cpu-2x, 4GB) | ~$25/mo | 持续运行；暂停时~$0.15/mo（只收存储） |
| AWS t3.medium（同规格） | ~$30/mo | 不停机 |
| 自己跑VPS（Hetzner CX31） | ~$8/mo | 最便宜，无托管 |

### Compute-State解耦：你的想法解构

**现在的问题**：
所有现有方案都把compute和state绑定在一起——你要state持久化，就得保持compute运行（花钱）；你要停compute节省成本，state就可能丢失或需要复杂的序列化/恢复。

**Fly.io Sprites最接近你的方向**：
- Inactive时compute billing停止，但filesystem永久保留
- Checkpoint/restore：<1秒恢复整个VM状态
- **但**：CPU only，无GPU，无法跨provider迁移

**真正的"compute-state完全解耦"长什么样**：
```
理想架构：
Agent State Store（永久，廉价）
    ↕ 标准接口
Compute Runtime（任意provider，按需spawn）
    ↕
Agent执行层（接到state就能继续跑，无论在哪个compute上）
```

**现在缺什么**：
1. **标准化的state序列化格式**：agent的完整运行时状态（memory + context + tool state）没有跨平台标准
2. **计算层的identity连续性**：agent在不同compute provider上运行时，如何保持同一个"身份"
3. **state store的成本**：真正便宜的持久层（S3级别）+ 快速恢复（Sprites级别）的组合方案

### 你公司在propose什么？

这个方向和Letta的架构理念接近——Letta把memory/state抽象成独立层，agent的"思维"持久化在外部存储，compute只是无状态的执行环境。

差异化空间：
- Letta专注于memory抽象，不解决compute provider的迁移问题
- Fly.io Sprites解决了persistence，但锁在自己的infra
- 没有人做通用的"agent state portability layer"

**如果你的公司在build这个**：核心护城河是标准接口（类似OCI container image之于计算，你需要一个类似的东西之于agent state）。先有标准，再有生态。

---

## 5. ENS + Reputation：ERC-8004的下一层

### ERC-8004的局限

ERC-8004（GOAT Network的agent身份标准）解决了：
- Agent有一个链上地址
- Agent可以被识别

**没有解决的**：
| 缺口 | 描述 |
|------|------|
| **Reputation** | 这个agent历史上完成了多少任务？失败率？被举报过？ |
| **Capability claims** | agent声称自己能做什么，谁验证的，可不可信 |
| **Revocation** | agent被compromise了怎么快速撤销身份 |
| **Delegation** | 人类授权agent去做某件具体的事，权限范围怎么链上表达 |
| **Portable identity** | agent在不同compute provider上迁移时，身份能不能跟过去 |

### ENS Subdomain作为"Decentralized IAM Role"

**为什么ENS适合这个场景：**
- ENS subdomain无需许可，任何人可以给自己的agent注册一个`agent.julie.eth`
- TXT records可以存任意数据（JSON格式的capability manifest、credential hash等）
- 可解析性：任何系统都能查`agent.julie.eth`的records，不需要中心化API
- 层级结构天然支持权限分级

**Proposed架构：Agent Credential Profile**

```
agent.julie.eth
├── TXT "capabilities" → JSON: ["code-execution", "web-search", "payment"]
├── TXT "x402-wallet" → "0x1234...abcd"（支付钱包）
├── TXT "public-key" → 用于签名验证
├── TXT "reputation-oracle" → 指向链上reputation合约地址
└── TXT "attestations" → 第三方对这个agent的认证（谁雇过、结果如何）

子域名 = 权限隔离：
read.agent.julie.eth     → 只读权限（无支付能力）
pay.agent.julie.eth      → 有x402支付能力
admin.agent.julie.eth    → 完整权限
```

### Reputation系统设计

**链上部分（轻量）：**
```solidity
// 极简设计
struct AgentRecord {
    uint256 tasksCompleted;
    uint256 tasksFailed;
    uint256 totalEarned;      // 单位: USDC，从x402交易聚合
    uint256 lastActive;
    bytes32 latestAttestationHash;
}
mapping(bytes32 => AgentRecord) public agentRecords; // key: ENS namehash
```

**链下部分（丰富）：**
- 任务完成证明：hash + 时间戳，存IPFS，链上只存hash
- Attestation：雇主对agent的评价，类似LinkedIn推荐信但链上可验证
- Capability证明：benchmark结果、特定任务的完成记录

### 与HLOS的根本区别

| 维度 | HLOS | ENS + Reputation |
|------|------|-----------------|
| 中心化程度 | 完全中心化（HLOS是intermediary） | 完全去中心化 |
| Reputation | 无 | 链上可查历史 |
| Credential隔离 | 内置（agent看不到原始key） | 需自建broker层 |
| 可组合性 | 低（HLOS API） | 高（任意子域名结构） |
| Censorship risk | 高（HLOS可以封你） | 无 |
| 适合人群 | 快速集成、不在乎去中心化 | web3 native、重视自主权 |

**你的差异化定位**：ENS给agent的不只是"一个地址"，而是"一个可验证的身份档案"——有能力声明、有历史记录、有经济活动记录。这是agent marketplace的信任基础层。

### 技术可行性

你已有的：
- ENS subdomain经验（知道怎么注册和解析）
- ERC-8004代码（GOAT系列）
- x402支付集成（goat-agent-demo）

还需要的：
- Reputation合约（简单，可以先用The Graph做索引）
- Attestation格式标准化
- ENS resolver配置（指向自定义resolver，能解析capability JSON）

**最小可demo版本**：一个ENS subdomain + TXT records存capability + x402 wallet绑定 + 一个简单的任务完成记录合约。估计2-3天能跑通。

---

## 6. 影响力策略：如何从"有想法的人"变成"这个领域的声音"

### 你现在的问题

你在多个地方都做了有深度的东西（awesome-ai-auth、agi-knowledge、goat系列、ENS identity想法），但这些东西目前是分散的。外人看到的是"在各种地方都有东西"，而不是"Julie是做X的人"。

**影响力不是靠频繁发帖积累的。是靠一件事的深度。**

### Narrative选择

你需要选一个核心叙事，其他的东西都是这个叙事的支线。候选：

**Option A: "Agent Identity的建造者"**
> "我在build让AI agent成为可信经济参与者的基础设施。身份、信誉、支付——agent需要的不只是一个地址。"

适合人：如果你对ENS + reputation这个方向真的兴奋
内容角度：ERC-8004的局限、ENS作为agent IAM、reputation system设计
代码角度：agent-passport这个demo项目

**Option B: "Agent Security的实践者"**
> "我研究AI agent的安全边界——不是'不要泄露secrets'这种废话，而是架构层面的解决方案。"

适合人：如果你的日常工作让你在这方面有一手insight
内容角度：awesome-ai-auth继续深化，加x402安全风险、MCP供应链风险
代码角度：安全工具、审计checklist

**Option C: "Agent Infra的思考者"**
> "我在公司build agent infra，在业余时间试图理解这整个生态将如何演化。"

适合人：如果你更想保持思考者/研究者的定位，不急于push一个具体产品
内容角度：agi-knowledge继续扩张，compute-state解耦的深度分析
代码角度：研究性demo，不用完整产品

### 聚集影响力的实际路径

**不靠发帖频率，靠"被引用"和"被找到"**

1. **成为某个具体问题的权威资源**
   - awesome-ai-auth加x402安全章节 → 当有人搜"x402 security risks"，你的内容排第一
   - agi-knowledge继续更新 → 当有人找agent identity的综合资料，指向你的repo
   - 这是被动流量，不需要你每天发帖

2. **做一个可demo的东西，然后在对的地方展示一次**
   - agent-passport demo（ENS + x402 + reputation）做出来
   - 在ENS DAO的Discord/论坛发一篇技术帖（不是广告，是技术讨论）
   - 在GOAT Network的社区分享你对ERC-8004局限的分析
   - 这比发100条推文有效

3. **找到你的"同频圈子"，不是泛发**
   - ENS DAO：正在讨论AI agent identity标准
   - GOAT Network社区：你已经有代码
   - x402 Foundation（Coinbase + Cloudflare）：他们在找builders
   - 在这些具体社区里一条有深度的帖子 >> 在Twitter上100条

4. **用你的工作输出内容，而不是为了内容而创作**
   - 你在公司research compute-state解耦 → 把这个变成一篇技术分析发出去
   - 你做了agent-passport demo → 把build过程写成writeup
   - 内容来自真实工作，不需要"想内容"

### 时间线建议

| 周期 | 行动 | 预期结果 |
|------|------|---------|
| 本周 | 在awesome-ai-auth加x402安全章节 | 被x402相关搜索找到 |
| 2-3周 | agent-passport demo（ENS+x402+reputation）最小版本 | 有东西可以展示 |
| 1个月 | 在ENS DAO论坛发技术帖：ERC-8004 vs ENS subdomain for agent identity | 进入对的圈子 |
| 持续 | agi-knowledge每2周更新一个节点，附一条X/LinkedIn帖子 | 被动积累 |

**核心原则：做一件事，做深，在对的地方出现一次。胜过广撒网发100条帖。**

---

## 7. 综合判断：你的一人公司切入点

**你的独特优势组合**：
ENS identity经验 + x402/goat commerce代码 + AI auth安全框架 + agent infra实战经验（工作）+ 对这个领域的系统性理解（agi-knowledge）

**最快能验证的切入**（按优先级）：

1. **awesome-ai-auth加x402章节**（1-2天）：最快的thought leadership建立，被动流量

2. **agent-passport demo**（1-2周）：ENS subdomain + x402 wallet + 最简单的reputation记录。不用完整产品，能demo就够了。这个可以直接在ENS DAO和GOAT Network社区展示。

3. **agent marketplace验证**（中期）：用"agent battle arena"GTM（谁说服了对方的agent谁赢奖池）来低成本验证有没有人care。不用build完整marketplace，先验证需求。

**最大风险**：想法太多，每个都做了一点，没有一个深到能被记住。选一个，做完。
