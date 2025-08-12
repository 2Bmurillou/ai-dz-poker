# AI Poker GTO 训练系统

一个专业的扑克 Game Theory Optimal (GTO) 策略训练应用，帮助玩家通过科学的方法提升决策水平。

## 🎯 核心功能

### 1. GTO 策略热力图
- **手牌范围可视化**: 13x13 网格展示所有起手牌的 GTO 策略
- **动态筛选**: 支持按对子、同花、非同花筛选
- **详细分析**: 悬停查看每手牌的具体行动频率（Raise/Call/Fold）
- **数据导出**: 支持 CSV 格式导出策略数据

### 2. 实时训练模式
- **交互式牌桌**: 完整的扑克游戏界面
- **即时反馈**: 每次决策后获得 GTO 分析和评分
- **位置策略**: 针对不同位置（UTG, CO, BTN, SB, BB）的专业策略建议
- **进度跟踪**: 实时统计平均得分和手数

### 3. 场景化训练
- **多种训练场景**: 6 个精心设计的训练场景
- **难度分级**: 初级、中级、高级三个难度等级
- **智能推荐**: 根据玩家表现推荐合适的训练场景
- **学习目标**: 每个场景都有明确的学习重点

## 🏗️ 技术架构

### 前端技术栈
- **React 18** + **TypeScript**: 现代化组件开发
- **Next.js 14**: 全栈框架，支持 SSR
- **Tailwind CSS**: 快速响应式样式开发
- **组件化设计**: 可复用的 UI 组件系统

### 核心模块

#### 1. 游戏引擎 (`src/lib/poker-engine.ts`)
```typescript
class PokerEngine {
  // 完整的扑克规则实现
  createDeck(): Card[]           // 洗牌发牌
  processAction(): boolean       // 处理玩家行动
  dealCommunityCards(): void     // 发放公共牌
  isBettingRoundComplete(): boolean // 判断下注轮结束
}
```

#### 2. GTO 策略引擎 (`src/lib/gto-strategy.ts`)
```typescript
class GtoStrategyEngine {
  // 基于位置的 GTO 策略推荐
  getGtoRecommendation(): GtoStrategy    // 获取 GTO 建议
  analyzeAction(): ActionAnalysis        // 分析玩家行动
  getHandRanking(): number               // 手牌强度排名
}
```

#### 3. 手牌范围管理 (`src/lib/hand-ranges.ts`)
```typescript
class HandRangeManager {
  // 手牌范围解析和管理
  parseRange(rangeString: string): HandRange     // 解析范围字符串
  getRangeStats(): RangeStatistics               // 获取范围统计
  isInRange(): boolean                           // 判断手牌是否在范围内
}
```

#### 4. 训练场景系统 (`src/lib/training-scenarios.ts`)
```typescript
class TrainingScenarioManager {
  // 训练场景管理和生成
  getAllScenarios(): TrainingScenario[]          // 获取所有场景
  getRecommendedScenarios(): TrainingScenario[]  // 智能推荐场景
  generateScenarioHand(): ScenarioSetup          // 生成场景设置
}
```

### UI 组件系统

#### 牌桌组件
- **PokerTable**: 主牌桌界面
- **PlayerSeat**: 玩家席位显示
- **CommunityCards**: 公共牌区域
- **ActionButtons**: 行动按钮组

#### 分析组件
- **GtoHeatmap**: 策略热力图
- **GtoFeedback**: 即时反馈模态框
- **ScenarioSelector**: 场景选择器

## 🚀 快速开始

### 安装依赖
```bash
npm install
```

### 启动开发服务器
```bash
npm run dev
```

访问 `http://localhost:3000` 开始使用。

### 构建生产版本
```bash
npm run build
npm start
```

## 📊 训练场景详解

### 初级场景
1. **Button vs Big Blind (Deep Stack)**: 深筹码按钮位训练
2. **Under The Gun (6-max)**: UTG 位置紧手范围练习

### 中级场景
3. **Cutoff Steal Attempt**: CO 位置偷盲策略
4. **Middle Position 3-Bet Defense**: 中位 3-bet 防守

### 高级场景
5. **Small Blind vs Big Blind**: 盲位对抗复杂决策
6. **Tournament Bubble Play**: 锦标赛泡沫期策略

## 🎨 界面特色

### 专业牌桌设计
- 真实感牌桌布局
- 流畅的动画效果
- 直观的信息展示

### 智能反馈系统
- 0-100 分评分制度
- 详细的决策分析
- 彩色编码的策略频率

### 数据可视化
- 热力图颜色编码
- 实时统计图表
- 进度跟踪面板

## 🔮 未来规划

### 第二阶段功能
- [ ] 翻后（Postflop）GTO 策略
- [ ] AI 对手多样化
- [ ] 手牌历史回放
- [ ] 更多训练场景

### 第三阶段功能
- [ ] 多人在线对战
- [ ] 排行榜系统
- [ ] 数据统计看板
- [ ] 自定义场景编辑器

### 第四阶段功能
- [ ] 云端 GTO Solver 集成
- [ ] 移动端应用
- [ ] 视频教学集成
- [ ] 社区功能

## 🛠️ 开发说明

### 项目结构
```
src/
├── components/          # React 组件
│   ├── Card.tsx        # 扑克牌组件
│   ├── PokerTable.tsx  # 牌桌组件
│   ├── GtoFeedback.tsx # 反馈组件
│   └── ...
├── lib/                # 核心逻辑
│   ├── poker-engine.ts # 游戏引擎
│   ├── gto-strategy.ts # GTO 策略
│   └── ...
├── types/              # TypeScript 类型定义
└── pages/              # Next.js 页面
```

### 代码规范
- TypeScript 严格模式
- ESLint 代码检查
- Prettier 代码格式化
- 组件化开发

## 📝 许可证

MIT License - 详见 [LICENSE](LICENSE) 文件。

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request 来改进项目！

---

**AI Poker GTO 训练系统** - 让每一个决策都更接近最优解 🎯

