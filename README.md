<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Leadership Clarity Assessment</title>
  <style>
    :root{
      --bg:#0b0f19;
      --card:#111827;
      --muted:#94a3b8;
      --text:#e5e7eb;
      --accent:#38bdf8;
      --accent2:#a78bfa;
      --border:#1f2937;
      --good:#34d399;
      --warn:#fbbf24;
      --bad:#fb7185;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
      background: radial-gradient(1200px 600px at 20% 0%, rgba(56,189,248,.12), transparent 60%),
                  radial-gradient(900px 500px at 80% 10%, rgba(167,139,250,.12), transparent 60%),
                  var(--bg);
      color:var(--text);
      line-height:1.45;
    }
    .wrap{
      max-width: 980px;
      margin: 0 auto;
      padding: 24px 16px 56px;
    }
    header{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:16px;
      margin-bottom:18px;
    }
    .brand{
      display:flex;
      align-items:center;
      gap:10px;
      font-weight:700;
      letter-spacing:.2px;
    }
    .dot{
      width:10px;height:10px;border-radius:999px;
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      box-shadow: 0 0 0 4px rgba(56,189,248,.12);
    }
    .pill{
      font-size:12px;
      color:var(--muted);
      border:1px solid var(--border);
      padding:6px 10px;
      border-radius:999px;
      background: rgba(17,24,39,.6);
    }
    .card{
      border:1px solid var(--border);
      background: rgba(17,24,39,.78);
      border-radius:16px;
      padding: 22px;
      box-shadow: 0 12px 30px rgba(0,0,0,.25);
    }
    .grid{
      display:grid;
      gap:16px;
    }
    h1,h2,h3{margin:0 0 10px}
    h1{font-size:30px; line-height:1.15}
    h2{font-size:22px}
    h3{font-size:16px; color:var(--muted); font-weight:600}
    p{margin:0 0 12px; color:var(--text)}
    .muted{color:var(--muted)}
    .btnrow{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      margin-top:12px;
    }
    button, .btn{
      appearance:none;
      border:1px solid var(--border);
      background: rgba(2,6,23,.35);
      color:var(--text);
      padding: 10px 14px;
      border-radius: 12px;
      cursor:pointer;
      font-weight:600;
      transition: transform .05s ease, border-color .15s ease, background .15s ease;
      text-decoration:none;
      display:inline-flex;
      align-items:center;
      justify-content:center;
      gap:8px;
      user-select:none;
    }
    button:hover, .btn:hover{
      border-color: rgba(56,189,248,.55);
      background: rgba(56,189,248,.08);
    }
    button:active{ transform: translateY(1px); }
    button.primary{
      border-color: rgba(56,189,248,.65);
      background: linear-gradient(135deg, rgba(56,189,248,.18), rgba(167,139,250,.12));
    }
    button.ghost{
      background: transparent;
    }
    .tiles{
      display:grid;
      grid-template-columns: repeat(5, minmax(0, 1fr));
      gap:12px;
      margin-top:10px;
    }
    .tile{
      text-align:left;
      padding:14px 14px;
      border-radius:14px;
      border:1px solid var(--border);
      background: rgba(2,6,23,.25);
      cursor:pointer;
      transition: border-color .15s ease, background .15s ease;
      min-height:74px;
    }
    .tile:hover{
      border-color: rgba(167,139,250,.55);
      background: rgba(167,139,250,.08);
    }
    .tile strong{display:block; font-size:14px; margin-bottom:6px;}
    .tile span{display:block; font-size:12px; color:var(--muted);}
    @media (max-width: 900px){
      .tiles{ grid-template-columns: repeat(2, minmax(0, 1fr)); }
    }
    @media (max-width: 460px){
      .tiles{ grid-template-columns: 1fr; }
    }

    .progress{
      height:8px;
      background: rgba(148,163,184,.18);
      border-radius:999px;
      overflow:hidden;
      border:1px solid var(--border);
      margin: 12px 0 14px;
    }
    .bar{
      height:100%;
      width:0%;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      transition: width .2s ease;
    }

    .question{
      font-size:20px;
      margin: 6px 0 14px;
    }
    .choices{
      display:grid;
      gap:10px;
      margin-top:8px;
    }
    .choice{
      border:1px solid var(--border);
      background: rgba(2,6,23,.25);
      padding: 12px 12px;
      border-radius: 12px;
      cursor:pointer;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:10px;
      transition: border-color .15s ease, background .15s ease;
    }
    .choice:hover{
      border-color: rgba(56,189,248,.55);
      background: rgba(56,189,248,.06);
    }
    .choice.selected{
      border-color: rgba(56,189,248,.85);
      background: rgba(56,189,248,.10);
    }
    .choice small{color:var(--muted)}
    .kpi{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      margin-top:8px;
    }
    .chip{
      border:1px solid var(--border);
      background: rgba(2,6,23,.25);
      padding: 8px 10px;
      border-radius:999px;
      font-size:12px;
      color:var(--muted);
    }
    .section{
      border-top:1px solid rgba(31,41,55,.9);
      margin-top:14px;
      padding-top:14px;
    }
    .callout{
      border:1px solid rgba(56,189,248,.35);
      background: rgba(56,189,248,.08);
      padding: 14px;
      border-radius:14px;
      margin-top:10px;
    }
    .roadmap{
      display:grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap:10px;
      margin-top:10px;
    }
    .step{
      border:1px solid var(--border);
      background: rgba(2,6,23,.22);
      border-radius:14px;
      padding: 12px;
    }
    .step strong{display:block; margin-bottom:6px}
    .step p{margin:0; color:var(--muted); font-size:13px}
    @media (max-width: 780px){
      .roadmap{ grid-template-columns: 1fr; }
    }
    .footerActions{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      margin-top:14px;
    }
    .note{
      font-size:12px;
      color:var(--muted);
      margin-top:10px;
    }
    .linklike{
      color: var(--accent);
      text-decoration: none;
      font-weight: 700;
    }
    .linklike:hover{ text-decoration: underline; }
    .hidden{display:none !important}
    .row{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
      flex-wrap:wrap;
    }
    .tiny{
      font-size:12px;
      color:var(--muted);
    }
    .divider{
      height:1px;background:rgba(31,41,55,.9);margin:10px 0;
    }
    .input{
      width:100%;
      padding: 10px 12px;
      border-radius: 12px;
      border: 1px solid var(--border);
      background: rgba(2,6,23,.25);
      color: var(--text);
      outline:none;
    }
    .input:focus{ border-color: rgba(56,189,248,.65); }
    .twoCol{
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
      margin-top: 10px;
    }
    @media (max-width: 780px){
      .twoCol{ grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="brand"><span class="dot"></span> Leadership Clarity Assessment</div>
      <div class="pill" id="statusPill">Private. 5 minutes.</div>
    </header>

    <!-- Screen: Start -->
    <section class="card" id="screenStart">
      <h1>What’s the real leadership issue draining your energy right now?</h1>
      <p class="muted">
        Most leaders don’t struggle because they lack skill. They struggle because one invisible issue keeps showing up.
        This short assessment helps you name it and shows you a clear path forward.
      </p>
      <div class="btnrow">
        <button class="primary" id="btnStart">Start the assessment</button>
        <button class="ghost" id="btnPreview">Preview the five areas</button>
      </div>
      <p class="note">Tip: Use this as a lead magnet. You can add an email capture right before results.</p>
    </section>

    <!-- Screen: Choose area -->
    <section class="card hidden" id="screenChoose">
      <div class="row">
        <h2>Pick the area that feels most frustrating right now.</h2>
        <span class="tiny" id="chooseHint">Choose one to personalize your path</span>
      </div>
      <div class="tiles" id="areaTiles"></div>
      <div class="btnrow">
        <button class="ghost" id="btnBackToStart">Back</button>
      </div>
    </section>

    <!-- Screen: Path intro -->
    <section class="card hidden" id="screenIntro">
      <h2 id="introTitle">You chose: </h2>
      <p class="muted">Answer honestly. This is private. There is no “good” score here. You are aiming for clarity.</p>
      <div class="kpi">
        <span class="chip" id="chipTime">Time: ~3 minutes</span>
        <span class="chip" id="chipCount">Questions: 7</span>
        <span class="chip" id="chipFlow">One question per screen</span>
      </div>
      <div class="btnrow">
        <button class="ghost" id="btnIntroBack">Back</button>
        <button class="primary" id="btnIntroNext">Continue</button>
      </div>
    </section>

    <!-- Screen: Question -->
    <section class="card hidden" id="screenQuestion">
      <div class="row">
        <h3 id="pathLabel">Path</h3>
        <span class="tiny" id="qCounter">Question 1 of 7</span>
      </div>
      <div class="progress" aria-label="Progress">
        <div class="bar" id="progressBar"></div>
      </div>

      <div class="question" id="questionText"></div>

      <div class="choices" id="choices"></div>

      <div class="btnrow">
        <button class="ghost" id="btnQBack">Back</button>
        <button class="primary" id="btnQNext" disabled>Next</button>
      </div>
      <p class="note">Your answers are stored only in this browser session unless you wire up your own backend.</p>
    </section>

    <!-- Screen: Optional email capture -->
    <section class="card hidden" id="screenEmail">
      <h2>Want your results sent to you?</h2>
      <p class="muted">
        Optional. If you skip, you can still view your results on the next screen.
      </p>

      <div class="twoCol">
        <div>
          <label class="tiny" for="nameInput">Name (optional)</label>
          <input class="input" id="nameInput" type="text" placeholder="Dave" />
        </div>
        <div>
          <label class="tiny" for="emailInput">Email (optional)</label>
          <input class="input" id="emailInput" type="email" placeholder="you@company.com" />
        </div>
      </div>

      <div class="btnrow">
        <button class="ghost" id="btnEmailSkip">Skip</button>
        <button class="primary" id="btnEmailContinue">Continue to results</button>
      </div>

      <p class="note">
        To actually email results, connect this to your form handler (HubSpot, Zapier, Make, or a small API endpoint).
        This page stores the name/email in memory only.
      </p>
    </section>

    <!-- Screen: Results -->
    <section class="card hidden" id="screenResults">
      <div class="row">
        <h2 id="resultsHeadline">Your results</h2>
        <span class="pill" id="resultsBadge">Profile</span>
      </div>

      <p class="muted" id="resultsSubhead"></p>

      <div class="section">
        <h3>What’s really happening</h3>
        <p id="resultsWhatsHappening"></p>
      </div>

      <div class="section">
        <h3>Why this feels exhausting</h3>
        <p id="resultsWhyExhausting"></p>
      </div>

      <div class="section">
        <h3>The hidden cost</h3>
        <p id="resultsHiddenCost"></p>
      </div>

      <div class="callout">
        <h3>One thing you can do immediately</h3>
        <p id="resultsQuickWin"></p>
      </div>

      <div class="section">
        <h3>Your personal roadmap</h3>
        <div class="roadmap">
          <div class="step">
            <strong id="rm1Title">Phase 1</strong>
            <p id="rm1Body"></p>
          </div>
          <div class="step">
            <strong id="rm2Title">Phase 2</strong>
            <p id="rm2Body"></p>
          </div>
          <div class="step">
            <strong id="rm3Title">Phase 3</strong>
            <p id="rm3Body"></p>
          </div>
        </div>
      </div>

      <div class="section">
        <h3>Next step</h3>
        <p id="resultsCTA"></p>
        <div class="footerActions">
          <!-- Replace href with your real URL -->
          <a class="btn primary" id="btnOffer" href="#" target="_blank" rel="noreferrer">View the Manage X Leadership Series</a>
          <button class="btn" id="btnCopy">Copy my results</button>
          <button class="btn ghost" id="btnRestart">Restart</button>
        </div>
        <p class="note" id="resultsNote"></p>
      </div>
    </section>
  </div>

  <script>
    // -----------------------------
    // CONFIG: Update these
    // -----------------------------
    const CONFIG = {
      offerUrl: "https://your-site.com/manage-x", // <- change me
      brandName: "Manage X",
      // If you want to pass results to a CRM later, use this object as your payload blueprint:
      captureFields: ["name","email","pathKey","pathLabel","profileKey","profileLabel","score","answers"]
    };

    // -----------------------------
    // Assessment content
    // 5 paths, 7 statements each
    // 3 profiles per path based on total score
    // -----------------------------
    const SCALE = [
      { key: "sa", label: "Strongly Agree", value: 4 },
      { key: "a",  label: "Agree",          value: 3 },
      { key: "d",  label: "Disagree",       value: 2 },
      { key: "sd", label: "Strongly Disagree", value: 1 }
    ];

    // Threshold ranges are inclusive
    const PROFILES = [
      { key: "avoidant", label: "Avoidant", min: 7,  max: 14 },
      { key: "inconsistent", label: "Inconsistent", min: 15, max: 21 },
      { key: "strained", label: "Engaged but Strained", min: 22, max: 28 }
    ];

    const PATHS = {
      communication: {
        label: "Communication",
        subtitle: "Clarity, confidence, and being heard.",
        statements: [
          "I sometimes say things that make sense to me, but my team still seems confused.",
          "I avoid being direct because I do not want to sound harsh or damage trust.",
          "I often repeat myself because messages do not land the first time.",
          "I struggle to deliver feedback without it feeling personal.",
          "I assume people understand me, then I find out they did not.",
          "I am not always sure what to say in the moment, so I say less than I should.",
          "When pressure is high, my communication gets shorter and less clear."
        ],
        // Results copy for each profile
        results: {
          avoidant: buildResultPack(
            "Your challenge is not communication. It is hesitation under pressure.",
            "You are likely holding back more than you realize. That usually comes from wanting to protect relationships and avoid saying the wrong thing.",
            "When you hesitate, your team fills the gaps with assumptions. That creates confusion and extra follow-up for you.",
            "Over time, this can reduce trust because people do not know what you really expect.",
            "Before your next important message, write one sentence: 'The outcome I need is ____.' Then say that sentence first, out loud, before details.",
            roadmap("Awareness", "Notice where you soften or avoid clarity. Name the moments you hold back.",
                    "Structure", "Use a repeatable message format: outcome, expectations, timeline, owner.",
                    "Consistency", "Practice direct feedback weekly so clarity becomes normal, not a crisis move."),
            ctaText()
          ),
          inconsistent: buildResultPack(
            "You communicate well, but it is not consistent across situations.",
            "You have moments of clarity, then moments where you soften, over-explain, or avoid the hard line.",
            "That inconsistency makes people second-guess priorities and escalates small questions into big interruptions.",
            "It can also put you in a constant loop of re-clarifying and re-aligning.",
            "Choose one meeting this week to be radically clear: outcome, priorities, and what 'good' looks like. Repeat it twice, then stop talking.",
            roadmap("Awareness", "Identify the situations where your clarity drops (pressure, conflict, high performers).",
                    "Structure", "Adopt a simple framework and use it every time, especially for feedback and priorities.",
                    "Consistency", "Create a weekly cadence for alignment so you do not rely on 'big talks'."),
            ctaText()
          ),
          strained: buildResultPack(
            "Your challenge is not being understood. It is carrying the weight of clarity for everyone.",
            "You can communicate, but you are often the translator, the clarifier, and the one who keeps the message alive.",
            "That creates fatigue because you are doing two jobs: leading and constantly re-communicating.",
            "If you keep carrying clarity alone, you risk burnout and a dependent team.",
            "Pick one decision area and push clarity ownership down: ask a team member to restate the message in writing and confirm next steps with others.",
            roadmap("Awareness", "Notice where the team depends on you to interpret everything.",
                    "Structure", "Install communication standards: agendas, decision notes, written owners.",
                    "Consistency", "Coach the team to communicate without you in the middle."),
            ctaText()
          )
        }
      },

      conflict: {
        label: "Conflict Resolution",
        subtitle: "Hard conversations without avoidance or escalation.",
        statements: [
          "I delay addressing conflict longer than I should.",
          "I replay difficult conversations in my head after they happen.",
          "I worry about saying the wrong thing and making situations worse.",
          "I handle conflict differently depending on who I’m dealing with.",
          "I avoid conflict with high performers more than I admit.",
          "I often step in to fix conflict instead of coaching others through it.",
          "Unresolved tension drains more of my energy than I realize."
        ],
        results: {
          avoidant: buildResultPack(
            "Your challenge is not conflict. It is confidence under pressure.",
            "You are not avoiding conflict because you do not care. You are avoiding it because you do not feel fully equipped to handle it cleanly.",
            "Avoidance usually looks like delay, overthinking, or trying to solve it indirectly.",
            "The cost is a quiet build-up of tension, plus mental load you carry alone.",
            "Before a hard conversation, separate emotion from objective. Write: outcome, boundary, next step. Then lead with the outcome.",
            roadmap("Awareness", "Spot your delay patterns and what triggers them (tone, authority, high performer).",
                    "Structure", "Use a repeatable conversation framework: facts, impact, expectation, next step.",
                    "Consistency", "Practice small, direct conversations weekly so the big ones are not rare events."),
            ctaText()
          ),
          inconsistent: buildResultPack(
            "You face conflict, but it costs more energy than it should.",
            "You can step in when needed, but you do not always have a consistent structure for the conversation.",
            "That creates a cycle: the problem resurfaces, you re-address it, and you carry the frustration.",
            "Inconsistent conflict handling makes standards feel optional.",
            "Use one opening line every time: 'Here is what I am seeing. Here is the impact. Here is what needs to change.'",
            roadmap("Awareness", "Identify the types of conflict that throw you off (peers, strong personalities, ambiguity).",
                    "Structure", "Install a single conflict framework and use it every time, even in small issues.",
                    "Consistency", "Coach others to handle tension so you are not the only mediator."),
            ctaText()
          ),
          strained: buildResultPack(
            "You do not avoid conflict. You carry it.",
            "You likely handle issues, but you absorb the emotional weight and end up being the system for conflict resolution.",
            "That becomes exhausting because you are the shock absorber for tension across the team.",
            "The cost is fatigue, and eventually a team that waits for you to step in.",
            "Shift from fixer to coach: ask, 'What conversation needs to happen, and what is your first sentence going to be?'",
            roadmap("Awareness", "Notice where you take ownership of conflicts that are not yours to own.",
                    "Structure", "Create a team standard for handling tension early, with clear escalation rules.",
                    "Consistency", "Build conflict capability in the team so you lead the system, not every situation."),
            ctaText()
          )
        }
      },

      alignment: {
        label: "Team Alignment",
        subtitle: "Direction, priorities, and moving as one.",
        statements: [
          "My team works hard, but we do not always feel like we are moving in the same direction.",
          "I assume priorities are clear, then I notice people are working on different things.",
          "We start projects with energy, then momentum fades before completion.",
          "People ask for clarity that I thought I already gave.",
          "I feel like I have to keep reminding everyone what matters most.",
          "We do not have a consistent rhythm for setting priorities and reviewing progress.",
          "When results slip, it is not effort. It is focus."
        ],
        results: {
          avoidant: buildResultPack(
            "Your challenge is not effort. It is shared direction.",
            "You likely have priorities in your head, but the system to keep them alive is not fully built yet.",
            "Without a rhythm, teams default to urgent tasks, not important outcomes.",
            "The cost is rework, frustration, and slower progress.",
            "Set one weekly alignment rhythm: top 3 priorities, owners, and a simple progress check.",
            roadmap("Awareness", "Identify where alignment breaks: priorities, owners, timelines, or success definition.",
                    "Structure", "Create a weekly cadence and a written one-page priority list.",
                    "Consistency", "Repeat the rhythm until it becomes the culture, not a special initiative."),
            ctaText()
          ),
          inconsistent: buildResultPack(
            "You have direction, but it is not sticking across the team.",
            "Sometimes priorities are clear, then day-to-day noise takes over and people drift.",
            "That creates interruption and decision fatigue for you.",
            "The cost is a team that feels busy but not effective.",
            "Make priorities visible and binary: what is in, what is out, and what is next.",
            roadmap("Awareness", "Track where drift happens: mid-week, after new requests, or after meetings.",
                    "Structure", "Use a simple decision filter for new work and publish it to the team.",
                    "Consistency", "Hold weekly reviews that reinforce focus and remove misalignment early."),
            ctaText()
          ),
          strained: buildResultPack(
            "Your challenge is not strategy. It is maintaining alignment without carrying it alone.",
            "You might be the only person connecting dots, translating priorities, and protecting focus.",
            "That is exhausting, and it builds dependency.",
            "The cost is leadership fatigue and a team that waits for you to set direction repeatedly.",
            "Assign an 'alignment owner' for each priority to run updates and keep work on track without you driving every reminder.",
            roadmap("Awareness", "Notice where you are the glue for alignment and why.",
                    "Structure", "Install clear owners and a cadence for updates that does not rely on you.",
                    "Consistency", "Coach the team to self-correct misalignment using shared standards."),
            ctaText()
          )
        }
      },

      delegation: {
        label: "Delegation",
        subtitle: "Letting go without losing quality.",
        statements: [
          "I often keep tasks because it feels faster than explaining what I need.",
          "I delegate, but I still end up checking and correcting a lot.",
          "I worry that if I do not stay involved, quality will drop.",
          "My team could take more ownership, but they wait for my direction.",
          "I feel like too much still comes back to me at the end.",
          "I struggle to delegate outcomes instead of just tasks.",
          "Delegation feels risky when timelines are tight."
        ],
        results: {
          avoidant: buildResultPack(
            "Your challenge is not delegation. It is trust plus clarity.",
            "You likely hold tasks because quality and speed matter, and you do not want to create mistakes.",
            "That is understandable, but it traps you in doing instead of leading.",
            "The cost is overwhelm and a team that does not develop ownership.",
            "Delegate one outcome this week with three guardrails: definition of done, checkpoint date, and decision authority.",
            roadmap("Awareness", "Identify the work you keep out of habit, not necessity.",
                    "Structure", "Delegate outcomes with clear standards and checkpoints.",
                    "Consistency", "Build ownership by letting people learn, with guardrails not micromanagement."),
            ctaText()
          ),
          inconsistent: buildResultPack(
            "You delegate, but the handoff is not always clean.",
            "Sometimes delegation works, other times you step back in and take it over.",
            "That creates confusion and reduces confidence on both sides.",
            "The cost is wasted time and leadership frustration.",
            "Use one delegation script: 'Here is the outcome, here is success, here is the deadline, here is what you decide without me.'",
            roadmap("Awareness", "Spot when you take back work and what triggers it (pressure, quality, speed).",
                    "Structure", "Standardize delegation with clear expectations and checkpoints.",
                    "Consistency", "Coach progress instead of correcting at the end."),
            ctaText()
          ),
          strained: buildResultPack(
            "Your challenge is not capability. It is capacity.",
            "You likely delegate, but you are still the final bottleneck for approvals, quality, and decisions.",
            "That keeps you in constant interruption and context switching.",
            "The cost is burnout and slow execution.",
            "Move one decision boundary down: define what 'good' is, then stop being the default approver.",
            roadmap("Awareness", "Identify where you are the bottleneck: approvals, standards, or confidence.",
                    "Structure", "Create decision rights and quality standards that scale.",
                    "Consistency", "Develop leaders in your team who can own outcomes without you."),
            ctaText()
          )
        }
      },

      motivation: {
        label: "Motivation",
        subtitle: "Engagement, accountability, and energy.",
        statements: [
          "I care more than my team seems to care, and that frustrates me.",
          "I struggle to get consistent urgency from people without pushing them.",
          "I have high standards, but I do not always know how to motivate without pressure.",
          "Some team members do the minimum and it affects everyone else.",
          "I feel like I am carrying the energy for the whole group.",
          "Recognition and accountability do not feel balanced on my team.",
          "When performance drops, I take it personally."
        ],
        results: {
          avoidant: buildResultPack(
            "Your challenge is not motivation. It is clarity plus accountability.",
            "You likely want to inspire people, but you do not want to become the 'push' leader.",
            "Without clear standards and follow-through, motivation becomes inconsistent and emotional.",
            "The cost is frustration, lowered standards, and energy drain.",
            "Clarify one standard this week and make it visible. Then follow through once, calmly and consistently.",
            roadmap("Awareness", "Identify which standards are implied instead of explicit.",
                    "Structure", "Create simple accountability rhythms: expectations, check-ins, consequences.",
                    "Consistency", "Balance recognition with standards so motivation is not dependent on your mood."),
            ctaText()
          ),
          inconsistent: buildResultPack(
            "You can motivate, but you do not always have a consistent system for it.",
            "Sometimes you inspire, sometimes you push, and sometimes you let things slide.",
            "That inconsistency trains the team to wait for pressure instead of owning performance.",
            "The cost is cycles of urgency and drop-off.",
            "Set a weekly scoreboard: 2 to 3 key behaviors, tracked, recognized, and addressed when missed.",
            roadmap("Awareness", "Notice where performance slips and why (standards, clarity, accountability).",
                    "Structure", "Install a simple system for expectations, coaching, and consequences.",
                    "Consistency", "Make motivation repeatable through culture, not spikes of pressure."),
            ctaText()
          ),
          strained: buildResultPack(
            "Your challenge is not motivating people. It is carrying the emotional weight of performance.",
            "You likely lead hard, care deeply, and feel responsible for team outcomes.",
            "That can turn motivation into personal burden.",
            "The cost is fatigue, impatience, and a team that depends on your energy.",
            "Shift the ownership question: 'What are you committed to this week, and how will you measure it?'",
            roadmap("Awareness", "Recognize where you absorb responsibility that belongs to the team.",
                    "Structure", "Build shared commitments and visible metrics that create ownership.",
                    "Consistency", "Develop a culture where performance is owned by everyone, not carried by you."),
            ctaText()
          )
        }
      }
    };

    function ctaText(){
      return `If you want a repeatable system to solve this long term, ${CONFIG.brandName} is designed to build clarity, structure, and confident execution with your team.`;
    }

    function roadmap(p1t,p1b,p2t,p2b,p3t,p3b){
      return {
        p1: { title: p1t, body: p1b },
        p2: { title: p2t, body: p2b },
        p3: { title: p3t, body: p3b }
      };
    }

    function buildResultPack(headline, whats, why, cost, quick, roadmapObj, cta){
      return { headline, whats, why, cost, quick, roadmap: roadmapObj, cta };
    }

    // -----------------------------
    // State
    // -----------------------------
    const state = {
      screen: "start",
      pathKey: null,
      qIndex: 0,
      answers: [], // {statementIndex, scaleKey, value}
      name: "",
      email: ""
    };

    // -----------------------------
    // DOM helpers
    // -----------------------------
    const $ = (id) => document.getElementById(id);

    const screens = {
      start: $("screenStart"),
      choose: $("screenChoose"),
      intro: $("screenIntro"),
      question: $("screenQuestion"),
      email: $("screenEmail"),
      results: $("screenResults")
    };

    function showScreen(key){
      Object.values(screens).forEach(el => el.classList.add("hidden"));
      screens[key].classList.remove("hidden");
      state.screen = key;
      updateStatusPill();
      window.scrollTo({ top: 0, behavior: "smooth" });
    }

    function updateStatusPill(){
      const pill = $("statusPill");
      const labelMap = {
        start: "Private. 5 minutes.",
        choose: "Pick one area.",
        intro: "Quick path. No judgment.",
        question: "One question at a time.",
        email: "Optional.",
        results: "Your roadmap."
      };
      pill.textContent = labelMap[state.screen] || "Private.";
    }

    // -----------------------------
    // Render area tiles
    // -----------------------------
    function renderTiles(){
      const holder = $("areaTiles");
      holder.innerHTML = "";
      const items = Object.entries(PATHS).map(([key, val]) => ({ key, ...val }));
      items.forEach(item => {
        const btn = document.createElement("button");
        btn.className = "tile";
        btn.type = "button";
        btn.innerHTML = `<strong>${item.label}</strong><span>${item.subtitle}</span>`;
        btn.addEventListener("click", () => selectPath(item.key));
        holder.appendChild(btn);
      });
    }

    function selectPath(pathKey){
      state.pathKey = pathKey;
      state.qIndex = 0;
      state.answers = [];
      const label = PATHS[pathKey].label;
      $("introTitle").textContent = "You chose: " + label;
      $("chipCount").textContent = "Questions: " + PATHS[pathKey].statements.length;
      showScreen("intro");
    }

    // -----------------------------
    // Question screen
    // -----------------------------
    function renderQuestion(){
      const path = PATHS[state.pathKey];
      const total = path.statements.length;
      const idx = state.qIndex;

      $("pathLabel").textContent = path.label;
      $("qCounter").textContent = `Question ${idx + 1} of ${total}`;

      const pct = Math.round((idx / total) * 100);
      $("progressBar").style.width = `${pct}%`;

      $("questionText").textContent = path.statements[idx];

      const choices = $("choices");
      choices.innerHTML = "";

      const existing = state.answers.find(a => a.statementIndex === idx);
      let selectedKey = existing ? existing.scaleKey : null;

      SCALE.forEach(opt => {
        const row = document.createElement("div");
        row.className = "choice" + (selectedKey === opt.key ? " selected" : "");
        row.setAttribute("role","button");
        row.setAttribute("tabindex","0");
        row.innerHTML = `
          <div>
            <div>${opt.label}</div>
            <small>${opt.value} point${opt.value === 1 ? "" : "s"}</small>
          </div>
          <div class="tiny">${selectedKey === opt.key ? "Selected" : ""}</div>
        `;
        const choose = () => {
          selectedKey = opt.key;
          // upsert answer
          const existingIndex = state.answers.findIndex(a => a.statementIndex === idx);
          const payload = { statementIndex: idx, scaleKey: opt.key, value: opt.value };
          if(existingIndex >= 0) state.answers[existingIndex] = payload;
          else state.answers.push(payload);

          // rerender to update selected styling
          renderQuestion();
          $("btnQNext").disabled = false;
        };
        row.addEventListener("click", choose);
        row.addEventListener("keydown", (e) => {
          if(e.key === "Enter" || e.key === " ") { e.preventDefault(); choose(); }
        });
        choices.appendChild(row);
      });

      $("btnQNext").disabled = !state.answers.some(a => a.statementIndex === idx);
    }

    function goNextQuestion(){
      const path = PATHS[state.pathKey];
      const total = path.statements.length;

      if(state.qIndex < total - 1){
        state.qIndex += 1;
        renderQuestion();
        return;
      }
      // Finished questions
      $("progressBar").style.width = "100%";
      showScreen("email");
    }

    function goPrevQuestion(){
      if(state.qIndex > 0){
        state.qIndex -= 1;
        renderQuestion();
      } else {
        showScreen("intro");
      }
    }

    // -----------------------------
    // Results
    // -----------------------------
    function computeScore(){
      const path = PATHS[state.pathKey];
      const totalStatements = path.statements.length;

      // Ensure answers are complete. If not, treat missing as 0 (should not happen due to UI gating).
      let sum = 0;
      for(let i=0;i<totalStatements;i++){
        const found = state.answers.find(a => a.statementIndex === i);
        sum += found ? found.value : 0;
      }
      return sum;
    }

    function pickProfile(score){
      return PROFILES.find(p => score >= p.min && score <= p.max) || PROFILES[1];
    }

    function renderResults(){
      const path = PATHS[state.pathKey];
      const score = computeScore();
      const profile = pickProfile(score);

      const pack = path.results[profile.key];
      const name = (state.name || "").trim();

      $("resultsHeadline").textContent = pack.headline;
      $("resultsBadge").textContent = profile.label;

      // subhead uses name if present
      $("resultsSubhead").textContent = name
        ? `${name}, here is what your answers suggest in the area of ${path.label}.`
        : `Here is what your answers suggest in the area of ${path.label}.`;

      $("resultsWhatsHappening").textContent = pack.whats;
      $("resultsWhyExhausting").textContent = pack.why;
      $("resultsHiddenCost").textContent = pack.cost;
      $("resultsQuickWin").textContent = pack.quick;

      $("rm1Title").textContent = pack.roadmap.p1.title;
      $("rm1Body").textContent = pack.roadmap.p1.body;
      $("rm2Title").textContent = pack.roadmap.p2.title;
      $("rm2Body").textContent = pack.roadmap.p2.body;
      $("rm3Title").textContent = pack.roadmap.p3.title;
      $("rm3Body").textContent = pack.roadmap.p3.body;

      $("resultsCTA").textContent = pack.cta;

      $("btnOffer").href = CONFIG.offerUrl;

      $("resultsNote").textContent =
        `Internal data you can capture: path="${state.pathKey}", profile="${profile.key}", score=${score}.`;

      // Store summary for copy button
      state.profileKey = profile.key;
      state.profileLabel = profile.label;
      state.score = score;
      state.pathLabel = path.label;
    }

    function resultsTextForClipboard(){
      const path = PATHS[state.pathKey];
      const profile = pickProfile(state.score);
      const pack = path.results[profile.key];

      const lines = [];
      lines.push("Leadership Clarity Assessment");
      lines.push(`Path: ${path.label}`);
      lines.push(`Profile: ${profile.label}`);
      lines.push(`Score: ${state.score}`);
      lines.push("");
      lines.push(pack.headline);
      lines.push("");
      lines.push("What’s really happening:");
      lines.push(pack.whats);
      lines.push("");
      lines.push("Why this feels exhausting:");
      lines.push(pack.why);
      lines.push("");
      lines.push("The hidden cost:");
      lines.push(pack.cost);
      lines.push("");
      lines.push("One immediate action:");
      lines.push(pack.quick);
      lines.push("");
      lines.push("Roadmap:");
      lines.push(`- ${pack.roadmap.p1.title}: ${pack.roadmap.p1.body}`);
      lines.push(`- ${pack.roadmap.p2.title}: ${pack.roadmap.p2.body}`);
      lines.push(`- ${pack.roadmap.p3.title}: ${pack.roadmap.p3.body}`);
      lines.push("");
      lines.push("Next step:");
      lines.push(pack.cta);
      lines.push("");
      lines.push(`Offer: ${CONFIG.offerUrl}`);
      return lines.join("\n");
    }

    async function copyResults(){
      const text = resultsTextForClipboard();
      try{
        await navigator.clipboard.writeText(text);
        $("btnCopy").textContent = "Copied";
        setTimeout(() => $("btnCopy").textContent = "Copy my results", 1400);
      }catch(err){
        alert("Copy failed. Your browser may block clipboard access on file://. Try on a hosted page.");
      }
    }

    // -----------------------------
    // Wiring events
    // -----------------------------
    renderTiles();

    $("btnStart").addEventListener("click", () => showScreen("choose"));
    $("btnPreview").addEventListener("click", () => showScreen("choose"));
    $("btnBackToStart").addEventListener("click", () => showScreen("start"));

    $("btnIntroBack").addEventListener("click", () => showScreen("choose"));
    $("btnIntroNext").addEventListener("click", () => {
      showScreen("question");
      renderQuestion();
    });

    $("btnQNext").addEventListener("click", () => goNextQuestion());
    $("btnQBack").addEventListener("click", () => goPrevQuestion());

    $("btnEmailSkip").addEventListener("click", () => {
      state.name = "";
      state.email = "";
      showResultsNow();
    });

    $("btnEmailContinue").addEventListener("click", () => {
      state.name = $("nameInput").value || "";
      state.email = $("emailInput").value || "";
      showResultsNow();
    });

    function showResultsNow(){
      showScreen("results");
      renderResults();
    }

    $("btnRestart").addEventListener("click", () => {
      // reset state
      state.pathKey = null;
      state.qIndex = 0;
      state.answers = [];
      state.name = "";
      state.email = "";
      $("nameInput").value = "";
      $("emailInput").value = "";
      showScreen("start");
    });

    $("btnCopy").addEventListener("click", () => copyResults());

    // Initialize offer link
    $("btnOffer").href = CONFIG.offerUrl;

    // Start screen
    showScreen("start");
  </script>
</body>
</html>
