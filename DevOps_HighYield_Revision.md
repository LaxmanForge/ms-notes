# DevOps Process Automation — High-Yield Revision Sheet
### Triaged by Marks Value, Not Reading Order

**How to use this in the time you have:**
- **Tier 1** = read + recite out loud twice each. This is the bulk of your marks. Do not skip any of these.
- **Tier 2** = read once, make sure you can say the keyword and one sentence. Skim the example.
- **Tier 3** = only if Tier 1 and 2 are solid and you still have time left.
---

## TIER 1 — MUST KNOW COLD (this is ~70% of your marks)

### 1. Shift-Left Testing
**One line:** Move testing as EARLY as possible in the pipeline — ideally to the moment code is committed — instead of a separate QA phase at the end.
**Say this:** "Traditional testing finds bugs late and expensive; DevOps shifts testing left so bugs are caught in minutes, cheap and immediate."

### 2. The Test Pyramid
```
        /\        Few: End-to-End / UI Tests (slow, expensive)
       /  \
      / -- \       Some: Integration Tests
     /------\
    /--------\      Many: Unit Tests (fast, cheap) <- base
```
**Say this:** "Many fast unit tests at the base, fewer integration tests in the middle, very few slow UI/E2E tests at the top. Inverting this (too many slow UI tests) is the classic anti-pattern to name."

### 3. DevSecOps — the 5 scan types (name ALL of them)
| Scan | What it checks | When |
|---|---|---|
| SAST | Source code, statically (not running) | Commit/build time |
| DAST | Running application, from outside | Pre-deployment |
| SCA | Third-party dependencies for known CVEs | Commit/build time |
| IaC Scanning | Terraform/CloudFormation misconfig | Before provisioning |
| Secrets Scanning | Accidentally committed credentials | Commit time |
**Say this:** "DevSecOps = shifting security left, the same idea as shift-left testing, applied to security. Security becomes everyone's job, not just a separate team's final gate."

### 4. Git: Distributed vs Centralized (the ONE fact that matters)
**Say this:** "Every Git clone has the FULL project history, not just the latest snapshot — that's what makes it distributed. No single point of failure; commits/branching/history all work offline."

