# Advanced R Package Development Workshop - Context File

**IMPORTANT:** Please update this file regularly as we develop the course materials and make decisions. This helps maintain shared context when working with Claude.

---

## Workshop Overview

- **Duration:** 3 consecutive half-days in February 2026
- **Time:** 8:00 AM - 12:30 PM daily
- **Format:** Three 80-minute sessions per day with 15-minute breaks
- **Participant Level:** Predominantly beginners (11/17 built 1-2 packages), 5 intermediate

---

## Survey Results Summary (17 responses)

### Key Insights - KEEP THESE TOP OF MIND

**Previous workshop:**
- 5/17 attended previous workshop

**Experience Level:**
- 11/17 participants are beginners (built 1-2 basic packages)
- 5/17 are intermediate (built several packages)
- This is a beginner-focused group - pace accordingly!

**IDE Preference:**
- 10/17 prefer RStudio
- 7/17 have no preference
- Use RStudio as primary IDE, show Positron equivalents when relevant

**Review Time Needed:**
- 14/17 want moderate review (2-3 hours)
- 1/17 wants substantial review (half day)
- Allocated half of Day 1 to fundamentals review

**HIGH PRIORITY TOPICS** (selected by 9+ participants):
1. Function design best practices - 16/17 selected ⭐
2. Advanced testing with testthat - 14/17 selected ⭐
3. Debugging techniques - 16/17 selected ⭐
5. Package versioning and releasing - 13/17 selected ⭐
4. Object-oriented programming - 11/17 selected ⭐

**MEDIUM PRIORITY:**
- Git/GitHub PR workflows - 10/17 very, 6/17 somewhat interested
- Including data in packages - 11 very interested, 5 somewhat interested
- Web APIs - Mixed interest

**LOWER PRIORITY:**
- GitLab Workflow extension - Mostly "somewhat interested"
- User secrets - Mostly "somewhat interested"
- AI-assisted development - Mixed, several not interested

**BYOP (Bring Your Own Package):**
- Most prefer more instruction over BYOP time
- Some open to it "if time permits"
- Decision: Final 80-min session only

### Special Requests from Survey:
- One participant asked about compilable/pre-compiled models in packages (DECISION: too specialized, skip)
- Interest in handling sensitive data (API keys, passwords) - included in Day 3

---

## Key Decisions Made

✅ **Included Topics:**
- Review of fundamentals and pain points (half of Day 1)
- Git/GitHub for collaborative development + PR workflow
- Object-oriented programming (S3, S4, R6)
- Debugging techniques
- Function design best practices (naming, default arguments, ellipsis, composition, pure functions)
- Advanced testing with testthat (clean tests, snapshot testing, mocking)
- Package versioning and releasing
- Data packages (internal/external data)
- BYOP time (final 80 minutes)

❌ **Excluded Topics:**
- Using tidyverse in packages (skipped to focus on higher priorities, may touch on organically)
- Compilable/pre-compiled models (too specialized - one-off request)
- LLMs for testing/documentation
- Connecting to databases
- AI-assisted development (low survey interest)

❓ **Brief Coverage:**
- GitLab Workflow extension (brief mention, though not using Positron so extensions are less relevant)
- Web APIs (brief coverage given mixed interest - mention httr2, could do in BYOP)
- User secrets/API keys (brief coverage)
- Advanced vignettes with quarto (20-25 min in final session)

---

## Schedule Structure

See `course-schedule.qmd` for full schedule.

**Day 1:** Foundations - fundamentals review, Git/GitHub, testing part 1
**Day 2:** Robust Development - function design, testing part 2, debugging
**Day 3:** Advanced Topics - OOP, data packages, releasing, BYOP

---

## Files in This Project

### Core Content Files
- `course-schedule.qmd` - Main schedule (Quarto format for website)
- `index.qmd` - Website homepage
- `CLAUDE.md` - This file (shared context, not rendered on site)

**Day 1 Sessions:**
- `package-fundamentals.qmd` - Session 1: Package Creation and Metadata
- `git-github.qmd` - Session 2: Git/GitHub for Collaborative Development
- `testing-part1.qmd` - Session 3: Testing with testthat - Part 1

**Day 2 Sessions:**
- `function-design-best-practices.qmd` - Session 1: Function Design Best Practices (naming, defaults, ellipsis, composition, pure functions - uses `log` package as running example)
- `testing-part2.qmd` - Session 2: Testing with testthat - Part 2 (snapshot review, withr/clean tests, covr)
- `documentation.qmd` - Session 3 (first 20 min, before debugging): Advanced Documentation (`@inheritParams`, `@inheritDotParams`, Markdown cross-references)
- `debugging-techniques.qmd` - Session 3 (last 60 min): Debugging Techniques

