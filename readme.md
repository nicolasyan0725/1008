---
title: 選擇題測驗卷網站講義（學生版）

---

---
title: 選擇題測驗卷網站講義（學生版）

---

---
title: 選擇題測驗卷網站講義（學生版）
tags: [114程式設計與實習_上學期]

---

# 選擇題測驗卷網站講義（學生版）

學號：＿＿＿＿＿＿＿＿　　姓名：＿＿＿＿＿＿＿＿

> **填寫方式**
> 1. 每個學習都要放：**執行截圖**、**三次問 AI 的提示詞**、**最後採用的程式碼**。
> 2. 問 AI 的提示詞請**逐字貼上**自己實際輸入的內容（不要寫摘要），第一次、第二次、第三次依序記錄。
> 3. 程式碼貼在「點開貼上」的收合區塊裡，貼上**你最後真正採用、而且能執行**的版本。

---

## 學習1：產生一個選擇題測驗卷網站

https://cfchen58.synology.me/115/week4/stage1/

**這個階段的目標：** 用 p5.js 做出一個一次顯示一題、四個選項、答完會顯示對錯與總分的測驗網站（題目先寫在程式裡）。
**這個階段會修改的檔案：** index.html、sketch.js

### 執行截圖

（把截圖拖曳到這裡，或貼上圖片連結）