### 5. Git Branching Strategies — compare all three, know which fits which project
| Strategy | Structure | Best for |
|---|---|---|
| Git Flow | main + develop + feature/* + release/* + hotfix/* | Scheduled, versioned releases |
| GitHub Flow | main + short-lived feature branches via PR | Continuous deployment / web apps |
| Trunk-Based Dev | Everyone commits to one trunk, multiple times/day, uses feature flags | High-velocity teams, true CI/CD |
**Say this:** "Git Flow is the most structured (has develop + release + hotfix branches). GitHub Flow is the simplest (just main + feature branches + PR). Trunk-Based skips long-lived branches almost entirely."

### 6. Jenkins: Controller vs Agent
**Say this:** "Controller (master) hosts job config, the UI, and scheduling. Agents (slaves) are the actual worker machines that run the build steps. This split is what lets Jenkins scale — add more agents, run more builds in parallel."

### 7. Jenkinsfile — Declarative Pipeline structure (be able to write this from memory)
```groovy
pipeline {
    agent any
    stages {
        stage('Checkout') { steps { git 'https://github.com/example/app.git' } }
        stage('Build')    { steps { sh 'mvn clean package' } }
        stage('Test')     { steps { sh 'mvn test' } }
        stage('Deploy')   { steps { sh './deploy.sh' } }
    }
}
```
**Say this:** "Freestyle jobs are configured by clicking through the UI — not version-controlled. Pipeline/Jenkinsfile is code, checked into Git alongside the app, reviewable and reproducible — this is why Pipeline-as-Code is preferred."

### 8. Final Artifact — "Build Once, Deploy Many Times"
**Say this:** "The exact same tested artifact (JAR/WAR/Docker image) that passed staging is what gets promoted to production — never rebuilt per environment. Rebuilding risks the deployed code not matching what was actually tested."

---

## TIER 2 — SHOULD KNOW (keyword + one line is enough)

### 9. Test Integration by Pipeline Stage
Commit (unit tests, static analysis) → Build (integration tests) → Pre-deployment (security + performance tests) → Pre-release (acceptance/UI/smoke tests). **Say this:** "Fast/cheap tests run first, so failures are caught before wasting time on slow/expensive later stages."

### 10. DevOps Testing Tools — one per category
| Category | Tool example |
|---|---|
| Unit | JUnit / pytest |
| API/Integration | Postman / RestAssured |
| UI/E2E | Selenium / Cypress |
| Performance | JMeter / Gatling |
| Security | OWASP ZAP / SonarQube |
| CI Orchestration | Jenkins / GitLab CI |

### 11. Managing Build Dependencies
Two layers: (1) Build-tool level — `pom.xml`/`package.json` pins library versions, pulled from Nexus/Artifactory. (2) Jenkins-level — Global Tool Configuration pins JDK/Maven version so every agent builds identically.

### 12. Continuous Testing — why it matters (not just what it is)
Immediate feedback (minutes not weeks) → de-risks frequent deployment → cheaper bug fixes the earlier they're caught → enough confidence to automate release decisions.

### 13. Building the Code — why it's needed
Consistency (same output every time) + dependency resolution (correct versions auto-fetched) + early error detection (compile errors caught before runtime).

---

## TIER 3 — QUICK SKIM ONLY IF TIME REMAINS

- **Git install:** Ubuntu = `sudo apt install git`; Windows = installer from git-scm.com, bundles **Git Bash**. Both need `git config --global user.name/user.email` before first commit.
- **Jenkins CLI:** `java -jar jenkins-cli.jar -s JENKINS_URL -auth USER:TOKEN build JOB_NAME` — broader than the remote trigger URL (can list jobs, manage plugins, read config too).
- **Testing strategy tips:** automate the most-run tests first, keep environments production-like, monitor for flaky tests.

---

## WEAK SPOT DRILL — you missed these on the diagnostic. Do this section last.

### Fix #1 — Git Flow vs GitHub Flow vs Trunk-Based (Q6)
The trap: all three sound similar. Anchor on ONE distinguishing feature each:
- **Git Flow** → has a `develop` branch (the extra one nobody else has).
- **GitHub Flow** → ONLY `main` + feature branches. No `develop`. Merges via Pull Request.
- **Trunk-Based** → no real branches at all, everyone pushes to trunk multiple times a day, uses **feature flags** to hide unfinished work.
**Drill it:** cover the table above, say all three from memory including which project type each suits, three times in a row.

### Fix #2 — Jenkins Remote Trigger URL (Q7)
The exact pattern, memorize character-for-character:
```
JOB_URL/build?token=TOKEN
```
- It's scoped to a specific **job**, not the whole Jenkins server.
- A GitHub/GitLab **webhook** is just an automated caller of this exact same URL — that's the connection to remember.
**Drill it:** write this URL pattern from memory 3 times on scratch paper right now.

### Fix #3 — Job Chaining: `wait: true` vs `wait: false` (Q8)
```groovy
build job: 'downstream-app-build', wait: true
```
- `wait: true` → upstream job **pauses and blocks** until downstream finishes; if downstream fails, upstream can be marked failed too. **Synchronous.**
- `wait: false` → upstream fires the downstream job and **immediately moves on** without waiting. **Asynchronous.**
**Drill it:** say out loud — "true waits, false fires-and-forgets" — three times.

---

## LAST-5-MINUTES RECITE LIST (say all 8 out loud once before you walk in)
```
[ ] Shift-left = testing/security moved as early as possible
[ ] Test pyramid = many unit, some integration, few UI/E2E
[ ] SAST=static code / DAST=running app / SCA=dependencies / IaC scan / secrets scan
[ ] Git = distributed = full history per clone = no single point of failure
[ ] Git Flow has develop / GitHub Flow is just main+feature+PR / Trunk-Based uses feature flags
[ ] Jenkins Controller = config+UI / Agent = actually runs builds
[ ] Pipeline-as-Code (Jenkinsfile) preferred over Freestyle: versioned, reviewable
[ ] Build once, deploy many times = same artifact promoted, never rebuilt per environment
```
