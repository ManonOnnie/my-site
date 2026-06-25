<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>일본어 친구 선생님 · Manon</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;700&family=Noto+Sans:wght@300;400;700&family=Cormorant+Garamond:ital,wght@0,300;1,300;1,400&display=swap" rel="stylesheet">
<style>
* { margin: 0; padding: 0; box-sizing: border-box; }
body {
  background: #faf6f0;
  color: #2a1f1a;
  font-family: 'Noto Sans KR', 'Noto Sans', -apple-system, sans-serif;
  font-weight: 300;
  line-height: 1.8;
  word-break: keep-all;
  overflow-x: hidden;
}

/* LANG SWITCHER */
.lang-bar {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  background: #fff;
  border-bottom: 1px solid #f2d4c8;
  padding: 8px 24px;
  display: flex;
  justify-content: flex-end;
  gap: 8px;
}
.lang-btn {
  background: none;
  border: 1.5px solid #f2d4c8;
  border-radius: 20px;
  padding: 4px 14px;
  font-size: 12px;
  cursor: pointer;
  font-family: 'Noto Sans KR', sans-serif;
  color: #8a6f68;
  transition: all 0.2s;
}
.lang-btn.active {
  background: #c9736a;
  border-color: #c9736a;
  color: white;
}
body { padding-top: 40px; }

