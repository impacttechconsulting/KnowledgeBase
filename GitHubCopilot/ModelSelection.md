

#### Model Capabilities Matrix

| Model                   | Multiplier | Speed    | Code Quality | Reasoning | Context | Vision | Best For                                          |
| ----------------------- | ---------- | -------- | ------------ | --------- | ------- | ------ | ------------------------------------------------- |
| GPT-4.1                 | 0x         | Fast     | Good         | Good      | 128K    | ✅     | Balanced general tasks, included in all plans     |
| GPT-5 mini              | 0x         | Fastest  | Good         | Basic     | 128K    | ❌     | Simple tasks, quick responses, cost-effective     |
| GPT-5                   | 1x         | Moderate | Excellent    | Advanced  | 128K    | ✅     | Complex code, advanced reasoning, multi-turn chat |
| GPT-5 Codex             | 1x         | Fast     | Excellent    | Good      | 128K    | ❌     | Code optimization, refactoring, algorithmic tasks |
| Claude Sonnet 3.5       | 1x         | Moderate | Excellent    | Excellent | 200K    | ✅     | Code generation, long context, balanced reasoning |
| Claude Sonnet 4         | 1x         | Moderate | Excellent    | Advanced  | 200K    | ❌     | Complex code, robust reasoning, enterprise tasks  |
| Claude Sonnet 4.5       | 1x         | Moderate | Excellent    | Expert    | 200K    | ✅     | Advanced code, architecture, design patterns      |
| Claude Opus 4.1         | 10x        | Slow     | Outstanding  | Expert    | 1M      | ✅     | Large codebases, architectural review, research   |
| Gemini 2.5 Pro          | 1x         | Moderate | Excellent    | Advanced  | 2M      | ✅     | Very long context, multi-modal, real-time data    |

#### Selection Decision Tree

```
START
  │
  ├─ Task Complexity?
  │   ├─ Simple/Repetitive → GPT-5 mini, Grok Code Fast 1, GPT-4.1
  │   ├─ Moderate → GPT-4.1, Claude Sonnet 4, GPT-5
  │   └─ Complex/Advanced → Claude Sonnet 4.5, GPT-5, Gemini 2.5 Pro, Claude Opus 4.1
  │
  ├─ Reasoning Depth?
  │   ├─ Basic → GPT-5 mini, Grok Code Fast 1
  │   ├─ Intermediate → GPT-4.1, Claude Sonnet 4
  │   ├─ Advanced → GPT-5, Claude Sonnet 4.5
  │   └─ Expert → Claude Opus 4.1, o3 (deprecated)
  │
  ├─ Code-Specific?
  │   ├─ Yes → GPT-5 Codex, Claude Sonnet 4.5, GPT-5
  │   └─ No → GPT-5, Claude Sonnet 4
  │
  ├─ Context Size?
  │   ├─ Small (<50K tokens) → Any model
  │   ├─ Medium (50-200K) → Claude models, GPT-5, Gemini
  │   ├─ Large (200K-1M) → Gemini 2.5 Pro, Claude Opus 4.1
  │   └─ Very Large (>1M) → Gemini 2.5 Pro (2M), Claude Opus 4.1 (1M)
  │
  ├─ Vision Required?
  │   ├─ Yes → GPT-4.1, GPT-5, Claude Sonnet 3.5/4.5, Gemini 2.5 Pro, Claude Opus 4.1
  │   └─ No → All models
  │
  ├─ Cost Sensitivity? (based on subscriptionTier)
  │   ├─ Free Tier → 0x models only: GPT-4.1, GPT-5 mini, Grok Code Fast 1
  │   ├─ Pro (1000 premium/month) → Prioritize 0x, use 1x judiciously, avoid 10x
  │   └─ Pro+ (5000 premium/month) → 1x freely, 10x for critical tasks
  │
  └─ Priority Factor?
      ├─ Speed → GPT-5 mini, Grok Code Fast 1, Gemini 2.0 Flash
      ├─ Cost → 0x models (GPT-4.1, GPT-5 mini) or lower multipliers (0.25x, 0.33x)
      ├─ Quality → Claude Sonnet 4.5, GPT-5, Claude Opus 4.1
      └─ Balanced → GPT-4.1, Claude Sonnet 4, GPT-5
```

**Categorize Task Type**:

Identify the primary task category based on content analysis:

1. **Simple Repetitive Tasks**:

   - Pattern: Formatting, simple refactoring, adding comments/docstrings, basic CRUD
   - Characteristics: Straightforward logic, minimal context, fast execution preferred
   - Keywords: format, comment, simple, basic, add docstring, rename, move

2. **Code Generation & Implementation**:

   - Pattern: Writing functions/classes, implementing features, API endpoints, tests
   - Characteristics: Moderate complexity, domain knowledge, idiomatic code
   - Keywords: implement, create, generate, write, build, scaffold

3. **Complex Refactoring & Architecture**:

   - Pattern: System design, architectural review, large-scale refactoring, performance optimization
   - Characteristics: Deep reasoning, multiple components, trade-off analysis
   - Keywords: architect, refactor, optimize, design, scale, review architecture

4. **Debugging & Problem-Solving**:

   - Pattern: Bug fixing, error analysis, systematic troubleshooting, root cause analysis
   - Characteristics: Step-by-step reasoning, debugging context, verification needs
   - Keywords: debug, fix, troubleshoot, diagnose, error, investigate

5. **Planning & Research**:

   - Pattern: Feature planning, research, documentation analysis, ADR creation
   - Characteristics: Read-only, context gathering, decision-making support
   - Keywords: plan, research, analyze, investigate, document, assess

6. **Code Review & Quality Analysis**:

   - Pattern: Security analysis, performance review, best practices validation, compliance checking
   - Characteristics: Critical thinking, pattern recognition, domain expertise
   - Keywords: review, analyze, security, performance, compliance, validate

7. **Specialized Domain Tasks**:

   - Pattern: Django/framework-specific, accessibility (WCAG), testing (TDD), API design
   - Characteristics: Deep domain knowledge, framework conventions, standards compliance
   - Keywords: django, accessibility, wcag, rest, api, testing, tdd

8. **Advanced Reasoning & Multi-Step Workflows**:
   - Pattern: Algorithmic optimization, complex data transformations, multi-phase workflows
   - Characteristics: Advanced reasoning, mathematical/algorithmic thinking, sequential logic
   - Keywords: algorithm, optimize, transform, sequential, reasoning, calculate