![動畫](https://hackmd.io/_uploads/rJXf9h4jfl.gif)

### 第一次問 AI

```tex!
幫我用p5.js的JavaScript程式碼做一個網頁測驗系統，主題為教育科技，要有即時的回饋，對錯的效果。系統採用全螢幕畫布，選項需有鑑別度，共五題，作答完畢後要告訴測驗者答對率及錯題之詳解。
```

### 第二次問 AI

```tex!
我要javascipt的程式碼
```
### 程式碼內容

:::info
:::spoiler 點開貼上學習1的程式碼
```javascript=
// 教育科技主題互動測驗系統 (p5.js) - 手動點擊下一題版本
let questions = [
  {
    question: "在教育科技領域中，TPACK 框架將教師的專業知識分為三個核心領域，請問下列何者正確？",
    options: [
      "A. 教學知識 (PK)、心理知識 (PK)、電腦知識 (CK)",
      "B. 學科內容知識 (CK)、教學法知識 (PK)、科技知識 (TK)",
      "C. 評量知識 (AK)、資訊知識 (IK)、課程知識 (CK)",
      "D. 理論知識 (TK)、實務知識 (PK)、數位素養 (DK)"
    ],
    answer: 1,
    explanation: "TPACK 全稱為 Technological Pedagogical Content Knowledge，核心包含學科內容知識 (CK)、教學法知識 (PK) 及科技知識 (TK) 三者的交集與融合。"
  },
  {
    question: "ADDIE 教學設計模型是數位課程發展的經典架構，其五個階段的正確順序為何？",
    options: [
      "A. 分析 (Analysis) → 設計 (Design) → 開發 (Development) → 實施 (Implementation) → 評量 (Evaluation)",
      "B. 評量 (Evaluation) → 設計 (Design) → 發展 (Development) → 實施 (Implementation) → 分析 (Analysis)",
      "C. 設計 (Design) → 分析 (Analysis) → 實施 (Implementation) → 評量 (Evaluation) → 開發 (Development)",
      "D. 開發 (Development) → 評量 (Evaluation) → 分析 (Analysis) → 設計 (Design) → 實施 (Implementation)"
    ],
    answer: 0,
    explanation: "ADDIE 模型標準五階段為：分析 (Analysis)、設計 (Design)、開發 (Development)、實施 (Implementation)、評量 (Evaluation)。"
  },
  {
    question: "關於「翻轉教室 (Flipped Classroom)」教學模式的敘述，下列哪一項最具鑑別度與正確性？",
    options: [
      "A. 課堂上由老師講授核心概念，回家後由學生自主完成紙筆測驗",
      "B. 學生在家透過線上影片自主學習知識，課堂上則進行討論、協作與實作應用",
      "C. 完全不使用任何紙本教材，全面以電子白板及虛擬實境取代傳統教學",
      "D. 僅適用於高等教育之遠距線上課程，國民義務教育階段無法實施"
    ],
    answer: 1,
    explanation: "翻轉教室核心精神為「先學後教」，學生課前自主看影片吸收知識，課堂時間則留給教師引導討論、解決問題與高階思維活動。"
  },
  {
    question: "在現代 AI 適性化學習系統 (Adaptive Learning) 中，最核心的底層技術與機制通常是：",
    options: [
      "A. 隨機亂數抽取題庫，確保每位學生的題目完全不重複",
      "B. 依賴教師手動逐題設定分數權重與固定解鎖關卡",
      "C. 透過知識圖譜 (Knowledge Graph) 與即時學生反應理論 (IRT) 動態評估能力並推薦路徑",
      "D. 強制規定所有學生必須在相同時間內完成相同進度的測驗"
    ],
    answer: 2,
    explanation: "適性化學習系統利用知識圖譜與試題反應理論 (Item Response Theory)，根據學生作答表現即時診斷強弱點，動態調整下一個學習內容或難度。"
  },
  {
    question: "關於學習管理系統 (LMS，如 Moodle、Canvas、Blackboard) 的主要功能與定位，下列何者描述最為精確？",
    options: [
      "A. 專門用於取代學校實體教室的硬體設備與桌椅配置",
      "B. 提供數位化課程管理、學習歷程紀錄 (Learning Analytics)、作業繳交與師生互動的整合平台",
      "C. 僅能提供選擇題自動批改，無法支援多元作業與同儕互評功能",
      "D. 屬於雲端社群軟體，主要用於學生課外社交與娛樂互動"
    ],
    answer: 1,
    explanation: "LMS 是數位教學的中央樞紐，整合了教材派發、作業繳交、成績管理、討論區及學習分析等強大功能。"
  }
];

let currentQuestion = 0;
let userAnswers = [];
let gameState = "START"; 
let selectedOption = null; 
let showFeedback = false; 

function setup() {
  createCanvas(windowWidth, windowHeight);
  textAlign(LEFT, TOP);
}

function draw() {
  background(15, 23, 42); 

  if (gameState === "START") {
    drawStartScreen();
  } else if (gameState === "QUIZ") {
    drawQuizScreen();
  } else if (gameState === "RESULT") {
    drawResultScreen();
  }
}

function windowResized() {
  resizeCanvas(windowWidth, windowHeight);
}

function drawStartScreen() {
  push();
  textAlign(CENTER, CENTER);
  
  fill(56, 189, 248);
  textSize(min(width * 0.04, 36));
  text("💡 教育科技 (EdTech) 互動素養測驗系統", width / 2, height * 0.28);
  
  fill(148, 163, 184);
  textSize(min(width * 0.02, 18));
  text("本測驗包含 5 道具有鑑別度的教育科技核心試題\n提供即時對錯回饋與詳細觀念解析", width / 2, height * 0.38);

  let btnW = 220, btnH = 60;
  let btnX = width / 2 - btnW / 2;
  let btnY = height * 0.58;
  
  let isHover = mouseX > btnX && mouseX < btnX + btnW && mouseY > btnY && mouseY < btnY + btnH;
  
  fill(isHover ? 14 : 2, isHover ? 165 : 132, isHover ? 233 : 199);
  noStroke();
  rect(btnX, btnY, btnW, btnH, 12);
  
  fill(255);
  textSize(20);
  text("開始測驗", width / 2, btnY + btnH / 2 - 10);
  pop();
}

function drawQuizScreen() {
  let margin = width > 768 ? width * 0.15 : 24;
  let cardW = width - (margin * 2);

  push();
  fill(148, 163, 184);
  textSize(16);
  text(`題目 ${currentQuestion + 1} / ${questions.length}`, margin, 30);
  
  let barW = cardW;
  let progress = (currentQuestion + 1) / questions.length;
  fill(30, 41, 59);
  noStroke();
  rect(margin, 55, barW, 8, 4);
  fill(56, 189, 248);
  rect(margin, 55, barW * progress, 8, 4);
  pop();

  let qData = questions[currentQuestion];
  push();
  fill(30, 41, 59, 200);
  stroke(51, 65, 85);
  strokeWeight(2);
  rect(margin, 80, cardW, 100, 12);

  fill(255);
  textSize(min(width * 0.022, 18));
  noStroke();
  text(qData.question, margin + 20, 95, cardW - 40, 75);
  pop();

  let startY = 195;
  let optH = 55;
  let gap = 12;

  for (let i = 0; i < qData.options.length; i++) {
    let optY = startY + i * (optH + gap);
    let isHover = mouseX > margin && mouseX < margin + cardW && mouseY > optY && mouseY < optY + optH;
    
    let boxColor = color(30, 41, 59);
    let strokeColor = color(51, 65, 85);

    if (showFeedback) {
      if (i === qData.answer) {
        boxColor = color(20, 83, 45); 
        strokeColor = color(34, 197, 94);
      } else if (i === selectedOption) {
        boxColor = color(127, 29, 29); 
        strokeColor = color(239, 68, 68);
      }
    } else if (isHover) {
      boxColor = color(51, 65, 85);
      strokeColor = color(56, 189, 248);
    }

    push();
    fill(boxColor);
    stroke(strokeColor);
    strokeWeight(2);
    rect(margin, optY, cardW, optH, 10);

    fill(255);
    noStroke();
    textSize(min(width * 0.018, 15));
    text(qData.options[i], margin + 15, optY + 14, cardW - 30, optH - 10);
    pop();
  }

  // 顯示即時回饋與詳解、下一題按鈕
  if (showFeedback) {
    push();
    let isCorrect = (selectedOption === qData.answer);
    let feedbackY = startY + 4 * (optH + gap) + 5;
    
    fill(isCorrect ? color(6, 78, 59) : color(127, 29, 29, 200));
    noStroke();
    rect(margin, feedbackY, cardW, 80, 10);

    fill(isCorrect ? color(74, 222, 128) : color(248, 113, 113));
    textSize(16);
    text(isCorrect ? "✔ 回答正確！" : "✖ 回答錯誤！", margin + 15, feedbackY + 10);

    fill(255);
    textSize(13);
    text("解析：" + qData.explanation, margin + 15, feedbackY + 32, cardW - 30, 42);
    pop();

    // 「下一題」按鈕
    let nextBtnW = 180, nextBtnH = 45;
    let nextBtnX = margin + cardW - nextBtnW;
    let nextBtnY = feedbackY + 90;
    let isNextHover = mouseX > nextBtnX && mouseX < nextBtnX + nextBtnW && mouseY > nextBtnY && mouseY < nextBtnY + nextBtnH;

    push();
    fill(isNextHover ? 14 : 2, isNextHover ? 165 : 132, isNextHover ? 233 : 199);
    noStroke();
    rect(nextBtnX, nextBtnY, nextBtnW, nextBtnH, 8);

    fill(255);
    textAlign(CENTER, CENTER);
    textSize(15);
    text(currentQuestion < questions.length - 1 ? "下一題 ➔" : "查看測驗結果 ➔", nextBtnX + nextBtnW / 2, nextBtnY + nextBtnH / 2);
    pop();
  }
}

function drawResultScreen() {
  let correctCount = 0;
  for (let i = 0; i < questions.length; i++) {
    if (userAnswers[i] === questions[i].answer) {
      correctCount++;
    }
  }
  let scorePercent = Math.round((correctCount / questions.length) * 100);

  let margin = width > 768 ? width * 0.15 : 24;
  let cardW = width - (margin * 2);

  push();
  fill(56, 189, 248);
  textSize(26);
  textAlign(CENTER, TOP);
  text("測驗結果與詳解報告", width / 2, 30);

  fill(30, 41, 59);
  stroke(51, 65, 85);
  strokeWeight(2);
  rect(margin, 75, cardW, 80, 12);

  fill(255);
  textSize(18);
  textAlign(LEFT, TOP);
  text(`答對題數：${correctCount} / ${questions.length}`, margin + 25, 92);
  text(`總體答對率：${scorePercent}%`, margin + 25, 120);
  pop();

  let startY = 170;
  let itemH = 58;
  for (let i = 0; i < questions.length; i++) {
    let q = questions[i];
    let isUserCorrect = userAnswers[i] === q.answer;
    let itemY = startY + i * (itemH + 8);

    push();
    fill(isUserCorrect ? color(20, 83, 45, 100) : color(127, 29, 29, 100));
    stroke(isUserCorrect ? color(34, 197, 94) : color(239, 68, 68));
    strokeWeight(1);
    rect(margin, itemY, cardW, itemH, 8);

    fill(255);
    noStroke();
    textSize(13);
    text(`Q${i + 1}: ${q.question.substring(0, 45)}...`, margin + 12, itemY + 8, cardW - 100, 18);
    
    textSize(12);
    fill(isUserCorrect ? color(74, 222, 128) : color(248, 113, 113));
    text(isUserCorrect ? "【答對】" : "【答錯】正確答案：" + q.options[q.answer].substring(0, 2), margin + 12, itemY + 32);
    pop();
  }

  let btnW = 180, btnH = 45;
  let btnX = width / 2 - btnW / 2;
  let btnY = height - 60;
  let isHover = mouseX > btnX && mouseX < btnX + btnW && mouseY > btnY && mouseY < btnY + btnH;

  push();
  fill(isHover ? 14 : 2, isHover ? 165 : 132, isHover ? 233 : 199);
  noStroke();
  rect(btnX, btnY, btnW, btnH, 8);

  fill(255);
  textAlign(CENTER, CENTER);
  textSize(15);
  text("重新測驗", width / 2, btnY + btnH / 2);
  pop();
}

function mousePressed() {
  if (gameState === "START") {
    let btnW = 220, btnH = 60;
    let btnX = width / 2 - btnW / 2;
    let btnY = height * 0.58;
    if (mouseX > btnX && mouseX < btnX + btnW && mouseY > btnY && mouseY < btnY + btnH) {
      gameState = "QUIZ";
      currentQuestion = 0;
      userAnswers = [];
      showFeedback = false;
    }
  } else if (gameState === "QUIZ") {
    let margin = width > 768 ? width * 0.15 : 24;
    let cardW = width - (margin * 2);
    let startY = 195;
    let optH = 55;
    let gap = 12;

    // 如果已經顯示回饋，點擊「下一題」按鈕事件
    if (showFeedback) {
      let nextBtnW = 180, nextBtnH = 45;
      let feedbackY = startY + 4 * (optH + gap) + 5;
      let nextBtnX = margin + cardW - nextBtnW;
      let nextBtnY = feedbackY + 90;

      if (mouseX > nextBtnX && mouseX < nextBtnX + nextBtnW && mouseY > nextBtnY && mouseY < nextBtnY + nextBtnH) {
        nextQuestion();
      }
      return; 
    }

    // 尚未作答時點選選項
    let qData = questions[currentQuestion];
    for (let i = 0; i < qData.options.length; i++) {
      let optY = startY + i * (optH + gap);
      if (mouseX > margin && mouseX < margin + cardW && mouseY > optY && mouseY < optY + optH) {
        selectedOption = i;
        userAnswers[currentQuestion] = i;
        showFeedback = true;
      }
    }
  } else if (gameState === "RESULT") {
    let btnW = 180, btnH = 45;
    let btnX = width / 2 - btnW / 2;
    let btnY = height - 60;
    if (mouseX > btnX && mouseX < btnX + btnW && mouseY > btnY && mouseY < btnY + btnH) {
      gameState = "START";
      currentQuestion = 0;
      userAnswers = [];
    }
  }
}

function nextQuestion() {
  showFeedback = false;
  selectedOption = null;
  currentQuestion++;
  if (currentQuestion >= questions.length) {
    gameState = "RESULT";
  }
}

```
:::


---

## 學習2：網頁設定為響應式網頁

https://cfchen58.synology.me/115/week4/stage2/

**這個階段的目標：** 讓網站在電腦、平板、手機（直向與橫向）都能正常顯示，視窗大小改變時版面自動調整。
**這個階段會修改的檔案：** index.html、sketch.js

### 執行截圖

（把截圖拖曳到這裡，或貼上圖片連結）
![動畫](https://hackmd.io/_uploads/BytWvp4szg.gif)
### 第一次問 AI

```
將其作成響應式網頁
```

### 程式碼內容

:::info
:::spoiler 點開貼上學習2的程式碼
```javascript=
// 教育科技主題互動測驗系統 (p5.js 響應式 JavaScript 版本)
let questions = [
  {
    question: "在教育科技領域中，TPACK 框架將教師的專業知識分為三個核心領域，請問下列何者正確？",
    options: [
      "A. 教學知識 (PK)、心理知識 (PK)、電腦知識 (CK)",
      "B. 學科內容知識 (CK)、教學法知識 (PK)、科技知識 (TK)",
      "C. 評量知識 (AK)、資訊知識 (IK)、課程知識 (CK)",
      "D. 理論知識 (TK)、實務知識 (PK)、數位素養 (DK)"
    ],
    answer: 1,
    explanation: "TPACK 全稱為 Technological Pedagogical Content Knowledge，核心包含學科內容知識 (CK)、教學法知識 (PK) 及科技知識 (TK) 三者的交集與融合。"
  },
  {
    question: "ADDIE 教學設計模型是數位課程發展的經典架構，其五個階段的正確順序為何？",
    options: [
      "A. 分析 (Analysis) → 設計 (Design) → 開發 (Development) → 實施 (Implementation) → 評量 (Evaluation)",
      "B. 評量 (Evaluation) → 設計 (Design) → 發展 (Development) → 實施 (Implementation) → 分析 (Analysis)",
      "C. 設計 (Design) → 分析 (Analysis) → 實施 (Implementation) → 評量 (Evaluation) → 開發 (Development)",
      "D. 開發 (Development) → 評量 (Evaluation) → 分析 (Analysis) → 設計 (Design) → 實施 (Implementation)"
    ],
    answer: 0,
    explanation: "ADDIE 模型標準五階段為：分析 (Analysis)、設計 (Design)、開發 (Development)、實施 (Implementation)、評量 (Evaluation)。"
  },
  {
    question: "關於「翻轉教室 (Flipped Classroom)」教學模式的敘述，下列哪一項最具鑑別度與正確性？",
    options: [
      "A. 課堂上由老師講授核心概念，回家後由學生自主完成紙筆測驗",
      "B. 學生在家透過線上影片自主學習知識，課堂上則進行討論、協作與實作應用",
      "C. 完全不使用任何紙本教材，全面以電子白板及虛擬實境取代傳統教學",
      "D. 僅適用於高等教育之遠距線上課程，國民義務教育階段無法實施"
    ],
    answer: 1,
    explanation: "翻轉教室核心精神為「先學後教」，學生課前自主看影片吸收知識，課堂時間則留給教師引導討論、解決問題與高階思維活動。"
  },
  {
    question: "在現代 AI 適性化學習系統 (Adaptive Learning) 中，最核心的底層技術與機制通常是：",
    options: [
      "A. 隨機亂數抽取題庫，確保每位學生的題目完全不重複",
      "B. 依賴教師手動逐題設定分數權重與固定解鎖關卡",
      "C. 透過知識圖譜 (Knowledge Graph) 與即時學生反應理論 (IRT) 動態評估能力並推薦路徑",
      "D. 強制規定所有學生必須在相同時間內完成相同進度的測驗"
    ],
    answer: 2,
    explanation: "適性化學習系統利用知識圖譜與試題反應理論 (Item Response Theory)，根據學生作答表現即時診斷強弱點，動態調整下一個學習內容或難度。"
  },
  {
    question: "關於學習管理系統 (LMS，如 Moodle、Canvas、Blackboard) 的主要功能與定位，下列何者描述最為精確？",
    options: [
      "A. 專門用於取代學校實體教室的硬體設備與桌椅配置",
      "B. 提供數位化課程管理、學習歷程紀錄 (Learning Analytics)、作業繳交與師生互動的整合平台",
      "C. 僅能提供選擇題自動批改，無法支援多元作業與同儕互評功能",
      "D. 屬於雲端社群軟體，主要用於學生課外社交與娛樂互動"
    ],
    answer: 1,
    explanation: "LMS 是數位教學的中央樞紐，整合了教材派發、作業繳交、成績管理、討論區及學習分析等強大功能。"
  }
];

let currentQuestion = 0;
let userAnswers = [];
let gameState = "START"; 
let selectedOption = null; 
let showFeedback = false; 

function setup() {
  let canvas = createCanvas(windowWidth, windowHeight);
  canvas.parent(document.body);
  textAlign(LEFT, TOP);
}

function draw() {
  background(15, 23, 42); // 現代深色科技風背景

  if (gameState === "START") {
    drawStartScreen();
  } else if (gameState === "QUIZ") {
    drawQuizScreen();
  } else if (gameState === "RESULT") {
    drawResultScreen();
  }
}

// 視窗大小改變時自動調整畫布與響應比例
function windowResized() {
  resizeCanvas(windowWidth, windowHeight);
}

// 取得響應式排版尺寸與邊距
function getLayoutConfig() {
  let isMobile = width < 768;
  return {
    margin: isMobile ? 16 : width * 0.15,
    cardW: isMobile ? width - 32 : width - (width * 0.3),
    isMobile: isMobile
  };
}

// ----------------- 開始畫面 -----------------
function drawStartScreen() {
  push();
  textAlign(CENTER, CENTER);
  
  let config = getLayoutConfig();
  
  fill(56, 189, 248);
  textSize(config.isMobile ? 22 : 36);
  text("💡 教育科技 (EdTech) 互動素養測驗系統", width / 2, height * 0.28);
  
  fill(148, 163, 184);
  textSize(config.isMobile ? 13 : 18);
  text("本測驗包含 5 道具有鑑別度的教育科技核心試題\n提供即時對錯回饋與詳細觀念解析", width / 2, height * 0.38);

  let btnW = config.isMobile ? 180 : 220;
  let btnH = config.isMobile ? 50 : 60;
  let btnX = width / 2 - btnW / 2;
  let btnY = height * 0.58;
  
  let isHover = mouseX > btnX && mouseX < btnX + btnW && mouseY > btnY && mouseY < btnY + btnH;
  
  fill(isHover ? 14 : 2, isHover ? 165 : 132, isHover ? 233 : 199);
  noStroke();
  rect(btnX, btnY, btnW, btnH, 12);
  
  fill(255);
  textSize(config.isMobile ? 16 : 20);
  text("開始測驗", width / 2, btnY + btnH / 2);
  pop();
}

// ----------------- 測驗畫面 -----------------
function drawQuizScreen() {
  let config = getLayoutConfig();
  let margin = config.margin;
  let cardW = config.cardW;

  // 進度條與題號
  push();
  fill(148, 163, 184);
  textSize(config.isMobile ? 13 : 15);
  text(`題目 ${currentQuestion + 1} / ${questions.length}`, margin, config.isMobile ? 15 : 25);
  
  let barW = cardW;
  let progress = (currentQuestion + 1) / questions.length;
  let barY = config.isMobile ? 38 : 50;
  fill(30, 41, 59);
  noStroke();
  rect(margin, barY, barW, 8, 4);
  fill(56, 189, 248);
  rect(margin, barY, barW * progress, 8, 4);
  pop();

  // 題目卡片
  let qData = questions[currentQuestion];
  let qBoxY = config.isMobile ? 55 : 70;
  let qBoxH = config.isMobile ? 100 : 95;
  push();
  fill(30, 41, 59, 200);
  stroke(51, 65, 85);
  strokeWeight(2);
  rect(margin, qBoxY, cardW, qBoxH, 12);

  fill(255);
  textSize(config.isMobile ? 13 : 16);
  noStroke();
  text(qData.question, margin + 15, qBoxY + 12, cardW - 30, qBoxH - 20);
  pop();

  // 選項按鈕
  let startY = qBoxY + qBoxH + (config.isMobile ? 12 : 18);
  let optH = config.isMobile ? 50 : 55;
  let gap = config.isMobile ? 8 : 12;

  for (let i = 0; i < qData.options.length; i++) {
    let optY = startY + i * (optH + gap);
    let isHover = mouseX > margin && mouseX < margin + cardW && mouseY > optY && mouseY < optY + optH;
    
    let boxColor = color(30, 41, 59);
    let strokeColor = color(51, 65, 85);

    if (showFeedback) {
      if (i === qData.answer) {
        boxColor = color(20, 83, 45); 
        strokeColor = color(34, 197, 94);
      } else if (i === selectedOption) {
        boxColor = color(127, 29, 29); 
        strokeColor = color(239, 68, 68);
      }
    } else if (isHover) {
      boxColor = color(51, 65, 85);
      strokeColor = color(56, 189, 248);
    }

    push();
    fill(boxColor);
    stroke(strokeColor);
    strokeWeight(2);
    rect(margin, optY, cardW, optH, 10);

    fill(255);
    noStroke();
    textSize(config.isMobile ? 12 : 14);
    text(qData.options[i], margin + 12, optY + 10, cardW - 24, optH - 15);
    pop();
  }

  // 即時回饋與詳解、下一題按鈕
  if (showFeedback) {
    push();
    let isCorrect = (selectedOption === qData.answer);
    let feedbackY = startY + 4 * (optH + gap) + 4;
    let feedbackH = config.isMobile ? 85 : 75;
    
    fill(isCorrect ? color(6, 78, 59) : color(127, 29, 29, 200));
    noStroke();
    rect(margin, feedbackY, cardW, feedbackH, 10);

    fill(isCorrect ? color(74, 222, 128) : color(248, 113, 113));
    textSize(config.isMobile ? 14 : 16);
    text(isCorrect ? "✔ 回答正確！" : "✖ 回答錯誤！", margin + 12, feedbackY + 8);

    fill(255);
    textSize(config.isMobile ? 11 : 13);
    text("解析：" + qData.explanation, margin + 12, feedbackY + 28, cardW - 24, feedbackH - 32);
    pop();

    // 「下一題」按鈕
    let nextBtnW = config.isMobile ? 150 : 180;
    let nextBtnH = config.isMobile ? 40 : 45;
    let feedbackYPos = startY + 4 * (optH + gap) + 4;
    let nextBtnX = margin + cardW - nextBtnW;
    let nextBtnY = feedbackYPos + (config.isMobile ? 90 : 82);
    
    let isNextHover = mouseX > nextBtnX && mouseX < nextBtnX + nextBtnW && mouseY > nextBtnY && mouseY < nextBtnY + nextBtnH;

    push();
    fill(isNextHover ? 14 : 2, isNextHover ? 165 : 132, isNextHover ? 233 : 199);
    noStroke();
    rect(nextBtnX, nextBtnY, nextBtnW, nextBtnH, 8);

    fill(255);
    textAlign(CENTER, CENTER);
    textSize(config.isMobile ? 13 : 15);
    text(currentQuestion < questions.length - 1 ? "下一題 ➔" : "查看結果 ➔", nextBtnX + nextBtnW / 2, nextBtnY + nextBtnH / 2);
    pop();
  }
}

// ----------------- 結果畫面 -----------------
function drawResultScreen() {
  let correctCount = 0;
  for (let i = 0; i < questions.length; i++) {
    if (userAnswers[i] === questions[i].answer) {
      correctCount++;
    }
  }
  let scorePercent = Math.round((correctCount / questions.length) * 100);

  let config = getLayoutConfig();
  let margin = config.margin;
  let cardW = config.cardW;

  push();
  fill(56, 189, 248);
  textSize(config.isMobile ? 20 : 26);
  textAlign(CENTER, TOP);
  text("測驗結果與詳解報告", width / 2, config.isMobile ? 15 : 25);

  let summaryH = config.isMobile ? 65 : 75;
  fill(30, 41, 59);
  stroke(51, 65, 85);
  strokeWeight(2);
  rect(margin, config.isMobile ? 45 : 65, cardW, summaryH, 12);

  fill(255);
  textSize(config.isMobile ? 13 : 17);
  textAlign(LEFT, TOP);
  text(`答對題數：${correctCount} / ${questions.length}    |    總體答對率：${scorePercent}%`, margin + 20, config.isMobile ? 60 : 85);
  pop();

  let startY = config.isMobile ? 120 : 155;
  let itemH = config.isMobile ? 48 : 55;
  for (let i = 0; i < questions.length; i++) {
    let q = questions[i];
    let isUserCorrect = userAnswers[i] === q.answer;
    let itemY = startY + i * (itemH + 6);

    push();
    fill(isUserCorrect ? color(20, 83, 45, 100) : color(127, 29, 29, 100));
    stroke(isUserCorrect ? color(34, 197, 94) : color(239, 68, 68));
    strokeWeight(1);
    rect(margin, itemY, cardW, itemH, 8);

    fill(255);
    noStroke();
    textSize(config.isMobile ? 11 : 13);
    text(`Q${i + 1}: ${q.question.substring(0, config.isMobile ? 32 : 50)}...`, margin + 10, itemY + 6, cardW - 80, 16);
    
    textSize(config.isMobile ? 11 : 12);
    fill(isUserCorrect ? color(74, 222, 128) : color(248, 113, 113));
    text(isUserCorrect ? "【答對】" : "【答錯】正確答案：" + q.options[q.answer].substring(0, 2), margin + 10, itemY + 26);
    pop();
  }

  let btnW = config.isMobile ? 150 : 180;
  let btnH = config.isMobile ? 40 : 45;
  let btnX = width / 2 - btnW / 2;
  let btnY = height - (config.isMobile ? 50 : 60);
  let isHover = mouseX > btnX && mouseX < btnX + btnW && mouseY > btnY && mouseY < btnY + btnH;

  push();
  fill(isHover ? 14 : 2, isHover ? 165 : 132, isHover ? 233 : 199);
  noStroke();
  rect(btnX, btnY, btnW, btnH, 8);

  fill(255);
  textAlign(CENTER, CENTER);
  textSize(config.isMobile ? 13 : 15);
  text("重新測驗", width / 2, btnY + btnH / 2);
  pop();
}

// ----------------- 滑鼠 / 觸控點擊互動 -----------------
function mousePressed() {
  let config = getLayoutConfig();
  let margin = config.margin;
  let cardW = config.cardW;

  if (gameState === "START") {
    let btnW = config.isMobile ? 180 : 220;
    let btnH = config.isMobile ? 50 : 60;
    let btnX = width / 2 - btnW / 2;
    let btnY = height * 0.58;
    if (mouseX > btnX && mouseX < btnX + btnW && mouseY > btnY && mouseY < btnY + btnH) {
      gameState = "QUIZ";
      currentQuestion = 0;
      userAnswers = [];
      showFeedback = false;
    }
  } else if (gameState === "QUIZ") {
    let qBoxY = config.isMobile ? 55 : 70;
    let qBoxH = config.isMobile ? 100 : 95;
    let startY = qBoxY + qBoxH + (config.isMobile ? 12 : 18);
    let optH = config.isMobile ? 50 : 55;
    let gap = config.isMobile ? 8 : 12;

    // 如果已顯示回饋，檢查是否點擊「下一題」按鈕
    if (showFeedback) {
      let nextBtnW = config.isMobile ? 150 : 180;
      let nextBtnH = config.isMobile ? 40 : 45;
      let feedbackYPos = startY + 4 * (optH + gap) + 4;
      let nextBtnX = margin + cardW - nextBtnW;
      let nextBtnY = feedbackYPos + (config.isMobile ? 90 : 82);

      if (mouseX > nextBtnX && mouseX < nextBtnX + nextBtnW && mouseY > nextBtnY && mouseY < nextBtnY + nextBtnH) {
        nextQuestion();
      }
      return; 
    }

    // 點選選項
    let qData = questions[currentQuestion];
    for (let i = 0; i < qData.options.length; i++) {
      let optY = startY + i * (optH + gap);
      if (mouseX > margin && mouseX < margin + cardW && mouseY > optY && mouseY < optY + optH) {
        selectedOption = i;
        userAnswers[currentQuestion] = i;
        showFeedback = true;
      }
    }
  } else if (gameState === "RESULT") {
    let btnW = config.isMobile ? 150 : 180;
    let btnH = config.isMobile ? 40 : 45;
    let btnX = width / 2 - btnW / 2;
    let btnY = height - (config.isMobile ? 50 : 60);
    if (mouseX > btnX && mouseX < btnX + btnW && mouseY > btnY && mouseY < btnY + btnH) {
      gameState = "START";
      currentQuestion = 0;
      userAnswers = [];
    }
  }
}

function nextQuestion() {
  showFeedback = false;
  selectedOption = null;
  currentQuestion++;
  if (currentQuestion >= questions.length) {
    gameState = "RESULT";
  }
}

```
:::


---

## 學習3：設定嵌入 Google 字型，網頁文字採用這些字型

https://cfchen58.synology.me/115/week4/stage3/

**這個階段的目標：** 從 Google Fonts 嵌入繁體中文字型，並讓畫布上的題目與選項文字使用這些字型。
**這個階段會修改的檔案：** index.html、sketch.js

### 執行截圖

（把截圖拖曳到這裡，或貼上圖片連結）

![學習3截圖](請貼上截圖)

### 第一次問 AI

```tex!
（逐字貼上你第一次問 AI 的提示詞）
```

### 第二次問 AI

```tex!
（逐字貼上你第二次問 AI 的提示詞）
```

### 第三次問 AI

```tex!
（逐字貼上你第三次問 AI 的提示詞）
```

### 程式碼內容

:::info
:::spoiler 點開貼上學習3的程式碼
```javascript=
//學習3程式碼所在

```
:::


---

## 學習4：設定題庫並抽題顯示題目網頁（CSV 檔案）

https://cfchen58.synology.me/115/week4/stage4/

**這個階段的目標：** 把題目移到 questions.csv，網站讀取題庫後每次隨機抽出 5 題。
**這個階段會修改的檔案：** index.html、sketch.js、questions.csv

### 執行截圖

（把截圖拖曳到這裡，或貼上圖片連結）

![學習4截圖](請貼上截圖)

### 第一次問 AI

```tex!
（逐字貼上你第一次問 AI 的提示詞）
```

### 第二次問 AI

```tex!
（逐字貼上你第二次問 AI 的提示詞）
```

### 第三次問 AI

```tex!
（逐字貼上你第三次問 AI 的提示詞）
```

### 程式碼內容

:::info
:::spoiler 點開貼上學習4的程式碼
```javascript=
//學習4程式碼所在

```
:::


---

## 學習5：利用 Google Sheets 當題庫

https://cfchen58.synology.me/115/week4/stage5/

**這個階段的目標：** 把題庫放在 Google 試算表，網站直接讀取，老師改試算表，網站題目就跟著更新。
**這個階段會修改的檔案：** index.html、sketch.js（questions.csv 當備用題庫）

### 執行截圖

（把截圖拖曳到這裡，或貼上圖片連結）

![學習5截圖](請貼上截圖)

### 第一次問 AI

```tex!
（逐字貼上你第一次問 AI 的提示詞）
```

### 第二次問 AI

```tex!
（逐字貼上你第二次問 AI 的提示詞）
```

### 第三次問 AI

```tex!
（逐字貼上你第三次問 AI 的提示詞）
```

### 程式碼內容

:::info
:::spoiler 點開貼上學習5的程式碼
```javascript=
//學習5程式碼所在

```
:::


---

## 我的心得

這五個學習中，哪一個最困難？你是怎麼解決的？（請寫出實際發生的事）

＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿
