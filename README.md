[index.html](https://github.com/user-attachments/files/27294749/index.html)
# gemini_gems_builder
gems builder<!DOCTYPE html>
<html lang="ko">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gemini Gems 프롬프트 작성 도우미</title>
  <link
    href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap"
    rel="stylesheet">
  <link rel="stylesheet" href="style.css">
</head>

<body>
  <div class="page-wrap">

    <!-- Header -->
    <header class="header">
      <div class="header-icon">
        <svg width="36" height="36" viewBox="0 0 36 36" fill="none">
          <rect width="36" height="36" rx="12" fill="url(#g1)" />
          <path d="M18 10l6 4v8l-6 4-6-4v-8l6-4z" fill="white" opacity="0.9" />
          <path d="M18 14l3 2v4l-3 2-3-2v-4l3-2z" fill="rgba(255,255,255,0.5)" />
          <defs>
            <linearGradient id="g1" x1="0" y1="0" x2="36" y2="36">
              <stop stop-color="#3182F6" />
              <stop offset="1" stop-color="#6366F1" />
            </linearGradient>
          </defs>
        </svg>
      </div>
      <h1>Gems 프롬프트 빌더</h1>
      <p class="header-sub">6단계만 따라오면 완성됩니다</p>
    </header>

    <!-- Progress -->
    <div class="progress-section">
      <div class="progress-steps" id="progressSteps">
        <div class="p-step active" data-step="0"><span class="p-num">1</span></div>
        <div class="p-line">
          <div class="p-line-fill"></div>
        </div>
        <div class="p-step" data-step="1"><span class="p-num">2</span></div>
        <div class="p-line">
          <div class="p-line-fill"></div>
        </div>
        <div class="p-step" data-step="2"><span class="p-num">3</span></div>
        <div class="p-line">
          <div class="p-line-fill"></div>
        </div>
        <div class="p-step" data-step="3"><span class="p-num">4</span></div>
        <div class="p-line">
          <div class="p-line-fill"></div>
        </div>
        <div class="p-step" data-step="4"><span class="p-num">5</span></div>
        <div class="p-line">
          <div class="p-line-fill"></div>
        </div>
        <div class="p-step" data-step="5"><span class="p-num">6</span></div>
        <div class="p-line">
          <div class="p-line-fill"></div>
        </div>
        <div class="p-step" data-step="6"><span class="p-num">✓</span></div>
      </div>
      <div class="progress-label" id="progressLabel">목표 설정</div>
    </div>

    <!-- Cards Container -->
    <div class="cards-area">

      <!-- Step 0: 목표 설정 -->
      <div class="card step active" id="step0">
        <div class="card-header">
          <span class="card-tag tag-blue">STEP 1</span>
          <h2>이 Gem은 무엇을 하나요?</h2>
          <p>목표가 구체적일수록 Gem 성능이 올라갑니다</p>
        </div>
        <div class="card-body">
          <div class="field">
            <label>Gem 이름</label>
            <input type="text" id="gemName" placeholder="예: 법률 문서 검토 도우미">
          </div>
          <div class="field">
            <label>핵심 문제</label>
            <textarea id="gemGoal" rows="4" placeholder="예: 계약서를 읽고 주요 조항과 위험 요소를 쉬운 말로 요약해준다"></textarea>
          </div>
          <div class="field">
            <label>사용 시나리오 <span class="optional">선택</span></label>
            <input type="text" id="gemScenario" placeholder="예: 근로계약서 검토, 임대차 계약 확인">
          </div>
        </div>
        <div class="card-footer">
          <span></span>
          <button class="btn-primary" onclick="goStep(1)">다음<svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M6 4l4 4-4 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg></button>
        </div>
      </div>

      <!-- Step 1: 페르소나 -->
      <div class="card step" id="step1">
        <div class="card-header">
          <span class="card-tag tag-purple">STEP 2</span>
          <h2>전문가 정체성 설정</h2>
          <p>경력과 전문 분야를 정의하면 답변 품질이 달라집니다</p>
        </div>
        <div class="card-body">
          <div class="field">
            <label>직함 & 경력</label>
            <input type="text" id="personaTitle" placeholder="예: 법무법인 10년 경력 계약 전문 변호사">
          </div>
          <div class="field">
            <label>전문 분야 & 강점</label>
            <textarea id="personaExpertise" rows="3" placeholder="예: 근로·임대차 계약 분석, 불공정 조항 식별에 강점"></textarea>
          </div>
          <div class="field">
            <label>사고방식</label>
            <div class="chip-grid" id="mindsetChips">
              <button class="chip" onclick="toggleChip(this)">데이터 중심적</button>
              <button class="chip" onclick="toggleChip(this)">창의적 발산형</button>
              <button class="chip" onclick="toggleChip(this)">전략적 사고</button>
              <button class="chip" onclick="toggleChip(this)">실용주의자</button>
              <button class="chip" onclick="toggleChip(this)">사용자 공감 우선</button>
              <button class="chip" onclick="toggleChip(this)">비판적 분석가</button>
              <button class="chip" onclick="toggleChip(this)">효율성 최우선</button>
              <button class="chip" onclick="toggleChip(this)">트렌드 선도</button>
            </div>
          </div>
        </div>
        <div class="card-footer">
          <button class="btn-ghost" onclick="goStep(0)"><svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M10 4l-4 4 4 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg>이전</button>
          <button class="btn-primary" onclick="goStep(2)">다음<svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M6 4l4 4-4 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg></button>
        </div>
      </div>

      <!-- Step 2: 컨텍스트 -->
      <div class="card step" id="step2">
        <div class="card-header">
          <span class="card-tag tag-green">STEP 3</span>
          <h2>배경 정보 제공</h2>
          <p>맥락이 풍부할수록 결과물의 질이 올라갑니다</p>
        </div>
        <div class="card-body">
          <div class="field">
            <label>대상 사용자</label>
            <input type="text" id="ctxAudience" placeholder="예: 계약서를 처음 검토하는 직장인">
          </div>
          <div class="field">
            <label>도메인 특수 지식</label>
            <textarea id="ctxDomain" rows="3" placeholder="예: 근로기준법 필수 기재 항목, 불공정약관규제법 위반 유형"></textarea>
          </div>
          <div class="field">
            <label>제약 & 금지 사항</label>
            <textarea id="ctxConstraints" rows="3" placeholder="예: 법적 최종 판단은 전문 변호사에게 받으라고 안내할 것"></textarea>
          </div>
        </div>
        <div class="card-footer">
          <button class="btn-ghost" onclick="goStep(1)"><svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M10 4l-4 4 4 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg>이전</button>
          <button class="btn-primary" onclick="goStep(3)">다음<svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M6 4l4 4-4 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg></button>
        </div>
      </div>

      <!-- Step 3: 톤 & 형식 -->
      <div class="card step" id="step3">
        <div class="card-header">
          <span class="card-tag tag-amber">STEP 4</span>
          <h2>톤 & 출력 형식</h2>
          <p>일관된 스타일이 Gem의 신뢰성을 만듭니다</p>
        </div>
        <div class="card-body">
          <div class="field">
            <label>커뮤니케이션 톤</label>
            <div class="chip-grid" id="toneChips">
              <button class="chip" onclick="toggleChipSingle(this,'toneChips')">전문적·공식적</button>
              <button class="chip" onclick="toggleChipSingle(this,'toneChips')">친근하고 따뜻한</button>
              <button class="chip" onclick="toggleChipSingle(this,'toneChips')">직설적·간결한</button>
              <button class="chip" onclick="toggleChipSingle(this,'toneChips')">유머러스·위트있는</button>
              <button class="chip" onclick="toggleChipSingle(this,'toneChips')">코칭·멘토링</button>
              <button class="chip" onclick="toggleChipSingle(this,'toneChips')">분석적·객관적</button>
            </div>
          </div>
          <div class="field">
            <label>출력 언어</label>
            <div class="chip-grid" id="langChips">
              <button class="chip selected" onclick="toggleChipSingle(this,'langChips')">한국어</button>
              <button class="chip" onclick="toggleChipSingle(this,'langChips')">영어</button>
              <button class="chip" onclick="toggleChipSingle(this,'langChips')">한국어 + 영어</button>
              <button class="chip" onclick="toggleChipSingle(this,'langChips')">사용자 언어 맞춤</button>
            </div>
          </div>
          <div class="field">
            <label>출력 형식 <span class="optional">복수 선택</span></label>
            <div class="chip-grid" id="formatChips">
              <button class="chip" onclick="toggleChip(this)">번호 목록</button>
              <button class="chip" onclick="toggleChip(this)">마크다운</button>
              <button class="chip" onclick="toggleChip(this)">표/테이블</button>
              <button class="chip" onclick="toggleChip(this)">단락형 산문</button>
              <button class="chip" onclick="toggleChip(this)">코드 블록</button>
              <button class="chip" onclick="toggleChip(this)">비교 형식</button>
              <button class="chip" onclick="toggleChip(this)">Q&amp;A 형식</button>
              <button class="chip" onclick="toggleChip(this)">결론 우선</button>
            </div>
          </div>
          <div class="field">
            <label>응답 길이</label>
            <div class="chip-grid" id="lengthChips">
              <button class="chip" onclick="toggleChipSingle(this,'lengthChips')">간결 (3-5줄)</button>
              <button class="chip selected" onclick="toggleChipSingle(this,'lengthChips')">보통</button>
              <button class="chip" onclick="toggleChipSingle(this,'lengthChips')">상세 (풍부한 설명)</button>
            </div>
          </div>
        </div>
        <div class="card-footer">
          <button class="btn-ghost" onclick="goStep(2)"><svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M10 4l-4 4 4 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg>이전</button>
          <button class="btn-primary" onclick="goStep(4)">다음<svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M6 4l4 4-4 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg></button>
        </div>
      </div>

      <!-- Step 4: 하네스 -->
      <div class="card step" id="step4">
        <div class="card-header">
          <span class="card-tag tag-red">STEP 5</span>
          <h2>시스템 설계</h2>
          <p>작업 순서와 금지 행동을 정하면 Gem이 안정적으로 작동합니다</p>
        </div>
        <div class="card-body">
          <div class="two-col">
            <div class="field">
              <label>워크플로우</label>
              <textarea id="harnessWorkflow" rows="6"
                placeholder="예:&#10;1. 계약 유형 파악&#10;2. 전체 구조 요약&#10;3. 핵심 조항 설명&#10;4. 수정 필요 부분 제안"></textarea>
            </div>
            <div class="field">
              <label>가드레일 (금지)</label>
              <textarea id="harnessGuardrails" rows="6"
                placeholder="예:&#10;- 확인 안 된 법조문 인용 금지&#10;- 최종 법적 판단 금지&#10;- 정보 부족 시 질문 먼저"></textarea>
            </div>
          </div>
          <div class="field">
            <label>피드백 방식 <span class="optional">복수 선택</span></label>
            <div class="chip-grid" id="feedbackChips">
              <button class="chip" onclick="toggleChip(this)">수정 요청 적극 반영</button>
              <button class="chip" onclick="toggleChip(this)">추가 정보 요청</button>
              <button class="chip" onclick="toggleChip(this)">다양한 버전 제시</button>
              <button class="chip" onclick="toggleChip(this)">결과물 평가 요청</button>
              <button class="chip" onclick="toggleChip(this)">단계적 개선 제안</button>
            </div>
          </div>
        </div>
        <div class="card-footer">
          <button class="btn-ghost" onclick="goStep(3)"><svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M10 4l-4 4 4 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg>이전</button>
          <button class="btn-primary" onclick="goStep(5)">다음<svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M6 4l4 4-4 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg></button>
        </div>
      </div>

      <!-- Step 5: 변수 -->
      <div class="card step" id="step5">
        <div class="card-header">
          <span class="card-tag tag-teal">STEP 6</span>
          <h2>동적 변수 정의</h2>
          <p>[변수명]을 쓰면 사용자가 직접 값을 입력할 수 있어요</p>
        </div>
        <div class="card-body">
          <div id="varsContainer">
            <div class="var-row">
              <input type="text" placeholder="변수명" class="var-name">
              <input type="text" placeholder="설명" class="var-desc">
              <button class="var-del" onclick="delVar(this)" aria-label="삭제">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none">
                  <path d="M4 4l8 8M12 4l-8 8" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
                </svg>
              </button>
            </div>
          </div>
          <button class="btn-add" onclick="addVar()">
            <svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M8 3v10M3 8h10" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg>
            변수 추가
          </button>
        </div>
        <div class="card-footer">
          <button class="btn-ghost" onclick="goStep(4)"><svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M10 4l-4 4 4 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg>이전</button>
          <button class="btn-primary btn-generate" onclick="goStep(6)">
            <svg width="18" height="18" viewBox="0 0 18 18" fill="none">
              <path d="M9 2l2 5h5l-4 3 2 5-5-3-5 3 2-5-4-3h5l2-5z" fill="currentColor" />
            </svg>
            프롬프트 생성
          </button>
        </div>
      </div>

      <!-- Step 6: 결과 -->
      <div class="card step" id="step6">
        <div class="card-header">
          <span class="card-tag tag-blue">완성</span>
          <h2>프롬프트가 완성되었어요</h2>
          <p>아래 내용을 Gemini Gems에 붙여넣으세요</p>
        </div>
        <div class="card-body">
          <div class="result-box">
            <div class="result-top">
              <span class="result-label">System Prompt</span>
              <button class="copy-btn" id="copyBtn" onclick="copyPrompt()">
                <svg width="14" height="14" viewBox="0 0 14 14" fill="none">
                  <rect x="4" y="4" width="8" height="8" rx="1.5" stroke="currentColor" stroke-width="1.5" />
                  <path d="M10 4V3a1.5 1.5 0 00-1.5-1.5H3A1.5 1.5 0 001.5 3v5.5A1.5 1.5 0 003 10h1"
                    stroke="currentColor" stroke-width="1.5" />
                </svg>
                <span id="copyText">복사</span>
              </button>
            </div>
            <pre class="result-text" id="resultText"></pre>
          </div>

          <div class="checklist" id="checkList"></div>

          <div class="howto-card">
            <div class="howto-icon">💡</div>
            <div>
              <strong>Gems 적용 방법</strong>
              <ol>
                <li><code>gemini.google.com</code> 접속</li>
                <li>사이드바 → <code>Gems 탐색하기</code></li>
                <li><code>+ 새 Gem</code> → 요청 사항에 붙여넣기</li>
                <li>미리보기 테스트 후 저장</li>
              </ol>
            </div>
          </div>
        </div>
        <div class="card-footer">
          <button class="btn-ghost" onclick="goStep(5)"><svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M10 4l-4 4 4 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg>수정하기</button>
          <button class="btn-reset" onclick="resetAll()">
            <svg width="16" height="16" viewBox="0 0 16 16" fill="none">
              <path d="M2 8a6 6 0 0111.5-2.5M14 8a6 6 0 01-11.5 2.5" stroke="currentColor" stroke-width="2"
                stroke-linecap="round" />
              <path d="M14 2v4h-4M2 14v-4h4" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                stroke-linejoin="round" />
            </svg>
            처음부터
          </button>
        </div>
      </div>

    </div><!-- /cards-area -->

    <footer class="footer">Gemini Gems 프롬프트 빌더 · 로컬 전용</footer>
  </div>

  <script src="app.js"></script>
</body>

</html>
