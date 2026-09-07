# 1 🏠 MATLAB / Simulink 学习主页

> 记录 MATLAB 与 Simulink 的学习轨迹。热力图颜色越深，代表当天创建/修改的笔记越多。

## 1.1 📊 学习热力图

```dataviewjs
// ===== GitHub 风格学习热力图 =====
// 数据来源：库内所有笔记的创建日期(file.cday)与最近修改日期(file.mday)

const TODAY = dv.luxon.DateTime.now().startOf("day");
const FMT = "yyyy-MM-dd";
const activity = new Map();

const add = (d) => {
  const key = d.toFormat(FMT);
  activity.set(key, (activity.get(key) ?? 0) + 1);
};

for (const p of dv.pages()) {
  const m = p.file.mday, c = p.file.cday;
  if (m && m.isValid) add(m);
  if (c && c.isValid && (!m || c.toFormat(FMT) !== m.toFormat(FMT))) add(c);
}

// 强度分级（可按笔记量自行调整阈值）
const levelOf = (n) => n >= 5 ? 4 : n >= 3 ? 3 : n >= 2 ? 2 : n >= 1 ? 1 : 0;
const COLORS = [
  "var(--background-modifier-border)", // 0
  "#9be9a8", "#40c463", "#30a14e", "#216e39",
];
const PITCH = 13, SIZE = 10, WEEKS = 53;

// ===== 统计 =====
let total = 0;
for (const v of activity.values()) total += v;
let streak = 0;
let cursor = activity.has(TODAY.toFormat(FMT)) ? TODAY : TODAY.minus({ days: 1 });
while (activity.has(cursor.toFormat(FMT))) { streak++; cursor = cursor.minus({ days: 1 }); }
let longest = 0, run = 0, prev = null;
for (const k of [...activity.keys()].sort()) {
  const d = dv.luxon.DateTime.fromFormat(k, FMT);
  run = prev && Math.round(d.diff(prev, "days").days) === 1 ? run + 1 : 1;
  longest = Math.max(longest, run);
  prev = d;
}

// ===== 渲染 =====
const start = TODAY.minus({ days: (WEEKS - 1) * 7 + (TODAY.weekday % 7) });

// 月份标签行
let monthsHtml = "", prevMonth = null;
for (let w = 0; w < WEEKS; w++) {
  const firstDay = start.plus({ days: w * 7 });
  const show = firstDay <= TODAY && firstDay.month !== prevMonth;
  monthsHtml += `<span style="display:inline-block;width:${PITCH}px;font-size:10px;line-height:14px;color:var(--text-faint);white-space:nowrap;">${show ? firstDay.month + "月" : ""}</span>`;
  prevMonth = firstDay.month;
}

// 星期标签列（一 / 三 / 五）
const dayLabels = ["", "一", "", "三", "", "五", ""]
  .map((t) => `<span style="display:block;width:14px;height:${SIZE}px;margin:1.5px 4px 1.5px 0;font-size:9px;line-height:${SIZE}px;color:var(--text-faint);text-align:right;">${t}</span>`)
  .join("");

// 53 列 × 7 行格子
const cell = (w, row) => {
  const day = start.plus({ days: w * 7 + row });
  if (day > TODAY)
    return `<span style="display:inline-block;width:${SIZE}px;height:${SIZE}px;margin:1.5px;border-radius:2px;"></span>`;
  const n = activity.get(day.toFormat(FMT)) ?? 0;
  const lvl = levelOf(n);
  return `<span title="${day.toFormat(FMT)} · ${n} 次活动" style="display:inline-block;width:${SIZE}px;height:${SIZE}px;margin:1.5px;border-radius:2px;background:${COLORS[lvl]};${lvl === 0 ? "opacity:0.5;" : ""}"></span>`;
};
let gridHtml = "";
for (let row = 0; row < 7; row++) {
  let rowHtml = "";
  for (let w = 0; w < WEEKS; w++) rowHtml += cell(w, row);
  gridHtml += `<div style="display:flex;">${rowHtml}</div>`;
}

const legend = COLORS
  .map((c) => `<span style="display:inline-block;width:${SIZE}px;height:${SIZE}px;margin:0 2px;border-radius:2px;background:${c};${c.startsWith("var") ? "opacity:0.5;" : ""}"></span>`)
  .join("");

const root = document.createElement("div");
root.innerHTML = `
<div style="overflow-x:auto;padding:2px 0;">
  <div style="display:flex;justify-content:flex-end;gap:6px;font-size:11px;color:var(--text-muted);margin-bottom:4px;">
    <span>累计 ${total} 次活动</span>·<span>${activity.size} 个活跃日</span>·<span>当前连续 ${streak} 天</span>·<span>最长连续 ${longest} 天</span>
  </div>
  <div style="margin-left:18px;display:flex;">${monthsHtml}</div>
  <div style="display:flex;">
    <div style="display:flex;flex-direction:column;justify-content:flex-start;">${dayLabels}</div>
    <div style="display:flex;flex-direction:column;">${gridHtml}</div>
  </div>
  <div style="display:flex;justify-content:flex-end;align-items:center;font-size:11px;color:var(--text-muted);margin-top:6px;">少 ${legend} 多</div>
</div>`;
dv.container.appendChild(root);
```

## 1.2 🗂 导航

| 板块               | 内容                      | 入口                                         |
| ---------------- | ----------------------- | ------------------------------------------ |
| **M_Note**       | MATLAB 语言学习笔记           | [[数组]] · [[内容]]                            |
| **SimulinkTest** | Simulink Test 学习路线与章节笔记 | [[ROADMAP]] · [[00-索引]] · [[README\|项目说明]] |
| **Models**       | Simulink 模型（FOC 电机控制等）  | —                                          |
| **Scripts**      | MATLAB 脚本与练习            | —                                          |

## 1.3 🕘 最近更新

```dataview
TABLE WITHOUT ID
  file.link AS "笔记",
  dateformat(file.mtime, "yyyy-MM-dd HH:mm") AS "更新时间",
  file.folder AS "目录"
WHERE file.name != this.file.name
SORT file.mtime DESC
LIMIT 8
```
