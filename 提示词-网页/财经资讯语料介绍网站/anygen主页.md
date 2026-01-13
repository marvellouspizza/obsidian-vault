
https://www.anygen.io/share/15MTZf8c7w8uyNRDsAyrBM
# Role

你是一位世界级的全栈前端工程师和UI/UX设计师，擅长构建高密度、高性能的金融数据终端界面（类似 Bloomberg Terminal 或雪球）。你的审美风格偏向 "Dark Aurora"（极光暗黑风格），擅长处理复杂的信息架构。

# Project Goal

构建一个**高密度的财经资讯门户网站**（Finance Insights Portal）。  
核心目标：去除所有营销性质的 Landing Page 元素，打造一个纯粹的、信息密集型的金融情报终端。用户进入首页即看到实时滚动的行情、7x24小时快讯流和深度研报。

# Tech Stack

- **Framework**: React 19 + TypeScript + Vite
    
- **Styling**: Tailwind CSS v4 (使用 OKLCH 色彩空间)
    
- **UI Library**: shadcn/ui (Cards, Badges, ScrollArea, Tabs, Buttons)
    
- **Icons**: Lucide React
    
- **Charts**: Recharts (用于迷你趋势图)
    
- **Animation**: Framer Motion (微交互) + CSS Keyframes (跑马灯)
    

# Design System: "Dark Aurora"

1. **Color Palette**:
    
    - **Background**: Deep Dark Blue/Black (`oklch(0.12 0.01 260)`), 营造沉浸式专业感。
        
    - **Primary**: Neon Cyan/Purple (`oklch(0.65 0.18 240)`), 用于高亮关键数据和交互点。
        
    - **Semantic**:
        
        - Red (`text-red-500`): 下跌/看空/警示。
            
        - Green (`text-green-500`): 上涨/看多/利好。
            
2. **Typography**:
    
    - **Headings**: "Space Grotesk" —— 现代、科技感、宽字重。
        
    - **Body**: "Rajdhani" —— 紧凑、具有终端机风格，适合高密度数据显示。
        
3. **UI Traits**:
    
    - **Glassmorphism**: 模块背景使用 `bg-card/50 backdrop-blur-md`。
        
    - **High Density**: 减小 Padding 和 Margin，字体偏小（text-xs/text-sm），一屏内展示尽可能多的信息。
        
    - **Borders**: 极细微的 `border-white/5` 或 `border-white/10`。
        

# Page Structure & Layout Requirements

页面应采用 **Sticky Header + 3-Column Grid** 布局。

## 1. Global Header (Sticky)

- **Top Bar**: 必须包含一个自动横向循环滚动（Marquee）的**全球市场行情条**。
    
    - 显示：上证指数、标普500、纳斯达克、比特币等实时点位和涨跌幅。
        
- **Nav Bar**: Logo 在左，中间是高密度的分类导航（宏观、A股、港美股、基金、量化、舆情），右侧是搜索框和用户状态。
    

## 2. Main Layout (3-Column Grid)

使用 CSS Grid，在大屏下分为 12 列：

### Left Column (Width: ~20-25%) - "7x24 Flash News"

- **Function**: 实时快讯流，类似电报风格。
    
- **Components**:
    
    - 垂直滚动区域 (`ScrollArea`)。
        
    - 时间轴样式：每条新闻左侧有时间戳（如 10:42）。
        
    - **Highlight Support**: 重要突发新闻使用红色高亮或脉冲动画 (`animate-pulse`) 标记。
        

### Center Column (Width: ~50%) - "Core Insights"

- **Function**: 深度阅读区。
    
- **Featured**: 顶部展示一个带有大图背景的“今日头条”卡片。
    
- **Reports List**: 下方排列深度研报摘要。
    
    - Card 样式：左侧文字（标题+摘要+元数据），右侧小图缩略图。
        
    - Metadata：需显示“券商来源”、“页数”、“发布时间”等专业信息。
        

### Right Column (Width: ~25-30%) - "Quant & Sentiment Dashboard"

- **Function**: 量化数据看板。
    
- **Module A: Sector Flows**: 主力资金流向表格，显示板块名称、涨跌幅、净流入金额（红绿配色）。
    
- **Module B: KOL Sentiment**: 大V观点监测。
    
    - 显示大V昵称、平台（雪球/微博）、多空态度（看多/看空/中性 Tag）。
        
    - 态度 Tag 需要用不同颜色区分（绿/红/黄）。
        
- **Module C: Sentiment Thermometer**: 市场情绪温度计（0-100），使用渐变色进度条展示当前是“恐慌”还是“贪婪”。
    

# Content Requirements

- **Mock Data**: 数据必须看起来**极度真实**。不要用 "Lorem Ipsum"。
    
    - 使用真实的金融术语：如“流动性拐点”、“北向资金”、“超配”、“底背离”、“主力吸筹”。
        
    - 涉及具体的实体：如“中信证券”、“宁德时代”、“美联储”、“高盛”。
        
- **Interactivity**:
    
    - 鼠标悬停在卡片上时，边框高亮 (`hover:border-primary/50`)。
        
    - 图片加载时要有渐变遮罩。
        

# Implementation Plan

请按照上述规范，输出 `src/pages/Home.tsx` 及相关组件代码。确保代码结构清晰，组件复用性高。