/* NOTICE BOX */
.notice-box {
  background: #fff8f6;
  border: 1px solid #f2d4c8;
  border-radius: 12px;
  padding: 20px 24px;
  margin-bottom: 24px;
}
.notice-title {
  font-size: 12px;
  font-weight: 700;
  color: #c9736a;
  margin-bottom: 12px;
  text-transform: uppercase;
  letter-spacing: 1px;
}
.notice-langs { display: flex; flex-direction: column; gap: 8px; }
.notice-lang { font-size: 12px; color: #8a6f68; display: flex; gap: 8px; align-items: flex-start; }
.notice-lang::before { content: '·'; color: #c9736a; flex-shrink: 0; }

.fade { opacity: 0; transform: translateY(24px); transition: opacity 0.7s ease, transform 0.7s ease; }
.fade.d1 { transition-delay: 0.1s; }
.fade.d2 { transition-delay: 0.25s; }
.fade.d3 { transition-delay: 0.4s; }
.fade.d4 { transition-delay: 0.55s; }
.fade.d5 { transition-delay: 0.7s; }
.fade.visible { opacity: 1; transform: translateY(0); }

.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 60px 24px;
  background: linear-gradient(160deg, #fdf0ea 0%, #faf6f0 50%, #f5ede8 100%);
  position: relative;
  overflow: hidden;
}
.hero::before {
  content: '日';
  position: absolute;
  font-size: 55vw;
  color: rgba(201,115,106,0.05);
  font-family: 'Cormorant Garamond', serif;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%);
  pointer-events: none;
  line-height: 1;
}
.hero-tag { font-size: 12px; color: #c9736a; margin-bottom: 18px; font-weight: 400; }
.hero h1 {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(44px, 11vw, 80px);
  font-weight: 300;
  font-style: italic;
  color: #2a1f1a;
  line-height: 1.2;
  margin-bottom: 20px;
}
.hero-catch { font-size: clamp(14px, 3vw, 17px); color: #2a1f1a; font-weight: 400; margin-bottom: 10px; }
.hero-sub { font-size: 13px; color: #8a6f68; margin-bottom: 36px; line-height: 2; }
.badges { display: flex; flex-wrap: wrap; gap: 8px; justify-content: center; margin-bottom: 28px; }
.badge {
  background: #fff;
  border: 1.5px solid #c9736a;
  padding: 7px 16px;
  border-radius: 24px;
  font-size: 12px;
  color: #c9736a;
  font-weight: 400;
  white-space: nowrap;
}
.hero-cta {
  display: inline-block;
  background: #c9736a;
  color: white;
  padding: 14px 30px;
  border-radius: 30px;
  font-size: 14px;
  text-decoration: none;
  font-weight: 400;
  transition: opacity 0.2s;
}
.hero-cta:hover { opacity: 0.85; }

.wrap { padding: 72px 24px; max-width: 640px; margin: 0 auto; }
.sec-label { font-size: 11px; color: #c9a96e; font-weight: 700; margin-bottom: 8px; text-transform: uppercase; }
.sec-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(22px, 5vw, 32px);
  font-weight: 300;
  font-style: italic;
  color: #2a1f1a;
  margin-bottom: 24px;
  line-height: 1.3;
}

.about-box { background: #fff; border: 1px solid #f2d4c8; border-radius: 16px; padding: 28px; }
.about-main { font-size: 15px; color: #2a1f1a; font-weight: 400; line-height: 2; margin-bottom: 20px; padding-bottom: 20px; border-bottom: 1px solid #f2d4c8; }
.about-main em { font-style: normal; color: #c9736a; font-weight: 700; }
.about-p { font-size: 13px; color: #8a6f68; line-height: 2; }
.about-p + .about-p { margin-top: 8px; }
.tips { display: flex; flex-direction: column; gap: 10px; margin-top: 16px; }
.tip { background: #faf6f0; border-left: 3px solid #f2d4c8; padding: 10px 14px; border-radius: 0 8px 8px 0; }
.tip-lbl { font-size: 11px; color: #c9a96e; font-weight: 700; display: block; margin-bottom: 3px; }
.tip-txt { font-size: 13px; color: #2a1f1a; font-style: italic; }

.cat-div {
  font-size: 12px; color: #8a6f68; font-weight: 700; text-transform: uppercase;
  margin: 28px 0 14px; padding-bottom: 10px; border-bottom: 2px solid #f2d4c8;
  display: flex; align-items: center; gap: 8px;
}

/* COURSE TABLE */
.course-table { width: 100%; border-collapse: collapse; margin-bottom: 16px; }
.course-table th {
  background: #faf6f0;
  padding: 10px 12px;
  font-size: 11px;
  font-weight: 700;
  color: #8a6f68;
  text-align: center;
  border: 1px solid #f2d4c8;
}
.course-table th.plan-name { text-align: left; }
.course-table td {
  padding: 12px;
  font-size: 13px;
  border: 1px solid #f2d4c8;
  text-align: center;
  background: #fff;
}
.course-table td.plan-info { text-align: left; }
.plan-title { font-weight: 700; color: #2a1f1a; font-size: 14px; margin-bottom: 2px; }
.plan-subtitle { font-size: 11px; color: #8a6f68; }
.price-cell { font-weight: 700; color: #c9736a; }
.price-original { font-size: 10px; color: #8a6f68; text-decoration: line-through; display: block; }
.price-save { font-size: 10px; color: #c9736a; display: block; }
.popular-row td { background: linear-gradient(135deg, #fff 0%, #fdf0ea 100%); }
.popular-badge {
  display: inline-block;
  background: #c9736a;
  color: white;
  font-size: 9px;
  font-weight: 700;
  padding: 2px 6px;
  border-radius: 4px;
  margin-left: 6px;
}

.plan-features {
  background: #faf6f0;
  border-radius: 12px;
  padding: 16px 18px;
  margin-bottom: 16px;
}
.plan-features-title { font-size: 12px; font-weight: 700; color: #c9a96e; margin-bottom: 10px; text-transform: uppercase; }
.plan-feature { font-size: 13px; color: #2a1f1a; display: flex; gap: 8px; margin-bottom: 6px; }
.plan-feature::before { content: '✓'; color: #c9736a; flex-shrink: 0; }

.policy-box {
  background: #faf6f0;
  border: 1px solid #f2d4c8;
  border-radius: 12px;
  padding: 18px;
  margin-top: 16px;
}
.policy-title { font-size: 12px; font-weight: 700; color: #c9a96e; margin-bottom: 10px; text-transform: uppercase; }
.policy-list { display: flex; flex-direction: column; gap: 6px; }
.policy-item { font-size: 12px; color: #8a6f68; display: flex; gap: 8px; }
.policy-item::before { content: '·'; color: #c9736a; flex-shrink: 0; }

.rules { display: flex; flex-direction: column; gap: 12px; }
.rule { display: flex; gap: 14px; align-items: flex-start; padding: 16px 18px; background: #fff; border: 1px solid #f2d4c8; border-radius: 12px; }
.rule-num { font-family: 'Cormorant Garamond', serif; font-size: 24px; font-style: italic; color: #f2d4c8; line-height: 1; flex-shrink: 0; width: 28px; }
.rule-title { font-size: 14px; font-weight: 700; color: #2a1f1a; margin-bottom: 4px; }
.rule-desc { font-size: 13px; color: #8a6f68; line-height: 1.7; }

.pay-box { background: #fff; border: 1px solid #f2d4c8; border-radius: 16px; padding: 24px; }
.pay-main { font-size: 15px; color: #2a1f1a; font-weight: 400; line-height: 2; margin-bottom: 16px; padding-bottom: 16px; border-bottom: 1px solid #f2d4c8; }
.pay-main em { font-style: normal; color: #c9736a; font-weight: 700; }
.pay-sub { font-size: 13px; color: #8a6f68; line-height: 2; }
.pay-step { background: #faf6f0; border-left: 3px solid #f2d4c8; padding: 10px 14px; border-radius: 0 8px 8px 0; margin-top: 14px; font-size: 13px; color: #2a1f1a; font-style: italic; }

.flow { display: flex; flex-direction: column; position: relative; }
.flow::before { content: ''; position: absolute; left: 20px; top: 40px; bottom: 40px; width: 1px; background: linear-gradient(to bottom, #f2d4c8, transparent); }
.flow-step { display: flex; gap: 18px; align-items: flex-start; padding: 12px 0; }
.flow-dot { width: 40px; height: 40px; border-radius: 50%; background: #fff; border: 2px solid #f2d4c8; display: flex; align-items: center; justify-content: center; font-size: 16px; flex-shrink: 0; position: relative; z-index: 1; }
.flow-name { font-size: 14px; font-weight: 700; color: #2a1f1a; margin-bottom: 2px; }
.flow-desc { font-size: 13px; color: #8a6f68; }

.review { background: #fff; border: 1px solid #f2d4c8; border-radius: 16px; padding: 22px; margin-bottom: 14px; }
.review-top { display: flex; align-items: center; gap: 12px; margin-bottom: 12px; }
.review-name { font-weight: 700; font-size: 14px; }
.review-tag { font-size: 11px; color: #8a6f68; }
.review-text { font-size: 13px; color: #2a1f1a; line-height: 2; }

.faq { display: flex; flex-direction: column; gap: 10px; }
.faq-item { background: #fff; border: 1px solid #f2d4c8; border-radius: 12px; overflow: hidden; }
.faq-q { width: 100%; background: none; border: none; padding: 16px 18px; display: flex; justify-content: space-between; align-items: center; cursor: pointer; text-align: left; font-family: 'Noto Sans KR', sans-serif; }
.faq-q-text { font-size: 14px; font-weight: 700; color: #2a1f1a; }
.faq-arrow { font-size: 14px; color: #c9736a; transition: transform 0.3s; flex-shrink: 0; }
.faq-a { max-height: 0; overflow: hidden; transition: max-height 0.35s ease; }
.faq-a.open { max-height: 200px; }
.faq-a-inner { padding: 0 18px 16px; font-size: 13px; color: #8a6f68; line-height: 1.9; border-top: 1px solid #f2d4c8; padding-top: 12px; }

.cta-box { background: linear-gradient(135deg, #fdf0ea, #faf6f0); border: 1px solid #f2d4c8; border-radius: 16px; padding: 28px; text-align: center; }
.cta-box p { font-size: 14px; color: #8a6f68; line-height: 2; margin-bottom: 20px; }
.cta-box strong { color: #c9736a; }
.cta-btn { display: inline-block; background: #c9736a; color: white; padding: 14px 30px; border-radius: 30px; font-size: 14px; text-decoration: none; font-weight: 400; transition: opacity 0.2s; }
.cta-btn:hover { opacity: 0.85; }

footer { text-align: center; padding: 32px 24px 48px; font-size: 12px; color: #f2d4c8; }

/* LANG DISPLAY */
.ko-content { display: block; }
.en-content { display: none; }
body.en .ko-content { display: none; }
body.en .en-content { display: block; }
</style>
</head>
<body>

<!-- LANG SWITCHER -->
<div class="lang-bar">
  <button class="lang-btn active" onclick="setLang('ko')">🇰🇷 한국어</button>
  <button class="lang-btn" onclick="setLang('en')">🇺🇸 English</button>
</div>

<!-- ========== KOREAN ========== -->
<div class="ko-content">

<div class="hero">
  <p class="hero-tag fade d1">일본어 친구 선생님 · 日本語お友達先生</p>
  <h1 class="fade d2">학습이 아니라<br>몰입이에요</h1>
  <p class="hero-catch fade d3">수업 내내 일본어만 써요.<br>자연스럽게 귀가 열리고, 뇌가 스스로 따라와요.</p>
  <p class="hero-sub fade d3">억지로 외우는 시간 말고 —<br>즐기면서 일본어가 쌓이는 시간을 만들어드릴게요 🌸</p>
  <div class="badges fade d4">
    <span class="badge">오사카 거주</span>
    <span class="badge">2002년생</span>
    <span class="badge">한국 1년 유학</span>
    <span class="badge">애니·만화 좋아해요</span>
  </div>
  <a href="https://calendly.com/mom-0730-mom/30min" target="_blank" class="hero-cta fade d5">무료 카운슬링 예약하기 🌸</a>
</div>

<div class="wrap">
  <p class="sec-label fade">About</p>
  <p class="sec-title fade">이런 사람이에요</p>
  <div class="about-box fade">
    <p class="about-main">수업 중에는 <em>계속 일본어로만 말해요.</em><br>처음엔 어색해도 괜찮아요.<br>일본어가 계속 귀에 들어오면 뇌가 알아서 따라가기 시작해요.<br>억지로 머릿속에 쑤셔넣는 게 아니라 — 즐기면서 자연스럽게.</p>
    <p class="about-p">시험 대비용 문법 수업이 아니에요. <em style="font-style:normal;color:#c9736a;font-weight:700">진짜 회화 중심</em>이에요.</p>
    <p class="about-p">이상한 일본어를 쓰면 바로 수정해드려요. 오래된 습관이나 어색한 표현도 자연스럽게 고쳐나가면서 점점 유창한 일본어로 만들어드릴게요.</p>
    <div class="tips">
      <div class="tip"><span class="tip-lbl">이런 분께 추천</span><p class="tip-txt">애니메이션·만화 좋아하고 일본어에 관심 생긴 분 🎌 저도 한국에서 1년 살았어요. 한국 문화 너무 좋아하는 일본인이에요 😊</p></div>
      <div class="tip"><span class="tip-lbl">이런 분은 비추</span><p class="tip-txt">JLPT 시험 대비가 목표라면 저보다 잘 맞는 선생님이 있어요. 저는 생활 회화 전문이에요.</p></div>
      <div class="tip"><span class="tip-lbl">솔직한 한 마디</span><p class="tip-txt">굳어버린 잘못된 일본어 표현, 저랑 같이 고쳐나가요. 유창한 일본어, 생각보다 가까워요.</p></div>
    </div>
  </div>
</div>

<div class="wrap" style="padding-top:0">
  <p class="sec-label fade">Services & Pricing</p>
  <p class="sec-title fade">코스 & 요금</p>

  <!-- ミニ -->
  <div class="cat-div fade">🗣️ 미니 레슨 · 15분</div>
  <div class="fade">
    <div class="plan-features">
      <div class="plan-features-title">포함 내용</div>
      <div class="plan-feature">자유 회화 위주</div>
      <div class="plan-feature">이상한 표현은 바로 수정</div>
      <div class="plan-feature">가볍게 일본어 입을 트고 싶은 분께</div>
    </div>
    <table class="course-table">
      <tr>
        <th>횟수</th>
        <th>정가</th>
        <th>월정액</th>
        <th>할인</th>
      </tr>
      <tr>
        <td>월 4회</td>
        <td>₩40,000</td>
        <td class="price-cell">₩38,000</td>
        <td>5% OFF</td>
      </tr>
      <tr>
        <td>월 8회</td>
        <td>₩80,000</td>
        <td class="price-cell">₩72,000</td>
        <td>10% OFF</td>
      </tr>
      <tr class="popular-row">
        <td>월 12회 <span class="popular-badge">BEST</span></td>
        <td>₩120,000</td>
        <td class="price-cell">₩102,000</td>
        <td>15% OFF</td>
      </tr>
    </table>
  </div>

  <!-- スタンダード -->
  <div class="cat-div fade">💬 스탠다드 레슨 · 30분 · 서포트 포함</div>
  <div class="fade">
    <div class="plan-features">
      <div class="plan-features-title">포함 내용</div>
      <div class="plan-feature">자유 회화 · 주제 자유 선택</div>
      <div class="plan-feature">수업 후 틀린 표현 TOP3 DM 전송</div>
      <div class="plan-feature">다음 수업 포인트 제시</div>
      <div class="plan-feature">첫 수업 무료 카운슬링 15분 포함</div>
    </div>
    <table class="course-table">
      <tr>
        <th>횟수</th>
        <th>정가</th>
        <th>월정액</th>
        <th>할인</th>
      </tr>
      <tr>
        <td>월 4회</td>
        <td>₩60,000</td>
        <td class="price-cell">₩57,000</td>
        <td>5% OFF</td>
      </tr>
      <tr>
        <td>월 8회</td>
        <td>₩120,000</td>
        <td class="price-cell">₩108,000</td>
        <td>10% OFF</td>
      </tr>
      <tr class="popular-row">
        <td>월 12회 <span class="popular-badge">BEST</span></td>
        <td>₩180,000</td>
        <td class="price-cell">₩153,000</td>
        <td>15% OFF</td>
      </tr>
    </table>
  </div>

  <!-- 授業型 -->
  <div class="cat-div fade">📖 수업형 레슨 · 30분</div>
  <div class="fade">
    <div class="plan-features">
      <div class="plan-features-title">포함 내용</div>
      <div class="plan-feature">목표 설정 후 맞춤 커리큘럼</div>
      <div class="plan-feature">복습 자료 매 수업 후 전송</div>
      <div class="plan-feature">숙제 있어요 (선택)</div>
      <div class="plan-feature">체계적으로 배우고 싶은 분께</div>
    </div>
    <table class="course-table">
      <tr>
        <th>횟수</th>
        <th>정가</th>
        <th>월정액</th>
        <th>할인</th>
      </tr>
      <tr>
        <td>월 4회</td>
        <td>₩80,000</td>
        <td class="price-cell">₩76,000</td>
        <td>5% OFF</td>
      </tr>
      <tr>
        <td>월 8회</td>
        <td>₩160,000</td>
        <td class="price-cell">₩144,000</td>
        <td>10% OFF</td>
      </tr>
      <tr class="popular-row">
        <td>월 12회 <span class="popular-badge">BEST</span></td>
        <td>₩240,000</td>
        <td class="price-cell">₩204,000</td>
        <td>15% OFF</td>
      </tr>
    </table>
  </div>

  <div class="policy-box fade">
    <div class="policy-title">📋 코스 이용 안내</div>
    <div class="policy-list">
      <div class="policy-item">1개월 단위로 자동 갱신돼요.</div>
      <div class="policy-item">해지는 다음 달 말까지 말씀해 주시면 그 다음 달부터 적용돼요.</div>
      <div class="policy-item">코스 도중 횟수 변경도 상담 후 가능해요.</div>
    </div>
  </div>
</div>

<div class="wrap" style="padding-top:0">
  <p class="sec-label fade">Rules</p>
  <p class="sec-title fade">약속해요 🤝</p>
  <div class="rules">
    <div class="rule fade"><div class="rule-num">1</div><div><div class="rule-title">수업은 기본 일본어로</div><p class="rule-desc">처음엔 어색해도 괜찮아요. 자연스럽게 익혀가요!</p></div></div>
    <div class="rule fade"><div class="rule-num">2</div><div><div class="rule-title">이상한 일본어는 바로 수정</div><p class="rule-desc">친구처럼 자연스럽게 알려드려요 😊</p></div></div>
    <div class="rule fade"><div class="rule-num">3</div><div><div class="rule-title">취소 · 변경</div><p class="rule-desc">5일 전 24시까지 무료 취소 · 변경<br>5일 이내 취소는 환불 없음, 변경은 무료</p></div></div>
    <div class="rule fade"><div class="rule-num">4</div><div><div class="rule-title">채팅 답장은 24시간 이내</div><p class="rule-desc">급하면 미리 알려주세요.</p></div></div>
    <div class="rule fade"><div class="rule-num">5</div><div><div class="rule-title">첫 수업은 무료 카운슬링 포함</div><p class="rule-desc">맞지 않으면 솔직하게 말해드려요.</p></div></div>
  </div>
</div>

<div class="wrap" style="padding-top:0">
  <p class="sec-label fade">Payment</p>
  <p class="sec-title fade">결제 방법 💳</p>
  <div class="pay-box fade">
    <p class="pay-main">결제는 <em>Stripe</em>를 이용해요.<br>한국 신용카드로 간편하게 결제할 수 있어요 🙂</p>
    <p class="pay-sub">예약 확정 후 DM으로 결제 링크를 보내드려요. 별도 앱 설치 불필요!</p>
    <div class="pay-step">① 예약 확정 → ② DM으로 결제 링크 수령 → ③ 카드 정보 입력 → ④ 결제 완료 🎉</div>
  </div>
</div>

<div class="wrap" style="padding-top:0">
  <p class="sec-label fade">How to Start</p>
  <p class="sec-title fade">시작 방법</p>
  <div class="flow">
    <div class="flow-step fade"><div class="flow-dot">👋</div><div><div class="flow-name">DM으로 연락</div><p class="flow-desc">어떤 서비스를 원하는지 편하게 메시지 주세요</p></div></div>
    <div class="flow-step fade"><div class="flow-dot">💭</div><div><div class="flow-name">무료 카운슬링 15분</div><p class="flow-desc">현재 실력, 목표, 원하는 스타일 이야기해요</p></div></div>
    <div class="flow-step fade"><div class="flow-dot">💳</div><div><div class="flow-name">결제 & 일정 확정</div><p class="flow-desc">편한 날짜 정하고 결제하면 끝</p></div></div>
    <div class="flow-step fade"><div class="flow-dot">🌸</div><div><div class="flow-name">스타트!</div><p class="flow-desc">첫 수업 시작 🎉</p></div></div>
  </div>
</div>

<div class="wrap" style="padding-top:0">
  <p class="sec-label fade">Reviews</p>
  <p class="sec-title fade">수강생 이야기 💬</p>
  <div class="review fade">
    <div class="review-top">
      <svg width="44" height="44" viewBox="0 0 44 44" fill="none"><circle cx="22" cy="22" r="22" fill="#fdf0ea"/><circle cx="22" cy="17" r="7" fill="#e8b4a0"/><path d="M8 38c0-7.732 6.268-14 14-14s14 6.268 14 14" fill="#e8b4a0"/><circle cx="19" cy="16" r="1.2" fill="#5a3a2a"/><circle cx="25" cy="16" r="1.2" fill="#5a3a2a"/><path d="M19.5 20c0.8 1 3.2 1 4 0" stroke="#5a3a2a" stroke-width="1" stroke-linecap="round"/></svg>
      <div><div class="review-name">지유 (23)</div><div class="review-tag">미니 레슨</div></div>
    </div>
    <p class="review-text">"애니메이션 보다가 일본어 공부하고 싶었는데 혼자 하기엔 너무 막막했어요. 부담 없는 가격에 가볍게 시작할 수 있어서 진짜 좋았어요!"</p>
  </div>
  <div class="review fade">
    <div class="review-top">
      <svg width="44" height="44" viewBox="0 0 44 44" fill="none"><circle cx="22" cy="22" r="22" fill="#fdf0ea"/><circle cx="22" cy="17" r="7" fill="#c4907a"/><path d="M8 38c0-7.732 6.268-14 14-14s14 6.268 14 14" fill="#c4907a"/><circle cx="19" cy="16" r="1.2" fill="#3a2010"/><circle cx="25" cy="16" r="1.2" fill="#3a2010"/><path d="M19.5 20.5c0.8 1.2 3.2 1.2 4 0" stroke="#3a2010" stroke-width="1" stroke-linecap="round"/></svg>
      <div><div class="review-name">민서 (26)</div><div class="review-tag">스탠다드 레슨</div></div>
    </div>
    <p class="review-text">"수업 전체가 일본어로 진행되니까 자연스럽게 귀에 들어오는 느낌이 너무 좋아요 😊"</p>
  </div>
  <div class="review fade">
    <div class="review-top">
      <svg width="44" height="44" viewBox="0 0 44 44" fill="none"><circle cx="22" cy="22" r="22" fill="#fdf0ea"/><circle cx="22" cy="17" r="7" fill="#d4a882"/><path d="M8 38c0-7.732 6.268-14 14-14s14 6.268 14 14" fill="#d4a882"/><circle cx="19" cy="16" r="1.2" fill="#3a2010"/><circle cx="25" cy="16" r="1.2" fill="#3a2010"/><path d="M19.5 20c0.8 1 3.2 1 4 0" stroke="#3a2010" stroke-width="1" stroke-linecap="round"/></svg>
      <div><div class="review-name">수진 (24)</div><div class="review-tag">월 4회 코스</div></div>
    </div>
    <p class="review-text">"일본에 워홀 중인데, 저렴하게 제 페이스에 맞춰서 공부하고 싶었어요. 모르는 사이에 굳어버린 발음이나 이상한 표현들을 자연스럽게 고쳐주셔서 정말 유창해진 느낌이에요!"</p>
  </div>
</div>

<div class="wrap" style="padding-top:0">
  <p class="sec-label fade">FAQ</p>
  <p class="sec-title fade">자주 묻는 질문 ❓</p>
  <div class="faq fade">
    <div class="faq-item">
      <button class="faq-q" onclick="toggleFaq(this)"><span class="faq-q-text">일본어 완전 초보도 괜찮아요?</span><span class="faq-arrow">▼</span></button>
      <div class="faq-a"><div class="faq-a-inner">물론이에요! 히라가나를 모르는 분도 환영해요 🌸</div></div>
    </div>
    <div class="faq-item">
      <button class="faq-q" onclick="toggleFaq(this)"><span class="faq-q-text">수업은 어떻게 진행돼요?</span><span class="faq-arrow">▼</span></button>
      <div class="faq-a"><div class="faq-a-inner">Google Meet로 진행해요. 예약 확정 후 링크가 자동으로 전송돼요.</div></div>
    </div>
    <div class="faq-item">
      <button class="faq-q" onclick="toggleFaq(this)"><span class="faq-q-text">코스 해지는 어떻게 해요?</span><span class="faq-arrow">▼</span></button>
      <div class="faq-a"><div class="faq-a-inner">다음 달 말까지 말씀해 주시면 그 다음 달부터 취소 적용돼요.</div></div>
    </div>
    <div class="faq-item">
      <button class="faq-q" onclick="toggleFaq(this)"><span class="faq-q-text">결제는 어떻게 해요?</span><span class="faq-arrow">▼</span></button>
      <div class="faq-a"><div class="faq-a-inner">Stripe로 한국 카드 결제 가능해요. 예약 확정 후 DM으로 결제 링크를 보내드려요.</div></div>
    </div>
    <div class="faq-item">
      <button class="faq-q" onclick="toggleFaq(this)"><span class="faq-q-text">선생님은 한국어 할 수 있어요?</span><span class="faq-arrow">▼</span></button>
      <div class="faq-a"><div class="faq-a-inner">조금은 할 수 있어요 😊 한국에서 1년 살았어요. 하지만 수업은 기본적으로 일본어로 진행해요.</div></div>
    </div>
    <div class="faq-item">
      <button class="faq-q" onclick="toggleFaq(this)"><span class="faq-q-text">JLPT 시험 대비도 해줘요?</span><span class="faq-arrow">▼</span></button>
      <div class="faq-a"><div class="faq-a-inner">저는 생활 회화 전문이에요. JLPT 대비가 목표라면 저보다 잘 맞는 선생님이 있을 수 있어요 🙏</div></div>
    </div>
  </div>
</div>

<div class="wrap" style="padding-top:0; padding-bottom:80px;">
  <div class="cta-box fade">
    <p>궁금한 점은 언제든지 DM으로 편하게 물어보세요 🌸<br>첫 카운슬링 <strong>15분은 무료</strong>예요.</p>
    <a href="https://calendly.com/mom-0730-mom/30min" target="_blank" class="cta-btn">무료 카운슬링 예약하기 🌸</a>
  </div>
</div>

<footer>✦ 일본어 친구 선생님 · Manon · Osaka, Japan ✦</footer>

</div><!-- end ko-content -->


<!-- ========== ENGLISH ========== -->
<div class="en-content">

<div class="hero">
  <p class="hero-tag fade d1">Japanese Friend Teacher · 日本語お友達先生</p>
  <h1 class="fade d2">Not studying —<br>immersing.</h1>
  <p class="hero-catch fade d3">We speak only Japanese throughout the lesson.<br>Your ears open naturally, and your brain follows.</p>
  <p class="hero-sub fade d3">No more forcing yourself to memorize —<br>let's make time for Japanese to build up naturally 🌸</p>
  <div class="badges fade d4">
    <span class="badge">Based in Osaka</span>
    <span class="badge">Born 2002</span>
    <span class="badge">1 year in Korea</span>
    <span class="badge">Anime & Manga lover</span>
  </div>
  <a href="https://calendly.com/mom-0730-mom/30min" target="_blank" class="hero-cta fade d5">Book a Free Counseling 🌸</a>
</div>

<div class="wrap">
  <p class="sec-label fade">Important Notice</p>
  <p class="sec-title fade">Please read before booking 📋</p>
  <div class="notice-box fade">
    <div class="notice-title">⚠️ Please note</div>
    <p style="font-size:13px; color:#2a1f1a; margin-bottom:16px; line-height:2;">I speak Japanese (native) and Korean only. My lessons are focused on <strong>conversation practice</strong> — not structured grammar instruction from zero. If you are a complete beginner with no Japanese foundation, I may not be the best fit for you.</p>
    <div class="notice-langs">
      <div class="notice-lang">🇺🇸 <strong>English:</strong> I only speak Japanese and Korean. This course is for conversation practice, not for absolute beginners.</div>
      <div class="notice-lang">🇻🇳 <strong>Tiếng Việt:</strong> Tôi chỉ nói tiếng Nhật và tiếng Hàn. Khóa học này dành cho luyện hội thoại, không phù hợp với người mới hoàn toàn.</div>
      <div class="notice-lang">🇹🇭 <strong>ภาษาไทย:</strong> ฉันพูดได้เฉพาะภาษาญี่ปุ่นและภาษาเกาหลี คอร์สนี้เน้นฝึกการสนทนา ไม่เหมาะสำหรับผู้เริ่มต้นใหม่ทีเดียว</div>
      <div class="notice-lang">🇹🇼 <strong>繁體中文：</strong>我只會說日語和韓語。這個課程專注於會話練習，不適合完全零基礎的學習者。</div>
      <div class="notice-lang">🇮🇩 <strong>Bahasa Indonesia:</strong> Saya hanya bisa berbicara bahasa Jepang dan Korea. Kursus ini untuk latihan percakapan, bukan untuk pemula yang benar-benar baru.</div>
    </div>
  </div>
</div>

<div class="wrap" style="padding-top:0">
  <p class="sec-label fade">About</p>
  <p class="sec-title fade">About me</p>
  <div class="about-box fade">
    <p class="about-main">During lessons, <em>we speak only in Japanese.</em><br>It's okay if it feels awkward at first.<br>The more Japanese flows into your ears, the more naturally your brain starts to follow.<br>Not forcing — just enjoying and absorbing.</p>
    <p class="about-p">This is not a grammar class for exams. It's <em style="font-style:normal;color:#c9736a;font-weight:700">real conversation-focused</em> learning.</p>
    <p class="about-p">I'll correct unnatural expressions right away, and help you build fluent, natural Japanese step by step.</p>
    <div class="tips">
      <div class="tip"><span class="tip-lbl">Recommended for</span><p class="tip-txt">Those who love anime/manga and want to speak Japanese 🎌 I lived in Korea for a year — I love Korean culture too 😊</p></div>
      <div class="tip"><span class="tip-lbl">Not recommended for</span><p class="tip-txt">If your goal is JLPT prep, there are better-suited teachers for that. I specialize in everyday conversation.</p></div>
      <div class="tip"><span class="tip-lbl">Honest note</span><p class="tip-txt">Let's fix those bad Japanese habits together. Fluent Japanese is closer than you think.</p></div>
    </div>
  </div>
</div>

<div class="wrap" style="padding-top:0">
  <p class="sec-label fade">Services & Pricing</p>
  <p class="sec-title fade">Courses & Pricing</p>

  <div class="cat-div fade">🗣️ Mini Lesson · 15 min</div>
  <div class="fade">
    <div class="plan-features">
      <div class="plan-features-title">Includes</div>
      <div class="plan-feature">Free conversation practice</div>
      <div class="plan-feature">Instant correction of unnatural expressions</div>
      <div class="plan-feature">Perfect for warming up your Japanese</div>
    </div>
    <table class="course-table">
      <tr><th class="plan-name">Plan</th><th>Regular</th><th>Monthly</th><th>Discount</th></tr>
      <tr><td>4x / month</td><td>₩40,000</td><td class="price-cell">₩38,000</td><td>5% OFF</td></tr>
      <tr><td>8x / month</td><td>₩80,000</td><td class="price-cell">₩72,000</td><td>10% OFF</td></tr>
      <tr class="popular-row"><td>12x / month <span class="popular-badge">BEST</span></td><td>₩120,000</td><td class="price-cell">₩102,000</td><td>15% OFF</td></tr>
    </table>
  </div>

  <div class="cat-div fade">💬 Standard Lesson · 30 min · With Support</div>
  <div class="fade">
    <div class="plan-features">
      <div class="plan-features-title">Includes</div>
      <div class="plan-feature">Free conversation · Any topic you choose</div>
      <div class="plan-feature">Top 3 mistakes sent via DM after each lesson</div>
      <div class="plan-feature">Next lesson focus point provided</div>
      <div class="plan-feature">First lesson includes free 15-min counseling</div>
    </div>
    <table class="course-table">
      <tr><th>Plan</th><th>Regular</th><th>Monthly</th><th>Discount</th></tr>
      <tr><td>4x / month</td><td>₩60,000</td><td class="price-cell">₩57,000</td><td>5% OFF</td></tr>
      <tr><td>8x / month</td><td>₩120,000</td><td class="price-cell">₩108,000</td><td>10% OFF</td></tr>
      <tr class="popular-row"><td>12x / month <span class="popular-badge">BEST</span></td><td>₩180,000</td><td class="price-cell">₩153,000</td><td>15% OFF</td></tr>
    </table>
  </div>

  <div class="cat-div fade">📖 Structured Lesson · 30 min</div>
  <div class="fade">
    <div class="plan-features">
      <div class="plan-features-title">Includes</div>
      <div class="plan-feature">Custom curriculum based on your goals</div>
      <div class="plan-feature">Review materials sent after every lesson</div>
      <div class="plan-feature">Optional homework</div>
    </div>
    <table class="course-table">
      <tr><th>Plan</th><th>Regular</th><th>Monthly</th><th>Discount</th></tr>
      <tr><td>4x / month</td><td>₩80,000</td><td class="price-cell">₩76,000</td><td>5% OFF</td></tr>
      <tr><td>8x / month</td><td>₩160,000</td><td class="price-cell">₩144,000</td><td>10% OFF</td></tr>
      <tr class="popular-row"><td>12x / month <span class="popular-badge">BEST</span></td><td>₩240,000</td><td class="price-cell">₩204,000</td><td>15% OFF</td></tr>
    </table>
  </div>

  <div class="policy-box fade">
    <div class="policy-title">📋 Course Info</div>
    <div class="policy-list">
      <div class="policy-item">Courses are billed monthly and auto-renewed.</div>
      <div class="policy-item">To cancel, please let me know by the end of the following month.</div>
      <div class="policy-item">Changing your plan mid-course is possible after consultation.</div>
    </div>
  </div>
</div>

<div class="wrap" style="padding-top:0">
  <p class="sec-label fade">Rules</p>
  <p class="sec-title fade">Our Promise 🤝</p>
  <div class="rules">
    <div class="rule fade"><div class="rule-num">1</div><div><div class="rule-title">Japanese only during lessons</div><p class="rule-desc">It's okay to feel awkward at first. You'll get used to it naturally!</p></div></div>
    <div class="rule fade"><div class="rule-num">2</div><div><div class="rule-title">Instant correction</div><p class="rule-desc">I'll fix unnatural expressions naturally, like a friend 😊</p></div></div>
    <div class="rule fade"><div class="rule-num">3</div><div><div class="rule-title">Cancellation & Changes</div><p class="rule-desc">Free cancellation/change up to 5 days before.<br>No refund for cancellations within 5 days.</p></div></div>
    <div class="rule fade"><div class="rule-num">4</div><div><div class="rule-title">Reply within 24 hours</div><p class="rule-desc">If it's urgent, please let me know in advance.</p></div></div>
    <div class="rule fade"><div class="rule-num">5</div><div><div class="rule-title">First lesson includes free counseling</div><p class="rule-desc">If we're not a good fit, I'll be honest with you.</p></div></div>
  </div>
</div>

<div class="wrap" style="padding-top:0">
  <p class="sec-label fade">Payment</p>
  <p class="sec-title fade">How to Pay 💳</p>
  <div class="pay-box fade">
    <p class="pay-main">Payment is made via <em>Stripe</em>.<br>You can pay easily with your card 🙂</p>
    <p class="pay-sub">After confirming your booking, I'll send a payment link via DM. No app installation needed!</p>
    <div class="pay-step">① Confirm booking → ② Receive payment link via DM → ③ Enter card details → ④ Done 🎉</div>
  </div>
</div>

<div class="wrap" style="padding-top:0">
  <p class="sec-label fade">How to Start</p>
  <p class="sec-title fade">Getting Started</p>
  <div class="flow">
    <div class="flow-step fade"><div class="flow-dot">👋</div><div><div class="flow-name">Send a DM</div><p class="flow-desc">Let me know what you're looking for</p></div></div>
    <div class="flow-step fade"><div class="flow-dot">💭</div><div><div class="flow-name">Free 15-min Counseling</div><p class="flow-desc">We'll talk about your level, goals, and style</p></div></div>
    <div class="flow-step fade"><div class="flow-dot">💳</div><div><div class="flow-name">Pay & Confirm Schedule</div><p class="flow-desc">Pick your time and pay — that's it!</p></div></div>
    <div class="flow-step fade"><div class="flow-dot">🌸</div><div><div class="flow-name">Let's start!</div><p class="flow-desc">First lesson begins 🎉</p></div></div>
  </div>
</div>

<div class="wrap" style="padding-top:0">
  <p class="sec-label fade">FAQ</p>
  <p class="sec-title fade">Frequently Asked Questions ❓</p>
  <div class="faq fade">
    <div class="faq-item">
      <button class="faq-q" onclick="toggleFaq(this)"><span class="faq-q-text">I'm a complete beginner. Is that okay?</span><span class="faq-arrow">▼</span></button>
      <div class="faq-a"><div class="faq-a-inner">If you have some basic foundation (like hiragana), you're welcome! However, if you are truly starting from zero with no Japanese at all, I may not be the best fit. Let's chat in a free counseling session first 🌸</div></div>
    </div>
    <div class="faq-item">
      <button class="faq-q" onclick="toggleFaq(this)"><span class="faq-q-text">How are lessons conducted?</span><span class="faq-arrow">▼</span></button>
      <div class="faq-a"><div class="faq-a-inner">Via Google Meet. The link is sent automatically after booking. No app installation needed!</div></div>
    </div>
    <div class="faq-item">
      <button class="faq-q" onclick="toggleFaq(this)"><span class="faq-q-text">Can I cancel my course?</span><span class="faq-arrow">▼</span></button>
      <div class="faq-a"><div class="faq-a-inner">Yes! Just let me know by the end of the following month and it will be cancelled from the month after.</div></div>
    </div>
    <div class="faq-item">
      <button class="faq-q" onclick="toggleFaq(this)"><span class="faq-q-text">Do you teach JLPT prep?</span><span class="faq-arrow">▼</span></button>
      <div class="faq-a"><div class="faq-a-inner">I specialize in everyday conversation. If JLPT is your goal, there may be better-suited teachers for you. I'll be honest 🙏</div></div>
    </div>
    <div class="faq-item">
      <button class="faq-q" onclick="toggleFaq(this)"><span class="faq-q-text">What languages do you speak?</span><span class="faq-arrow">▼</span></button>
      <div class="faq-a"><div class="faq-a-inner">Japanese (native) and Korean. Lessons are conducted in Japanese, but I can support Korean speakers a little too 😊</div></div>
    </div>
  </div>
</div>

<div class="wrap" style="padding-top:0; padding-bottom:80px;">
  <div class="cta-box fade">
    <p>Feel free to DM me anytime 🌸<br>The first counseling session is <strong>free for 15 minutes</strong>.<br>Let's find the right plan for you!</p>
    <a href="https://calendly.com/mom-0730-mom/30min" target="_blank" class="cta-btn">Book a Free Counseling 🌸</a>
  </div>
</div>

<footer>✦ Japanese Friend Teacher · Manon · Osaka, Japan ✦</footer>

</div><!-- end en-content -->

<script>
function setLang(lang) {
  document.body.classList.toggle('en', lang === 'en');
  document.querySelectorAll('.lang-btn').forEach(function(btn) {
    btn.classList.remove('active');
  });
  event.target.classList.add('active');
}

document.addEventListener('DOMContentLoaded', function() {
  var heroFades = document.querySelectorAll('.hero .fade');
  heroFades.forEach(function(el, i) {
    setTimeout(function() { el.classList.add('visible'); }, 100 + i * 150);
  });
  var observer = new IntersectionObserver(function(entries) {
    entries.forEach(function(entry) {
      if (entry.isIntersecting) { entry.target.classList.add('visible'); observer.unobserve(entry.target); }
    });
  }, { threshold: 0.1 });
  document.querySelectorAll('.wrap .fade, .review, .rule, .flow-step, .cta-box, .pay-box, .faq, .notice-box, .policy-box').forEach(function(el) { observer.observe(el); });
});

function toggleFaq(btn) {
  var answer = btn.nextElementSibling;
  var arrow = btn.querySelector('.faq-arrow');
  var isOpen = answer.classList.contains('open');
  document.querySelectorAll('.faq-a').forEach(function(a) { a.classList.remove('open'); });
  document.querySelectorAll('.faq-arrow').forEach(function(a) { a.style.transform = 'rotate(0)'; });
  if (!isOpen) {
    answer.classList.add('open');
    arrow.style.transform = 'rotate(180deg)';
  }
}
</script>
</body>
</html>