**Day 3 Sessions:**
- `object-oriented-programming.qmd` - Session 1: Object-Oriented Programming (S3, S4, R6)
- `data-packages.qmd` - Session 2: Data in Packages (static data via use_data(), httr2 API functions, internal data - uses Kluane Lake Trout dataset from Parks Canada)
- `releasing-your-r-package.qmd` - Session 3: Releasing Your R Package (stub)
- `releasing-slides.qmd` - RevealJS slides for releasing session (licensing, distribution options, R-Universe setup, CRAN submission)
- `releasing-your-r-package.qmd` - Session 2: Releasing Your R Package (stub)
  - `releasing-slides.qmd` - RevealJS slides for releasing session (licensing, distribution options, R-Universe setup, CRAN submission)

**Other Content:**
- `setup.qmd` - System setup instructions for participants
- `_parking-lot.qmd` - Parking lot / scratch notes

### Example Package: fishr
The course uses the `fishr` package as a running example throughout all sessions.

- **GitHub:** https://github.com/boshek/fishr
- **Example PR:** https://github.com/boshek/fishr/pull/1

View with gh cli: `gh pr view 1 --repo boshek/fishr`

**To learn about the current structure and source code of the fishr package, consult the repo directly:** use `gh api` or `gh browse` against https://github.com/boshek/fishr. Do not guess at file contents - fetch them.

**Package contents:**
- `R/cpue.R` - Main function with verbose and options support
- `R/biomass.R` - biomass_index function (added via PR workflow in Session 2)
- `tests/testthat/test-cpue.R` - Comprehensive tests matching testing-part1.qmd
- `tests/testthat/test-biomass.R` - Tests for biomass_index
- `tests/testthat/helper.R` - Test helpers (generate_fishing_data, expected_cpue)
- `tests/testthat/setup.R` - Test fixtures (reference_data)

### Website Infrastructure
- `_quarto.yml` - Quarto website configuration
- `style-light.scss` - Light theme customization
- `style-dark.scss` - Dark theme customization
- `air.toml` - Air formatter configuration
- `.gitignore` - Git ignore patterns

### Governance
- `CODE_OF_CONDUCT.md` - Contributor Covenant v2.1
- `LICENSE.md` - Creative Commons Attribution-ShareAlike 4.0 International
- `README.md` - Project README


---

## Notes for Course Development

**STYLE:**
- Use Canadian English spellings throughout all course materials (behaviour, colour, centre, etc.). Code identifiers that match R conventions (e.g., `center` in `scale()`) are exempt.

**REMEMBER:**
- This is a beginner-focused group - don't assume advanced knowledge
- Each session should include practical exercises, not just lecture
- Participants want substantial instruction time over self-directed work
- Build progressively from fundamentals to advanced
- Keep RStudio as primary IDE but be ready to show Positron equivalents

**TODO (update as we work):**

**Day 1 Content:**
- [x] Day 1, Session 1: Package Development Fundamentals (`package-fundamentals.qmd`)
- [x] Day 1, Session 2: Git/GitHub for Collaborative Development (`git-github.qmd`)
- [x] Day 1, Session 3: Testing with testthat - Part 1 (`testing-part1.qmd`)

**Day 2 Content:**
- [x] Day 2, Session 1: Function Design Best Practices (`function-design-best-practices.qmd`)
- [x] Day 2, Session 2: Testing with testthat - Part 2 (`testing-part2.qmd`)
- [x] Day 2, Session 3: (first 20 min): Advanced Documentation (`documentation.qmd`)
- [x] Day 2, Session 3 (last 60 min): Debugging Techniques (`debugging-techniques.qmd`)

