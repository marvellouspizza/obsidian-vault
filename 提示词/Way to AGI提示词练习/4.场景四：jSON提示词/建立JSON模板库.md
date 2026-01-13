#### 什么场景下最适合用 JSON 写提示词？

1. 高精度视频生成 (Sora 2 / Veo 3.1)：
2. 批量化内容生产 (Programmatic SEO / Ads)：生成 1000 条格式统一、但内容不同的广告文案时
3. 复杂角色扮演 (Complex Roleplay)：
需要维护复杂的角色状态时。例如：{"Current_Mood": "Angry", "Memory": ["Insulted by user"], "Goal": "Seek revenge"}
4. API 对接与工作流自动化 (Agents)：
当提示词是自动化程序的一部分，需要被代码解析时。

建立一套通用的 JSON 模板库
{

 "subject": "具体的人、物，包含外观特征", //主体

 "composition": "x", //构图

 "lighting": "x", //布光

 "color_palette": "x", //色彩

 "camera": "x", //镜头

 "style": "胶片质感、CGI、写实、黑白",

//负向提示词

"negative_constraints": {

"Forbidden_Elements": [

"文字",

"水印",

"人物"

],

"Style_Restrictions": "无卡通风格, 仅写实风格"

}

}