**Day 3 Content:**
- [x] Day 3, Session 1: Object-Oriented Programming (80 min) (`object-oriented-programming.qmd` - PR #15)
- [~] Day 3, Session 2: Data Packages (60 min) 
- [x] Day 3, Session 2: Releasing (20 min) (`releasing-your-r-package.qmd` - PR #16)
- [ ] Day 3, Session 3: BYOP + Advanced Vignettes (80 min)

**Other Tasks:**
- [x] Prepare example package for hands-on work (fishr)
- [x] Create test-writing exercises (in testing-part1.qmd)
- [x] Prepare debugging scenarios
- [x] Develop OOP examples
- [ ] Create slides or presentation materials

---

## Update Log

- 2026-01-03: Initial context file created with survey analysis and schedule decisions
- 2026-01-06: Set up project infrastructure
  - Created Quarto website with light/dark themes
  - Added CODE_OF_CONDUCT.md and LICENSE.md (CC BY-SA 4.0)
  - Configured GitHub repo: https://github.com/boshek/2026-feb-course-planning
  - Created Day 1, Session 1 content (`fundamentals-review.qmd`) by adapting materials from Nov 2024 course
  - Maintained code-first style with emoji headers and minimal prose from original course
- 2026-01-09:
  - Update survey results (now 17 responses!)
  - Comments on topic scopes
- 2026-01-13:
  - Completed Day 1 content files using fishr package as running example
  - Created `package-fundamentals.qmd` (Session 1) - package creation, metadata, documentation
  - Created `git-github.qmd` (Session 2) - GitHub setup, CI, air formatter, PR workflows
  - Created `testing-part1.qmd` (Session 3) - testthat, clean tests with withr, helpers/fixtures, snapshots
  - Updated fishr package to include all code shown in course materials:
    - Added verbose parameter and options support to cpue()
    - Added biomass_index() function
    - Added comprehensive test suite matching testing-part1.qmd
    - Added helper.R and setup.R test infrastructure
  - Updated _quarto.yml sidebar with Day 1 sessions
  - Removed emojis from headers per style preference
- 2026-01-23:
  - Added `_parking-lot.qmd` for scratch notes
  - Began `function-design-best-practices.qmd` with input validation examples
  - Started `releasing-your-r-package.qmd` stub
- 2026-02-02 to 2026-02-05:
  - Substantially built out `testing-part2.qmd`:
    - Snapshot updating and review workflow (snapshot_review/snapshot_accept)
    - Clean tests with withr (local_options, with_options, local_tempfile, local_seed, etc.)
    - "Your turn" exercise: add verbose to biomass_index and write tests
    - Test coverage with covr (package_coverage, zero_coverage, report, interactive checking)
    - CI coverage setup with GitHub Actions and Codecov (including non-Codecov alternative)
    - Coverage philosophy guidance
  - Refined `testing-part1.qmd`: removed error class test, added expect_warning, restructured snapshot flow
  - Updated `course-schedule.qmd` with instructor assignments and refined session descriptions
  - Updated `_quarto.yml` sidebar with Day 2 sessions
- 2026-02-16:
  - Created `debugging-techniques.qmd` (Day 2, Session 3):
    - Reading error messages and traceback()
    - Print/message debugging (message vs cat vs print)
    - browser() interactive debugging with commands table
    - RStudio breakpoints, debug()/debugonce(), options(error = recover)
    - Debugging failing tests (browser in tests, state leakage, snapshot mismatches)
    - rlang::last_trace() and last_error()
    - "Your turn" exercise: buggy standardize_effort() function
  - Added debugging-techniques.qmd to _quarto.yml sidebar
- 2026-02-08 to 2026-02-17:
  - Completed `function-design-best-practices.qmd` (Day 2, Session 1): naming conventions, default arguments, ellipsis, composition, pure functions - uses `log` package as running example
  - Further refined `testing-part1.qmd`: added testing patterns, use_testthat_helper(), narrative and tip improvements
  - Minor fixes and polish across `package-fundamentals.qmd`, `git-github.qmd`, `testing-part2.qmd`
  - Substantially updated `setup.qmd`: refined package list and setup instructions
  - `README.md` tweaks
  - Created `object-oriented-programming.qmd` (PR #15 - Day 3, Session 1)
- 2026-02-20:
  - Added R-Universe setup slides to `releasing-slides.qmd`: two new slides covering the four-step setup process (create GitHub repo, packages.json, install GitHub App, wait for build) and user installation patterns
- 2026-02-21:
  - Created and substantially revised `data-packages.qmd` (Day 3, Session 2):
    - Static exported data: `horsefly_sample` (fictional Rainbow Trout catch/effort data, ready for `cpue()`)
    - Live data via httr2: `fetch_kluane_data()` fetching from Government of Canada CKAN API (Kluane Lake Trout dataset); uses `resp_check_status()`, `simplifyVector = TRUE`; no pipe
    - Internal data: `gear_types` lookup table replacing `gear_factor` argument in `cpue.numeric()` and `cpue.data.frame()`; error message generated dynamically from table
    - Your turn: extend gear table, update broken tests, commit
    - Note on HTTP API testing (vcr, httptest2)
  - Added data-packages.qmd to _quarto.yml sidebar under Day 3
  - Updated `course-schedule.qmd` bullets for data packages session
