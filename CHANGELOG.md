# Changelog

All notable changes to FlexPrime are documented here, in reverse chronological order.

## 2.2.1 — Cloudflare Bypass, Login Hotfix & Attendance Sync (Sep 12, 2026)

### Added

- Live portal status badge on the login screen — know if the portal is reachable before you sign in.
- New “Show Profile Picture” setting under Appearance — turn it off to hide your photo on the dashboard card and profile screen.

### Improved

- Login error banner got a cleaner look — soft, no white flash, no stray close button.
- Dashboard summary cards now show the icon of the screen they open instead of a generic arrow, and the risk panel got a cleaner grid.
- A professor’s teaching tab now shows class timings and venues on each course card.
- Enrolled courses stay at the top of the browser, single-section courses got their Add button, and bookmarked subjects form a “Custom Subjects” group.
- Class notifications now include the course name, and the “Something Changed” sheet closes automatically when you jump into an item.
- Your class average now sits right beside your marks with a small up/down trend arrow.
- Marks and Attendance preview screens now show compact subject labels (e.g. “DS · CS301”) instead of full course names — no more header overflow.

### Fixed

- Login now handles Flex’s new Cloudflare verification automatically — just sign in as usual, no extra steps.
- 2026-batch logins with the “HSSC/SSC marks missing” notice now sail straight to your dashboard — no more false “incorrect credentials” error.
- Class detection is more reliable throughout the day, and attendance sync no longer falls back to stale cached records after a refresh.
- Timetable sync recognises when your data is already downloaded, and GPA/status readouts are saner where data is missing.
- Teaching courses now read both course data formats, so credit hours and sections appear reliably for every instructor.
- No more silently dropped courses — the timetable pipeline recovers every class even when entries are malformed.
- Credit hours come straight from the real course data, and meetings are grouped into one entry so teaching loads aren’t inflated by repeats.
- Course titles are cleaner — merged-course annotation text no longer leaks in, and credits/sections show correctly.
- Resource sync no longer fails with “Local version is current”, and fresh fixes reach your device even when the version number hasn’t changed.
- Course Browser no longer shows “No Courses Found” when your transcript hasn’t matched anything — it lists the full catalog to browse.
- New-semester detection resets Marks and Attendance baselines with one clean notice, and existing courses are no longer re-flagged as brand-new.
- Acronymizer now properly spaces dashes in subject names, and lab vs theory attendance cards are detected by name instead of fragile code letters.
- The update count and red dot clear from the sync button once pending items are downloaded, and no longer flash on at startup.
- The “What’s New” dialog now reliably shows once after every version update.

## 2.1.0 — Session Manager, Smarter Room Finder & Navigation Overhaul (Aug 30, 2026)

### Added

- New "Session & Sync" panel — see your login status, whether background tasks are ready, and keep-alive activity at a glance.
- "Kill Session" — signs you out and back to login while keeping your downloaded data, so you can start fresh anytime.
- App actions (updates, resource sync, changelog, share, feedback, report) moved from the drawer into the top bar — everything easier to reach.
- New Appearance menu in the top bar — toggle Light/Dark, Blurred Views, and Share App, plus a direct shortcut to Settings.
- "About Dev" moved into the Smart Tools section of the navigation.

### Improved

- The panel got a cleaner, friendlier look — a simple status card up top and tidy rows below, with copy that keeps the technical details out of sight.
- "Kill Session" only shows up while you're actually signed in — otherwise you get a friendly nudge to sign back in.
- The Appearance button got a cleaner sliders icon with a fun flip animation on tap.
- A single "Check Updates" entry now covers both app and data updates — the sync panel shows an "App Update Ready" row only when a newer version is available.
- Sync confirmations now tell you when downloads land ("Everything is now up to date").
- A red dot appears on the sync button when updates are waiting to be downloaded.
- Developer and Changelog screens now use the same top bar, so you can navigate without losing your place.
- Off-hours snark — outside 8:30 AM–8:30 PM you get a playful note instead of a wall of empty rooms.
- Room listings hide during off-hours, but the day/time picker stays so you can still plan ahead.
- Teaching course cards now show their schedule inline — day, time, and venue on each course.

## 2.0.0 — New Backend, Smart Sync & In-App Feedback (Jul 14, 2026)

### Added

- Upgraded to a brand-new backend (Supabase) — timetable, datesheet, papers, faculty, and teacher schedules all load faster and more reliably.
- Data is now version-tracked — the app only re-downloads something when it actually changes, saving bandwidth and time.
- Returning to the login screen with a valid session now resumes automatically — no need to solve CAPTCHA again.
- Your session is silently kept alive in the background, so you stay logged in longer without re-authentication.
- New sync panel in the side navigation — see which resources have pending updates and sync them individually or all at once.
- Send feedback directly from inside the app — choose from Feature Request, Bug Report, Feedback, Review, or General Contact, each with a tailored form.
- The app can now be opened directly from a browser — links on the website will take you straight into the right screen.
- Long-press the app icon for quick shortcuts to Dashboard, Timetable, Marks, and Attendance.
- Reviews is now Faculty Hub — moved to Core Features with a new icon.
- Website link added to the side navigation, top bar, and About App — opens theflexprime.vercel.app.
- Confidence scoring system (0-100) with four signals — name similarity, cross-source corroboration, department consistency, and token quality — replaces fragile single-match auto-resolve.
- Only verified/probable professors show NucesRate reviews and profile details; uncertain matches display timetable info only.
- Refresh button re-syncs NucesRate reviews and clears saved mappings to force fresh re-matching.
- Outdated app versions now see a clear "Update Required" screen with a direct link to download the latest version.
- Birthday card titles cleaned up — no more lone emojis cluttering the header line.
- Birthday card now shows age, adds "Add to Calendar" (Google Calendar) and "Share Wish" actions.
- Birthday reminder bell button opens Google Calendar pre-filled with event.

### Improved

- Everything loads through a single smart pipeline: remote first, local fallback if offline. No more blank screens.
- Fewer delays on startup — duplicate network requests are eliminated so the app feels snappier right after launch.
- The Refresh button now tries your existing session first — only asks for re-login if the session has actually expired.
- Version labels in the top bar are now always accurate and up to date.
- All "Suggest Improvement" and "Report Bug" buttons throughout the app now open this new form instead of your email app.
- Smoother keyboard transitions between roll number and password fields — no more bounce or delay.
- Android autofill now works on both fields so your password manager can suggest saved entries.
- Cleaner look — removed clutter and unnecessary icons from the login header.
- Roll number input now shows a full green or red border based on whether the number is valid, making it easier to spot typos.
- Faculty renamed to Faculty Directory for clarity.
- App logo is now used consistently across the side nav, footer, and top bar menus.
- Disambiguation candidates are now sorted by department match and fuse score with visual hint chips.
- The "Something Changed" notification sheet now shows the actual detected changes inline — compact cards with the affected subjects, entries, and attendance stats — so you can read what changed without jumping into Insights.
- FlexPrime Insight no longer repeats the same low/high marks alert for the same subject — once an assessment phase is surfaced, it stays quiet until a new mid/final is actually graded, and tiny quizzes/assignments never nag you.
- Developer Mode now switches on automatically for the developer's own account and stays off for everyone else.
- Info cards now support a quick sub-line under the title, with reserved space and a slightly larger icon — cleaner hierarchy across TimeTable, RoomFinder, References, Recommendations, Guest Mode, and Birthday screens.
- Login roll number field now shows a dashed success border once it meets the format requirements.
- Course cards now show full title in expanded view when shortTitle was abbreviated.
- Empty state "Timetable Not Found" note is now clickable with markdown support — tap to open manual wizard.
- Top version badge only shows when timetable data exists — no more "v?" when data cleared.
- Manual entry mode banner now supports markdown.
- Upcoming birthday tiers: 0 days (celebration card), 1-3 days (warning), 4-7 days (info), 8-10 days (tip) with contextual icons.
- SGPA card now shows incomplete state ("X/Y graded — select remaining") instead of misleading "0.00".
- Better state awareness — users can still pick grades but see what's missing.

### Fixed

- Remember Me now actually remembers your preference instead of always being on.
- Credentials are only saved when you tap Sign In — not on every keystroke.
- Faculty Hub professor tabs now scroll independently — content no longer gets cut off.
- Datesheet setup status now persists correctly after navigating away and back.
- Paper links with special characters (#) now open correctly instead of breaking.
- Dashboard no longer shows multiple update sheets stacking on top of each other.
- Profile image no longer overflows its circle on the dashboard card.
- Quick actions (long-press shortcuts) no longer crash on first launch.
- Notification tips now respect their cooldown — no more seeing the same hint on every refresh.
- Milestone celebrations (every 10 syncs) are cleaner and less intrusive.
- Mid-semester exams no longer cancel all class notifications — only class alerts on exam days (day before through last exam) are suspended. Semester-end exams are unaffected.
- Fixed a crash when opening subject details by correctly exporting missing achievement grade utilities.
- Fixed marks summary category rows incorrectly displaying raw marks instead of weightage scores.
- Fixed timetable class cards incorrectly showing the "NOW" badge due to 24-hour time range parsing issues.
- Added data integrity validation in fetchData — student info, marks, attendance, transcript, and study plan now only overwrite cache when the returned data has valid content, preventing null/empty data from replacing good cached data during auto-refresh.
- Card titles no longer clip their descenders (extra line height) and the title sub-line reads a touch bolder.
- Screen headers without a help guide now align vertically with those that have one — title no longer drops out of line.
- Portal (Marks/Attendance) no longer shows its duplicate header strip inside the app webview — more room for your data.
- Update checks now verify actual parsed data exists (hasData) — no more false "up to date" when timetable/datesheet missing.
- Version metadata cache (rm_timetable_meta, rm_datesheet_meta) now updated after Excel parsing completes.
- Side nav update badge now correctly reflects pending updates by reading fresh cache and checking hasData.
- Timetable no longer stays stuck in the sync panel as "pending" after updating to the latest version.
- Old builds now correctly show "Update Required" screen instead of falling to "In Development" fallback.
- Dev builds bypass update block — development mode no longer triggers Caution screen.
- Truncated server shortTitle (e.g. "Appled Probability in Computi") now detected and regenerated via acronymizer.
- Expected SGPA card no longer stuck on "Loading" when no current marks — returns proper state objects.

## 1.9.9 — Help Guides — Finally! (Jun 26, 2026)

### Added

- Almost every screen now comes with its own help guide. Tap the info icon at the top and you'll see what each card, grid, and button on that screen actually does — no more guessing.
- Dashboard, Calculator, Academic Journey, Marks, and most main screens now have visual walkthroughs ready for you.
- Open Help Guides for the first time and you'll get a quick intro sheet explaining what guides are and how they work.
- New "Recent Changes" section on the Dashboard — shows the top 3 groups of insights (marks updates, attendance changes, system detections) detected during sync, each tappable to navigate directly to the relevant screen.
- Pre-scheduled reengagement notifications with a concrete DATE trigger — fires at end of day if user hasn't synced recently, even if the app is in background.
- Settings entry added to the side nav for quick access.

### Improved

- The Help Guides entry moved up to the Core Features section in the side nav — always visible, always in reach.
- New info icon replaces the old compass, so it no longer clashes with RoomFinder.
- The catalog screen got a redesign — cleaner rows with color accents that make each guide easy to scan.
- Loading state uses isSyncing directly so the section waits for diffs to settle after a sync before displaying.
- Soft refresh now uses a single unified "Refresh" toast with inline progress updates instead of separate toasts per stage — less flicker, clearer messaging.
- Cookie flush and session finalization on login are deferred via InteractionManager for smoother transition animations.

### Fixed

- Note Editor and Profile were pulling up the Dashboard guide when you tapped help — they now open their own guides like they should.
- Repeat/improvement detection on Marks cards now reads transcript history directly instead of relying on helper functions that incorrectly returned current-semester data for previous semesters.
- Soft sync reports which data types actually changed (marks/attendance) instead of just whether the fetch succeeded.
- Background reengagement task now correctly parses timestamp as a number instead of a string.
- Background sync tasks now return Success instead of NoData/NewData for more reliable OS scheduling on iOS.
- Removed BackgroundTaskStatus.Denied check that could block background sync on some devices.
- Fall batch semester ID now uses endYear + "2" instead of "3", fixing potential schedule/notification issues for Fall enrollees.
- Removed stray console.warn(item) in FileCard that was logging every file object on press.
- Fixed shimmer colors in PapersFiles and PapersFolders to use proper surface tones with explicit borderColor, improving skeleton visibility on both light and dark themes.

## 1.9.8 — UI Tweaks & Smarter Cards (Jun 25, 2026)

### Improved

- Repeat courses now show clearer icons — different visuals for failed vs improvement attempts.
- Course cards automatically shorten long titles for a cleaner timetable view.
- Progress messages in GPA calculator now compare against your own history instead of generic thresholds.
- SGPA messages now include direction + magnitude tiers (massive/significant/notable/modest/tiny) with tone-adjusted copy per combination.
- CGPA messages now include net change amount and consistency qualifier for stable trends.

### Fixed

- Fixed notification stats not updating in real time after background changes.
- Summer semester detection for isSemesterEnded — bypasses stale calendar end date when enrolled in Summer.
- Datesheet selectedExams now re-validate when transcript or academic calendar loads after initial download, preventing stale matches.
- Pre-semester exams no longer sneak into selectedExams — cutoff check deferred when calendar is unavailable.
- isSemesterEnded now filters out pre-semester exams before checking if all exams have passed.
- ToggleExamSelection no longer sets hasData to false when last exam is deselected, preventing unnecessary re-downloads on restart.
- Replaced fragile recursive acronym matcher with acronymizer-based comparison for reliable subject cluster merging.
- Fixed case-sensitive comparison causing acronyms like "DLD" and "Dld" to stay in separate clusters.
- Loading shimmer skeleton count now matches actual layout — 2 left (menu + theme), 2 right (sync + profile).
- Expected SGPA card no longer gets stuck on "Loading courses" when current semester data is missing from the study plan — now calculates directly from marks and transcript.
- Empty (unfilled) stars in professor pills, professor header, and review cards now use tertiary text color instead of border color — visible on both light and dark themes.

## 1.9.7 — Summer Safeguards, Marks Accuracy & UI Polish (Jun 24, 2026)

### Improved

- Data-Aware Datesheet Guard: Smart early semester check now only blocks if you have no exam data loaded yet, ensuring valid summer datesheets display immediately.
- Not Yet Assessed Grouping: Ungraded courses are now cleanly grouped under "Not Yet Assessed" instead of "In Progress".
- Marking Progress Descriptions: Overhauled progress cards to show clear status lines like "No assessments graded yet" or "X of Y graded".
- Semester History Icon: The semester switcher is now a git branch icon button — clean and minimal, no more wide text trigger in the header.
- Newest First: Semesters in the history dropdown now show newest first so you're never scrolling to the bottom to find your current term.
- Dividers in Semester List: Thin separators between semester options make the list easier to scan.
- Clean Storage Resets: Added notification store and read-state keys to the academic data group to ensure everything resets cleanly when clearing academic data.
- Drawer Update Hub: Added quick access in the side navigation to check for updates, view pending downloads, and open the latest changelog from one place.
- Simplified Top Navigation: Moved the update and changelog entry points out of the top bar and kept the header focused on a cleaner theme-toggle experience.
- Animated Sign In Button: The Sign In button now morphs its corners with a smooth spring animation when pressed or loading — no more jarring instant shape change.
- Animated Guest Button: The Continue as Guest button gets the same spring border-radius animation on press.
- Faster Post-Login Flow: The success overlay → fade → navigate sequence is now significantly snappier, getting you to your Dashboard much quicker after login.
- Tappable Course Rows: The entire course row is now pressable with a full ripple for quick selection.
- Newest Semester First: The semester chip strip now displays your most recent semester at the left.
- Premium GPA Cards: Replaced basic scorecards with the animated premium Card and Note components for a sleek look.
- Smarter Menu Options: Rephrased actions and restricted reset controls to only show when edits exist.

### Fixed

- Stale Exam Filtering: Automatically strip outdated exam dates from previous semesters upon loading, file uploading, or syncing your datesheet.
- Universal Summer Detection: Bypasses the early semester guard for Summer semesters even when the API omits the semester field, avoiding blank "Too Early" screens.
- Category Total Mismatch: Category totals now correctly use the sum of individual item weightages (e.g. 9.99 = 3×3.33) instead of the portal's rounded value (e.g. 9) — scored and max are finally on the same basis.
- No More Impossible Scores: Fixed cases like "9.02/9" where the scored value exceeded the max due to floating point accumulation from the portal's rounded denominator.
- Float Cleanup: All computed marks values — scored, percentages, averages, min/max — are now rounded to 2 decimal places at the source, no more 16-digit floats in the data.
- Grade Precision: Subject percentage is now floored before grade lookup, so 65.46% correctly stays a C instead of jumping to C+.
- Ungraded Subject Support: Fixed subjects with ungraded categories incorrectly showing 0/24 marks and an F grade. They now display cleanly as "Not assessed" with a pending grade.
- Semester Average Calculation: Excluded ungraded subjects from your semester averages so they do not artificially lower your academic standing or distort "Above Average" statistics.
- Instant Notification Updates: Fixed a bug where background notifications (like semester baseline resets and marks syncs) would not display until a hard app restart. The screen now instantly reloads whenever you open it.
- Sign-Out Race Condition: Fixed the "Timetable Not Found" sheet incorrectly popping up during sign-out. It now verifies you are still authenticated and on the Dashboard before showing — no more surprise prompts mid-logout.
- Smooth Login Transition: The Login screen now fades out cleanly before navigating to Dashboard — no more jerky slide or Dashboard flashing under a still-visible sheet.
- Attendance Empty State: Corrected typos and polished wording for a cleaner look.

## 1.9.6 — Performance Boosts & UI Polish (Jun 22, 2026)

### Improved

- Silky Smooth Scrolling: Moving through your Attendance and Marks is now noticeably faster and more fluid.
- Lighter Rendering: Shifted heavy data calculations off the screen to prevent stuttering.
- Instant Datesheets: Your exam schedule now pops up instantly without any freezing.
- Smarter Loading: Redesigned how exam dates are fetched to make loading lightning fast.
- Consistent Colors: Refined WebView sheets to perfectly match your chosen theme.
- Seamless Login: Fixed visual color inconsistencies on the login screen for a cleaner look.

## 1.9.5 — GPA Calculator Overhaul & Critical Fixes (Jun 19, 2026)

### Added

- Grade Unselection: Added a "Clear Grade" button and toggle-to-deselect to easily reset selected grades.
- Fine-Grained Planner: Added a custom CGPA target text input next to the milestones for precise target forecasting.

### Improved

- Non-Credit Support: Excluded non-credit courses from GPA credit math and forecast calculations, and visualised them with an NC badge.
- Refreshed UI: Upgraded top tabs into a single unified capsule control, wrapped semester selection in a horizontal scroll, added live progress bars to GPA scorecards, and styled courses as nested cards.
- Transcript-Based Courses: Combined active timetable courses with transcript courses for the current semester, ensuring the GPA calculator never misses any subjects.
- Silent Update Dismissal: Dashboard update prompts now intelligently auto-dismiss themselves when a new timetable or datesheet successfully finishes downloading in the background.
- Stat Card Widths: Adjusted the width proportions of the CGPA, Expected SGPA, and Degree Progress cards for a more balanced and visually consistent layout.

### Fixed

- Persistent Login Loop: Fixed a critical bug where student data was never actually written to local storage after login — the save function assembled the data object but never called the AsyncStorage write. This caused the app to redirect to Login on every cold launch, even after a successful sign-in.
- GPA Grade Normalization: Grades from the transcript are now trimmed and uppercased before lookup, so values like "A " or "b+" no longer get silently dropped from GPA calculations.
- Repeated Course Deduplication: CGPA now tracks already-counted course codes across semesters — retaken courses only count the latest attempt instead of inflating totals by double-counting.
- Non-Credit Detection: Expanded the non-credit course filter to catch all common variants — "non credit", "non-credit", and "nc" — so they are consistently excluded from GPA math across all tabs.
- Improved rechecking semester guard with stricter date validation and more reliable range handling.
- Missing Registered Courses: Courses recovered by the transcript backfill (repeats, cross-discipline) were being silently dropped by the semester filter before reaching the GPA calculator — fixed.
- Cross-Discipline Courses: Added a second-pass backfill after all sheets are loaded so courses from another discipline's timetable sheet are no longer invisible to the parser.
- Repeat Course Matching: Priority 1 section matching now cleanly falls through to Priority 2 when a repeat course is offered under a different section label in the current timetable.

## 1.9.4 — Summer Semester Support & Smoother Login (Jun 16, 2026)

### Added

- Summer support is here! The app now correctly detects when you're in a Summer semester — no more showing wrong semester data.

### Improved

- Not registered for Summer? No worries — the app automatically falls back to your Spring data so you're never left with an empty screen.
- Tapping a nav item now nudges the label slightly instead of tilting the icon — feels cleaner and less distracting.
- Nav item text is a touch bolder now — easier to read at a glance.
- Sidebar Icons: Updated the side nav icons to a more modern and polished feel, refactoring the icon resolver to resolve components directly.
- Slight spacing and sizing adjustments to the top bar for a tighter, more balanced look.
- Timeline Styling: Softened timeline borders and backgrounds on the Profile screen to match the design system.

### Fixed

- Login shimmer now stays on screen long enough — it used to disappear a split second too early while the page was still loading.
- Close button on the sidebar now shows a proper ripple effect when tapped.
- The loading skeleton on the References page had misaligned table columns — they now stretch evenly across the full width.
- Clipping PopupMenu Ripples: Added a custom ClippedRipple component wrapping TouchableRipple in an overflow:hidden View to ensure ripples are clipped to the trigger shape on all Android menus.

## 1.9.3 (Beta) — Polished Semester End Guards, Notifications & Animated Buttons (Jun 15, 2026)

### Added

- Animated Action Buttons: Added smooth spring-based border radius morphing to EmptyState action buttons on press.

### Improved

- Robust Date Parsing: Enhanced academic calendar date extraction to support custom formats and fallbacks like endOfSemesterSemesterBreakStart.
- Flexible EmptyState Icons: Added support for different icon families (Feather and MaterialCommunityIcons) in EmptyState components.
- Concluded Semesters: Timetable screen now cleanly hides editing controls and shows a friendly celebration state when the semester has wrapped up.
- Missing Data Hooks: Refactored useMissingData hooks to streamline semester-ended guards and robustly check date ranges.

### Fixed

- Notification Scheduling Fallback: Integrated exam-based fallback checks inside DataContext class notification scheduler to correctly skip/cancel class alerts during semester transitions.
- Force Reschedule Guards: Prevented class notification rescheduling via Settings if the semester has ended, adding clear UI indicators and toast descriptions.

## 1.9.2 (Beta) — Manual Timetable Entry — Build Your Schedule When the Server Can't (Jun 14, 2026)

### Added

- Manual Timetable: Server timetable not out yet? No problem — use the new wizard to enter your schedule yourself in just a few taps.
- Courses Pre-filled: Your enrolled courses are pulled straight from your transcript so you don't have to type them in — just fill in the days, times, and rooms.
- Smart Day Pairing: Picking Monday? Wednesday gets added automatically (and vice versa) for 3-credit courses, just like how your real schedule works.
- Labs & Summer handled: The app figures out whether your course is a lab or a summer course and shows you the right time slots automatically.
- Different rooms on different days? You can set a separate time or room for each day if your classes don't share the same slot.
- Preview before saving: See a clean summary of your full week before you hit save — catch any mistakes before they matter.
- Helpful prompt: If your courses couldn't be loaded from the server, the dashboard now pops up a clear message and takes you straight to the manual entry screen.
- Manual mode label: A small banner at the top of your timetable lets you know you're viewing a manually entered schedule.
- Try syncing from server: A new option in Settings lets you re-fetch your timetable from the server. If nothing comes back, your manually entered schedule stays safe.

### Improved

- See your progress: A progress bar shows how many courses are fully set up vs. still missing details.
- Less clutter: Instructor name, short title, and credit hours are hidden by default — tap to expand only if you need them.
- Forgot a course? If you try to save with missing details, you'll get a prompt to either go back and fix it or save only the complete ones.
- No repeat nagging: Once you've entered your schedule, the prompt won't show up again.
- Quick setup shortcut: If your timetable is empty, there's now a direct link to jump into the manual entry wizard right from the timetable screen.
- Smarter "Missing Data" alerts — the app won't prematurely warn you about missing data if the new semester is still days away.
- Empty state guards: Datesheet and Rechecking screens now gracefully hide during inter-semester breaks or early semester days instead of showing missing data errors.

### Fixed

- Fixed an issue where your SGPA might show as 0.00 when using a manually entered timetable.
- Fixed a crash on the Marks screen that prevented some students from viewing their grades.
- Resolved a bug where the timetable loading spinner would get stuck indefinitely if no courses were found.
- Semester Transition Guard: Automatically detects when your current semester has ended by verifying if all registered exams have passed, effectively hiding old courses during new semester overlaps.
- Phantom Notifications: Background class alerts will now properly sleep during semester overlaps, so you don't get woken up for an old class before your new registration completes.

## 1.9.1 — Smarter Class Notifications, Semester Checks & Calculator Polish (Jun 12, 2026)

### Added

- Centralized Semester Check: Introduced a reusable semester check helper that fetches active dates directly from the academic calendar.
- Refreshed Calculators: A brand new calculators screen is now available with polished layouts, better metrics, and improved accuracy.

### Improved

- Improved Startup Heal: Hardened startup checks in App.js to cleanly auto-suspend class alerts and show explicit guidance toasts on startup.
- Robust Sanity Checks: Aligned notification sanity checking to prevent rescheduling classes when the semester is inactive.
- SGPA Forecasting: Expected SGPA calculations now fallback to transcript grades first (matching the core grade calculations) for greater correctness.
- Improved Calculations: Enhanced GPA/CGPA forecasting math and accuracy metrics.

### Fixed

- Auto-Suspension of Alerts: Class notifications are now automatically cancelled and skipped if the semester is yet to start or has ended.
- Dashboard Metadata Notes: Fixed notes visibility when the semester is yet to start and days-left values format as countdowns (e.g. 15d).
- Marks Graded Sorting: Aligned Marks page to place courses with active transcript grades in the Graded section and show their correct finalized grade status.

### Notes

- Known Issues: Some calculator edge cases are still expected and will be fully resolved in upcoming patches.
- Summer Timetable Integration: Integration has been postponed and will be addressed later in an upcoming patch.

## 1.9.0 — Guest Mode, Marks Grouping & Rechecking Fixes (Jun 10, 2026)

### Added

- Guest Mode is back — explore timetables, datesheets, past papers, room finder, and more without signing in.
- Added a collapsible Absolute Grading Scheme section to Marks details screen for quick grade references.
- Subjects are now grouped into three sections — Graded, In Progress, and Not Yet Assessed — so you can instantly see which courses are finalized vs still being marked.
- Timetable screen is now read-only once the semester ends — edit mode and "Add Course" are locked to prevent accidental changes to a concluded schedule.

### Improved

- Onboarding now shows a clean 4-field section picker for guest setup — no unnecessary name field, just what's needed.
- Each dropdown in the guest form now highlights with a primary border once filled, giving clear step-by-step progress.
- Consent slide now leads with login as the primary action, with "Explore as Guest" as a subtle ghost option below.
- Switching to guest now performs a full cache clear — data, reviews, papers, theme, preferences, and profile picture — matching the user-switch cleanup.
- Refreshed all marks category icons — quiz, assignment, sessional, project, final exam, and more now use cleaner outline variants.
- Guest info card and icon container now use consistent corner radii matching the app's design language.
- Dashboard guest banner now uses an arrow-right icon instead of chevron for clearer directional intent.
- Smart Chunking: Automatically displays only 3 relevant rows (matched row and one up/down) based on current score, with option to expand to full table.
- Premium Interactions: Overhauled the header with TouchableRipple touch feedback, dynamic grade previews, and polished layout borders.
- Updated class-participation marks icon to a better-suited variant.
- A contextual "Semester has ended" info banner replaces conflict and clearance warnings once classes are over.
- Screen subtitle updates to "view-only mode" and the edit/add buttons are visually dimmed when the semester has ended.
- Marks Preview grading scheme table now opens expanded by default instead of requiring an extra tap.

### Fixed

- Fixed guest initialization leaving the app stuck on a loading screen by correctly resetting loading state after demo user setup.
- Dashboard rechecking card no longer shows an arbitrary course when multiple exams share the same rechecking date — it now surfaces the earliest time slot.
- Dashboard "All Caught Up" sheet no longer shows Transcript and Study Plan sync status for guest users — those fields are irrelevant in guest mode.

## 1.8.9 — Animated Interactions, Smarter Cards & UI Polish (Jun 6, 2026)

### Added

- Added a "Built by a FASTian" slide before consent — highlights community contribution and previews the side menu feedback shortcuts.

### Improved

- Info cards now animate their corners on tap — they gently round out when you press and spring back when you let go.
- The rounding effect is sized to feel right depending on the card type — subtle on small ones, more noticeable on wider cards.
- Intro screen buttons now animate their border radius on press using a spring instead of snapping instantly.
- Modernized the Notifications screen with TouchableRipple elements for polished touch feedback.
- Consent disclaimer reworded to be friendlier and less legalistic.
- Section headers now show a red dot on the top-right corner when any item inside has a missing data indicator, but only while the section is collapsed.
- Hardened version checking to compare local and remote timetable/datesheet versions in update prompts.
- Polished Soft, Full, and Partial Sync bottom sheets to dynamically show device database versions.
- Smart Sync: Automatically skips attendance sync once academic calendar indicates the semester has wrapped up.
- Added markdown strikethrough support in bottom sheets.
- Softened default light-theme primary text color for improved readability.
- Aligned top-right login screen action buttons horizontally for a cleaner look.
- Added direct navigation back to onboarding slides from the login screen.
- Adjusted dark-theme surface colors and light-theme border colors for consistent contrast.
- SideNav footer shortcut buttons (suggest, report, share, GitHub) now use the unified Note component with dashed borders and icon-only mode for a polished, consistent look.

### Fixed

- Grading summary notes (finalized subjects, top grade) now correctly show up only after the semester has fully wrapped up.
- Grading stats cards now stay hidden when the current semester has no results yet, instead of showing last semester's grades.
- Grading summary notes now show a shimmer loader while stats are being calculated instead of disappearing entirely.
- PFP Cache Collision: Profile pictures are now cached per roll number — switching accounts no longer shows the previous user's photo.

## 1.8.8 — New Activity Bottom Sheets & Visual Polish (Jun 3, 2026)

### Added

- Tap any marked assessment to open a detailed summary card showing class statistics, ranges, and averages.
- Standardized category and subject summaries to use the same high-fidelity details sheet.
- Integrated the rechecking schedule with the unified Export/Share screen for PDF, PNG, Excel, or JSON export.
- Tap Share on a rechecking card to capture and share the exact card UI as a branded PNG.

### Improved

- Cleaned up PNG activity card sharing by removing the modal background.
- Added dynamic color badges (above, equal, below) to class average scores.
- Standardized spacing, weightage badges, and layout inside the details sheet.
- Enlarged the text area for a cleaner schedule import paste experience.
- Matched the shared PNG card design with the list card, adding borders and a branding footer.
- Polished bottom sheet drag handles and updated changelog headers.
- Modernized navigation icons for Changelog, About App, and Dashboard.
- Polished update sheet layouts with friendly, readable statuses.
- Smoothed out WebView loading transitions to prevent page flashes.
- Floating action buttons now fade out elegantly when sheets or side menus are open.

### Fixed

- Corrected category math logic to leverage pre-calculated weighted totals.
- Restored and corrected overall course statistics in summary bottom sheets.
- Improved deadline verification using date and time range comparisons.
- Replaced FlatList with simple maps to fix tab transition blank screens.

## 1.8.7 — Portal WebView, One-Tap Login & Navigation Polish (Jun 2, 2026)

### Added

- Portal button: Tap the globe icon in the Marks or Attendance header to open the university portal right inside the app.

### Improved

- Auto-login: Once you solve the captcha, the login form submits itself automatically — no need to tap the button.
- Smart paste button: The paste button on input fields now only shows up when the field is focused and empty, keeping the layout clean.
- Notification Cache: Added rechecking cache keys (`notif_cache_rechecking`) to notification rescheduling for a cleaner offline sync.
- Cleaner sidebar: The main section is now labelled "Core Features" and stays open by default every time you open the drawer.

## 1.8.6 — New: Proactive Switch User Warning, PFP Cache Clearing & Rechecking Polish (May 30, 2026)

### Added

- Switch User: Intercepts logins with different roll numbers proactively, showing an elegant bottom sheet warning to prevent accidental local data wipes.

### Improved

- Automatic Pre-Sync Wipe: Clears previous user records, reviews, papers, and themes instantly *before* launching the portal WebView login if proceeding.
- Centralized Matching: Rechecking schedule matching is now calculated instantly and globally inside DataContext on save or clear, removing screen-level delays.
- Dialog Migration: Converted clear-all and single-item delete alerts inside the Rechecking screen to high-fidelity, premium bottom sheets.

### Fixed

- PFP Cache Leak: Wipes custom profile pictures (customProfileImage) and developer overrides alongside the disk image cache on user switches.
- Instant Notifications: Cancels rechecking alerts and clears background caches immediately when schedules are wiped, without waiting for the next bg sync.
- Navigation Fix: Added RecheckingSchedule to the Dashboard allowed-guest navigation routes to prevent transition blocks.

## 1.8.5 — New: Subject Hub Screen, Expected Grades & Spacing Polish (May 28, 2026)

### Added

- Subject Hub: New unified overview screen for any course — schedule, attendance, marks, exams, rechecking & downloads.
- Long-press any subject card in Dashboard, Marks, Attendance, or Datesheet to open the Hub.
- Shimmer skeletons replace blank screens while rechecking list loads.
- Dashboard warning banner listing missing documents (Timetable, Datesheet, Rechecking, Academics) with tap-to-fix routes.
- Red dot badges on SideNav rows and TopNav header button for incomplete profile fields.
- New Settings toggles for Advanced Features and Smart Features (on by default).

### Improved

- Marks Summary: Assessment categories with no grades yet are automatically hidden from the card.
- View All: Replaced plain text arrows with Feather chevron-right icon rows.
- Day.js: Migrated date parsing to Day.js to fix silent Hermes crashes in concluded pills.
- Attendance dot strip spacing and flame-accented streak banner polish.
- Check Mail: Direct email client shortcut to fetch rechecking details.
- Smart Tools Section: New dedicated "Smart Tools" nav group for Insights, Calculators, Export, RoomFinder, Rechecking, Faculty, Reviews, References & Settings.
- Extra Utilities: Renamed "Partially Completed" to "Extra Utilities", gated behind showAdvancedPages.
- Faculty Bio: Removed "Read more" label to eliminate the false impression the text is tappable.
- References: Replaced outer ScrollView with a fragment; horizontal tables use nestedScrollEnabled & directionalLockEnabled.

### Fixed

- Stats cards auto-hide when rechecking schedule data is empty.

## 1.8.4 — Toast Morphing Engine, Dashboard Shortcuts & Media Sharing Polish (May 26, 2026)

### Added

- Festive Greeting: Added a beautiful Eid ul Adha bottom sheet with custom barbecue-themed humor and warm wishes.
- Toast Morphing: Introduced ToastMorphing.js and overhauled Toast.js UI to support fluid, real-time status transitions (e.g., LOADING to SUCCESS/ERROR) on a single card.
- Feature Promotion: Elevated the Rechecking screen as a primary live feature across introductory screens.

### Improved

- Selective Notes: Introduced smart announcement filtering with validity ranges to show time-sensitive info cleanly.
- Data Sync Overhaul: Re-engineered background sync pipelines in DataContext.js to utilize a single, morphing Main loader, replacing separate overlapping toasts.
- Smart Filter: Integrated notification helpers to silence generic "Profile ready" spam and automatically configure durations based on warning levels.
- Quick Actions Overhaul: Re-engineered the dashboard actions grid with direct access to Room Finder, Insights (notices), and Export & Share.
- Dynamic Semester Status: Upgraded semester tracking to show positive completed states and dynamic results expectations.
- Rechecking Progress: Hardened rechecking deadline cards with custom warning statuses and colors based on urgency.
- Clean Settings: Pruned inactive settings preferences and disabled legacy elements for an uncluttered experience.
- Fluid Animations: Integrated spring physics, custom touch delays, and updated radius curves to File Card action buttons.
- Direct API Downloads: Automated seamless download redirects for API-only papers, removing redundant loading loops.
- Polished Share templates: Decoded resource sharing URLs and standardized a clean, minimal FlexPrime message signature.

## 1.8.3 — New: Rechecking Schedule Screen & Import Parser (May 22, 2026)

### Added

- Added a brand-new Rechecking Schedule screen with AcademicCard-style layout, header actions and info chips.
- Introduced an Edit mode toggle in the screen header to enable bulk Edit/Remove workflows.
- Added a redesigned global crash screen with recovery and reporting actions.
- Built a new rechecking parser that extracts rows from PDF/text imports including section and course parsing.

### Improved

- Improved date displays: aligned rechecking and exam dates and applied muted styling for exam dates.
- Global toast safety: ensured the toast wrapper always supplies title and message to avoid empty notifications.
- Improved crash logging, trace handling and clipboard export support.
- Refined spacing, typography and action button consistency across newer screens.
- Adjusted spacing and paddings in list cards and header actions for improved alignment.
- Refined theme color usage and minor UI alignment issues across related screens.

### Fixed

- Fixed empty toast edge cases and several minor alignment issues.

## 1.8.2 — Notification Accuracy & Interface Polish (May 20, 2026)

### Improved

- Sanity Checks: Added background validation to detect and correct AM/PM time shifts before scheduling alerts.
- List Scanning: Added inline badges and auto-bolded title prefixes to the What's New changelog.
- Nested Accordions: Flattened older release rows into single-layer expandable cards, removing nested boxes.
- Optimal Padding: Added comfortable left-padding indentation and adjusted spacing to prevent walls of text.

### Fixed

- Exam Scheduling: Fixed afternoon/PM exam alerts getting scheduled for AM hours due to parsing quirks.

## 1.8.1 — Interface Polish & Onboarding Experience (May 19, 2026)

### Improved

- Login UI Polish: Redesigned the authentication screen with a premium modern glassmorphic theme and smooth transitions.
- Input Fields: Standardized username/password inputs with vector icons, active glow borders, and clear buttons.
- Easter Egg: Added a context-aware student assistant engine with witty comments about stats, attendance, and grades.
- Animated Transitions: Added smooth fade-and-slide text animations to dashboard card value and description shifts.
- Exam Layout: Updated dashboard exam cards to display the course code instead of redundant TBA venues.
- Milestone Sheet: Upgraded sync milestone popups into interactive, high-fidelity mobile bottom sheets.
- Bottom Sheet Onboarding: Migrated all six core guides into premium, thumb-navigable swipeable bottom sheets.
- Note Spacing Polish: Redesigned Markdown Notebook and sync help guides with optimal margins and list alignments.

### Fixed

- Badge Alignment: Fixed a vertical alignment offset on the EXAM badge to center it next to the title.

## 1.8.0 — Smart Subject Recommendations & Core Stability (May 19, 2026)

### Added

- Smart Recommendations: Added subject suggestions for enrolled courses that lack exact timetable matches.
- Resilient Cache Fallback: Instantly redirects to offline cache under heavy portal load or network timeouts.
- Smart Response Guard: Parses HTML server responses for runtime and login errors to instantly trigger offline fallbacks.

### Improved

- Smarter Parsing: Datesheet parser now extracts instructor and section data from matched courses for exams.
- Fuzzy Matching: Built a Fuse.js matching layer to find partial subject titles while filtering false matches.
- Confidence Scores: Recommendations display confidence percentage with transparent, advisory matching text.
- Global Toast Clean-up: Resolves all pending loading spinners on fallback, showing a single haptic feedback warning toast.

### Fixed

- Time Logic Fix: Fixed afternoon/PM exams getting marked finished in the morning due to 24-hour time parsing quirks.
- Countdown Accuracy: Today's exams stay visible on the dashboard until end of day instead of disappearing early.
- Grid Card Value: Fixed empty top grid card value display when all exams are finished.
- Notification Scheduling: Resolved afternoon/PM exam notifications scheduling for midnight due to 24-hour parse errors.
- Developer Mode Trigger: Fixed async race condition in rapid developer options taps using high-perf synchronous refs.
- Dashboard Crash: Resolved a React rendering crash in dashboard quick action logic.

## 1.7.9 — Qualitative Performance & Absence Tracking (May 15, 2026)

### Added

- Interactive GPA Analytics: Introduced dynamic SVG growth timelines with touch scrubbing for semester insights.
- Focus Mode: Tappable legend pills isolate SGPA or CGPA trends with smooth area-gradient transitions.
- Academic Milestones: Integrated high-visibility threshold indicators for Dean's List (3.50) and Rector's List (4.00).
- Live Forecasts: Integrated predictive engine that forecasts future CGPA based on assessment trends.

### Improved

- Ghost Mode Privacy: Intelligently masks sensitive GPA values while preserving interactive trend visualizers.
- Unified UI Logic: Replaced redundant header icons with a sleek Reveal/Navigate morphing toggle.
- Qualitative Standings: Simplified dashboard showing descriptive semester grades instead of dry raw percentages.
- Visual Cues: Added class standing trending arrows and quota-remaining badges for attendance tracking.
- Refined Makeup Week: Upgraded progress indicators and semantic colors for the final semester phase.
- Skeleton Polish: Rescaled loading placeholders on the Dashboard to provide a snappier, instant load feel.
- Clean Architecture: Pruned unused dependencies and optimized component memory allocation.

### Fixed

- Stuck Animations: Implemented auto-resets for PopupMenu tilt animations to prevent icons getting stuck.
- Logic Hardening: Standardized theme-aware style injection in chart elements to resolve dynamic rendering crashes.
- Layout Consistency: Removed redundant borders and optimized margins in academic card footers.

## 1.7.8 — Hardened Sync, Vertical Dialogs & Notification Polish (May 12, 2026)

### Added

- Professional Notices: Added campus-aware notice sheets to set expectations for alumni and external students.
- Title Shimmers: Linked Schedule and Favorites header shimmers to load in lockstep with content lists.
- Vertical Dialogs: Added support for vertically stacked dialog action triggers to fit compact phone screens.
- Action Icons: Integrated Feather icon rendering inside dialog action buttons for clear visual hierarchy.

### Improved

- Hardened Sync: Rewrote the background sync engine for enhanced reliability and faster data recoveries.
- Log Cleanup: Silenced duplicate synchronization console entries to keep bg operations clean.
- Sync Persistence: Ensured last sync timestamps update correctly to trigger re-engagement reminders.
- Smart Inactivity: Calibrated inactivity thresholds to trigger stale data warnings accurately after 24 hours.
- Storage Resilience: Hardened the clear-data engine to wipe caches and snapshots during explicit resets.
- Snappy Logout: Re-engineered sign-out to navigate instantly, removing blank-screen flashes.
- Enhanced Login: Redesigned login inputs with native Paste, automatic styling, and status indicators.
- Remember Me Fix: Refined credentials retention to secure storage immediately upon toggle shifts.
- Milestone Sheets: Upgraded the 10-sync milestone dialog with mobile bottom-sheet styling.
- Autofill Polish: Softened visual error feedback highlights and resolved Android dark-mode input coloring.
- Interactive Prompts: Made notifications-setup dialogs trigger on active user taps to prevent sudden popups.
- Readability Polish: Standardized descriptive status tags and list keys within the notification log panel.
- Muted Status: Softened academic context indicators to direct focus onto actionable updates.

### Fixed

- Sync Race Fix: Fixed a race condition where the Datesheet parser failed in bg by verifying profile propagation.

## 1.7.7 — Unified Dashboard Cards & Schedule Polish (May 10, 2026)

### Added

- Contextual Summaries: Added helpful descriptive subtitles for all empty schedule states.

### Improved

- Unified Design: Replaced standalone Exam Countdowns with unified, clean dashboard QuickActionCards.
- Card Definition: Increased borders on QuickActionCards to improve contrast against standard backdrops.
- Dynamic Colors: Allowed theme-aware color mapping on grid components to handle status states.
- Dashboard Space: Moved holiday and seasonal setups into reference files to declutter the dashboard.
- Compact Layouts: Condenses room selector grid pads, border radii, and weights for clean UI.
- Solid Accents: Upgraded day and time slots with bold solid badges and optimized spacing.
- Sidebar Layout: Promoted Room Finder and Faculty timetables into the primary drawer navigation.
- Smart Sync: Skips background class reminders automatically when the academic semester has ended.
- Favorites Tips: Added helpful empty state guidance text within the materials library list.
- Fine Styling: Perfected list spacing in schedule rows and card border curves.

### Fixed

- Countdown Trigger: Restored the 10-day active threshold for exam cards so they display only when imminent.
- Shimmer Outages: Resolved stuck loading skeletons across attendance calendars and list shimmers.
- Attendance Alerts: Fixed vertical alignment and formatting details on critical absence cards.

## 1.7.6 — Premium Animations, Smart Grouping & Accuracy Fixes (May 8, 2026)

### Added

- Sleeker Cards: Subjects and folders now share a premium card design with smooth morphing animations
- Concise Login: The Login screen now honors your "Concise UI" preference, hiding status cards for a cleaner look
- Auto-Grouping: Marks and attendance are now grouped by category (Quizzes, Assignments, etc.)
- Interactive Summary: Tap any assessment pill to jump straight to the detailed view
- Icon Legend: A new guide explaining every notification type (find it via the info icon)
- Makeup Week Support: The Dashboard now recognizes and displays "Makeup Week" during the final semester phase
- Feature Visibility: Added Room Finder to the intro slides and app info screen
- Smart Fallbacks: Automatic default avatars if a profile image fails to load

### Improved

- Modern Layouts: Staggered grid widths on Dashboard and Papers screens for a more dynamic look
- Satisfying Micro-interactions: Fixed ripple clipping on PopupMenu triggers for a cleaner tactile feel
- Session Hardening: Background refreshes now verify cookie validity in real-time to prevent syncing with stale sessions
- Calendar Accuracy: Extended classes-end detection to account for the final makeup classes week
- Optimized Infrastructure: Migrated background system to a more battery-efficient engine

### Fixed

- Course Name Fix: Resolved an issue where courses with dashes (e.g., "AI - Lab") were being shortened in Insights
- Reference Error: Fixed a bug in the data engine that could cause syncs to hang in specific scenarios

## 1.7.5 — Room Finder, Micro-Interactions & Export Polish (May 2, 2026)

### Added

- Room Finder is now available — search the university-wide timetable to instantly see which rooms are free or busy at any time and day
- Two modes: "By Slot" lets you pick a day and time to see all free/busy rooms at once; "By Room" lets you search any room and see its full weekly schedule
- Availability labels are precise and context-aware — "FREE UNTIL X" tells you how long a room stays free, "FREES AT X" tells you exactly when it opens up
- Rooms are grouped by block (F Block, C Block, Labs, etc.) and sorted chronologically within each availability window
- Covers the entire university timetable — not just your own courses — so you can find any free room across all sections
- Dedicated Share screen now available for timetable and datesheet exports — a proper home for all your export needs
- Three export sources: your selected courses, a fully custom hand-picked selection, or an entire section at once
- Four export formats: image (PNG), PDF, Excel spreadsheet (.xlsx), and raw JSON data
- Two layout modes: Calendar view (week grid) and Tabular view (day-by-day list) — switch before exporting
- Full-screen Marks snapshot export also added — share your marks card directly from the Marks screen
- "Include current" toggle lets you decide whether to include today's data in your export
- NavIconButton in TopNav now tilts, rotates, and morphs on press for a satisfying tactile feel
- Fresh startup mode introduced — skips OTA check, cache lookup, and background data initialization for an instant cold start

### Improved

- Shimmer placeholders show while results are loading — no blank screens during search
- Exam season is detected automatically — Room Finder disables itself during exams since exam venues are assigned manually on notice boards
- Export options include venue, instructor, course code, and full name toggles for full control over what appears in the output
- LockOverlay now cross-fades between lock and unlock icons before the overlay exits — smoother visual handoff
- PopupMenu options now individually tilt their icons on press
- SideNav nav items now tilt their icon on press instead of scaling — matches the TopNav style and feels more premium
- SideNav group headers now tilt their section icon when you expand or collapse a group
- ActivityRow cards scale on press and the more-icon tilts when the menu opens
- CategoryCard icons shake on expand/collapse, with dots icon tilt on press
- AcademicCard now has compact header, press scale, animated chevron, and a loading shimmer that matches the real layout
- Settings group cards have opposing icon and chevron tilt on press for a premium feel
- Marks parsing completely rewritten as a single-pass operation (was 3 passes) — significantly faster data processing
- Timetable helper functions enhanced for university-wide room occupancy parsing
- Action controls and popup behavior unified across Timetable and Datesheet screens for consistency
- Datesheet time slot detection refined with stricter filtering safeguards
- FlexPrime branding refined with unified smooth button rounding animations across Dialog, Sheet, and CustomTimePicker
- Contribution graph corrected — grid now anchors to the actual day-of-week, trailing future cells are invisible, and empty cells are visually distinct from active ones
- AcademicJourney loading state replaced with inline shimmer cards that match the real layout instead of a separate skeleton component
- Attendance risk indicators integrated with optimized next-item navigation
- App-wide storage refresh logic centralized and simplified — legacy keys list removed
- Dashboard update notifications refined for better clarity and less noise

### Fixed

- Removed native DateTimePicker libraries that caused crashes — switched to a reliable community-standard alternative
- Fixed a crash caused by captureRef being called before the view was mounted
- Fixed ReferenceErrors in Share screen — all state and config values are now properly scoped and initialized
- Fixed a greedy break bug in best-of case handling that was selecting the wrong item
- Fixed a name-collision bug in selectedIds — now uses index tracking instead of item name
- PARTIAL login now correctly skips the student info fetch and extracts URLs from the marks page directly
- Fixed a study plan skip condition that was incorrectly firing on FULL syncs too
- Fixed divide-by-zero error in category average accumulation
- Fixed missing gap between multiple exam cards in the Datesheet view
- Fixed possible parsing issues with EE and FSM department timetables — edge cases in schedule structure are now handled correctly

## 1.7.4 — Biometric Lock, Smart Notifications & Smoother Everything (April 27, 2026)

### Added

- You can now lock the app with your fingerprint or face ID — it kicks in automatically when you leave and come back
- Tapping a class notification now shows a live summary — your attendance standing and latest marks, all in one place
- Attendance status is color-coded: green when you're safe, yellow as a heads-up, red when you're running out of chances
- Same for marks — at a glance you know if you're doing great, need to catch up, or things are critical
- Reviews and References screens now show detailed skeleton previews while loading instead of a blank screen
- Real-time GitHub contribution graph integrated directly into your developer profile
- Horizontal scrolling for a full 52-week view of your coding consistency

### Improved

- Falls back to your PIN or pattern if biometrics aren't available, so it always works
- Tap the attendance or marks badge directly from the notification preview to jump straight into the detailed view for that subject
- Classes that have already ended show a celebratory finish state instead of a plain status message
- Venue and teacher info now look cleaner with a consistent card style that fits the app theme
- Absence limits are now calculated more reliably even when credit hour data isn't perfectly clean
- Tapping the attendance badge from a notification takes you straight to that subject's attendance record — no searching needed
- Side menu items now have a satisfying spring animation when you press them — small but makes a difference
- The active section in the side menu now expands automatically so you always land in the right place
- Navigating between screens feels noticeably smoother — animations no longer stutter when screens are data-heavy
- Heavy screens wait for navigation to finish before loading content, so you never see a janky mid-slide render
- Persistent caching (24h) for instant graph loading on subsequent visits
- Manual refresh action with a pulsing sync indicator for up-to-the-minute activity updates
- Redesigned "Let's Connect" section with a streamlined grid of social actions
- Integrated the premium QR-share modal for easy app sharing directly from the Dev screen
- Refined skill group styling and overall card hierarchy for a more professional developer portfolio feel
- Profile screen got a visual refresh — cleaner layout, better spacing, easier to read at a glance
- Game screen redesigned with a more polished look
- Context menus, the dashboard, and the app details section all received subtle consistency tweaks

### Fixed

- Fixed a background crash that could cause the app to freeze when a notification was tapped — completely resolved
- Fixed a bug where all subjects showed only 3 allowed absences — theory courses now correctly show 6
- Several screens that used to flash or flicker while loading data now transition cleanly
- Various minor glitches across different screens quietly squashed

## 1.7.3 — Modular Updates, Diagnostic Grid & Login Refinement (April 24, 2026)

### Added

- Created useUpdates hook to centralize OTA update logic, ensuring consistent behavior across all entry points
- Introduced a 2-column AppStatus grid on the Login screen for quick access to version info, changelogs, and support

### Improved

- Migrated Settings update logic to the centralized hook, removing over 50 lines of redundant code
- Standardized update check cooldowns and UI feedback (toasts/dialogs) into a single reusable service
- Added descriptive action-oriented labels (e.g., "Tap to check") to status buttons for better guidance
- Redesigned Login footer with a bottom-aligned layout and subtle dividers for a more professional finish
- Synchronized heights and spacing across all diagnostic elements for a perfectly balanced interface
- Reduced button roundness and switched to surface-neutral backgrounds for diagnostic tools
- Restored the high-contrast tagline and campus info to the Login screen layout

### Fixed

- Resolved a bug where update button clicks were ignored due to incorrect event argument handling
- Removed redundant imports and variables from TopNav and Login components after refactoring

## 1.7.2 — Datesheet Metrics, Timetable Logic & Semester Calculation Fixes (April 24, 2026)

### Added

- Integrated subject performance metrics into exam cards, displaying current weighted percentage and absolute marks for each subject
- Overhauled Application Type cards with a premium tactile design, featuring spring-based scaling and vibrant LinearGradients

### Improved

- Enhanced exam card interactivity with dynamic border-radius transitions and high-contrast tactile feedback on press
- Polished "Prepare" button with high-contrast active states and smooth ripple transitions
- Improved discipline matching by switching to short-code identification (e.g., "BCS") for better compatibility with timetable strings
- Integrated a tiered haptic feedback system (light, medium, heavy) across all interactive surfaces including navigation, settings, and academic modules
- Redesigned card headers in Applications for better visual hierarchy and modern icon backgrounds
- Added descriptive icons to the Profile academic section for better visual navigation
- Refined Dashboard welcome card spacing and typography for a cleaner first impression

### Fixed

- Integrated loading state feedback into the Datesheet screen header
- Overhauled section matching logic to handle whitespace and case-formatting inconsistencies in timetable data
- Ensured transcript-verified sections are explicitly prioritized and correctly labeled as exact matches
- Resolved a critical bug in getCurrentSemester where incorrect data property mapping caused the semester to return as 0
- Hardened semester calculation with robust fallbacks to batch data, ensuring accurate progression tracking for all students

## 1.7.1 — Core Optimization, Notification Logic & UI Cleanup (April 23, 2026)

### Improved

- Removed legacy easter egg button and hidden dialog from ScreenWrapper for a cleaner navigation experience
- Overhauled background synchronization logic for better reliability and faster data recovery
- Optimized notification scheduling and cancellation logic to prevent duplicate alerts
- Refactored ThemeContext and optimized internal theme tokens to reduce memory footprint
- Improved theme switching performance with optimized memoization in core providers
- Polished Attendance and Marks components for better visual consistency across themes
- Improved Login screen state handling and keyboard transition smoothness

### Fixed

- Optimized FAB button rendering logic to prevent interaction interference
- Resolved sync orphaning issues where tasks would persist after manual logout
- Cleaned up legacy theme definitions and unified color constants

## 1.7.0 — Unified Profile, UI Evolution & Smart Sync (April 19, 2026)

### Added

- Introduced an interactive Vertical Timeline for academic events with automatic state parsing (Ongoing, Soon, Ended)
- Standardized Footer UI: All action buttons now share a uniform 32px height and consistent corner radii
- Calendar view is now embedded directly inside the Attendance Preview sheet — see your full attendance calendar without leaving the subject detail view
- Added a dedicated Info button in the calendar header — opens the attendance legend sheet directly from the calendar toolbar

### Improved

- Merged Information and Profile screens into a single, high-performance Academic Hub
- Redesigned Personal Details into a modern, grid-based identity hero with degree pills and quick actions
- Account Insights: Technical usage stats replaced with a clean, grid-based insights dashboard
- Relocated Version Pill from Dashboard header to an extended Star button in the SideNav footer
- Extended Star Button: Now dynamically displays the version string alongside the feedback action icon
- Refined Sync Header: Sync indicators now hide completely once successful to keep the dashboard minimal
- Enhanced Button Logic: The changelog icon now hides during sync to prevent interaction overlap and settles back on idle
- Decluttered Header: Removed informational sync notes from the dashboard view for a more focused experience
- Sheet bottom padding is now device-aware using the navigation bar height constant, preventing content from clipping behind system UI
- Redesigned empty state: replaced plain text with a centred icon, heading, and descriptive message for a more polished no-data experience
- Navigation chevron icon size now uses the typography scale instead of a hardcoded value for better text-to-icon harmony
- Content container padding increased (horizontal 42 px, top 48 px) for better breathing room on all screen sizes
- Step list and session card now have a maxWidth cap of 320 px to prevent awkward stretching on wider displays

### Fixed

- Removed redundant navigation routes and unified state management for profile data
- Corrected layout shift issues in the dashboard header during sync transitions
- Sheet slide animation now uses the shared SCREEN_HEIGHT constant for consistent behavior across all devices
- Removed the inline day-detail panel from the calendar body — detail is now handled by the legend and selection flow, reducing visual clutter
- Login completion callback now fires 500 ms after success state so the user briefly sees the confirmation before navigation proceeds
- Sheet close delayed to 900 ms to let navigation settle before dismissal, eliminating the flash-and-close race condition

## 1.6.9 — Comprehensive Sync, Auth Stability & UI Rebranding (April 16, 2026)

### Added

- Added dedicated support action buttons as square tiles in the navigation footer

### Improved

- Sync engine now fetches comprehensive data from both Dashboard and Profile pages
- Migrated background tasks to expo-background-fetch for better reliability and performance
- Streamlined authentication flow with better persistence of login success state
- Side navigation redesigned with collapsible sections for a cleaner interface
- Removed personal branding and developer credits from login, dashboard, and about screens
- Cleaned up footer notes and branding elements for a more professional aesthetic

### Fixed

- Resolved first-login sync failure by ensuring credentials are available for auth hash generation
- Fixed WebView stage reset that would occasionally loop security checks after successful login

## 1.6.8 — Toast Enhancements & UI Polish (March 30, 2026)

### Added

- Added a new "tip" style for helpful information popups
- New welcome card on the dashboard shows your profile info nicely

### Improved

- Toast messages now have more options for showing progress and hints
- Update and download messages are now clearer and more consistent
- Sheet notifications replaced with toast messages in timetable and datesheet operations
- Timetable and datesheet updates now check for new versions faster
- Dashboard update prompts are simpler with direct download buttons
- Datesheet updates show better progress without extra loading screens
- App update notifications give clearer success or error messages
- Small design tweaks in the top navigation and dashboard cards
- Datesheet actions redesigned with separate export and options buttons

### Fixed

- Timetable update flows simplified with consistent toast notifications
- Fixed display issues in the datesheet update screens
- All update messages now use the same clear notification style
- Timetable loading skeleton updated to match real component layouts
- Fixed rendering errors in popup menus and sheet descriptions
- Improved navigation parameter handling to prevent serialization warnings

## 1.6.7 — Post-Eid Patch — Performance, Polish & Crash Fixes (March 25, 2026)

### Added

- Major revisions and feature drops are targeted for before mid-May

### Improved

- WebView injection script overhauled — removed redundant re-injections and unnecessary re-renders
- Login flow is noticeably faster — reduced overhead between page load and form fill
- Navigation after successful login is smoother with less intermediate state flickering
- Icon wrappers redesigned across multiple screens — more consistent sizing, rounding, and background treatment
- Loading skeleton improved — better placeholder proportions and shimmer coverage
- Several components tightened up with minor rendering and layout improvements

### Fixed

- Fixed a crash on the Faculty screen that occurred under certain data conditions
- March and April will continue to see steady minor patches, fixes, and small improvements
- Every bug report, suggestion, and piece of feedback directly influences what gets built next

### Tweaked

- Duplicate style tag injection guarded — no more stacking of loader and close button styles on every poll tick
- Icon colors refined in several places for better contrast and theme consistency
- Minor spacing and alignment polish carried over from pre-Eid build
- Bigger updates are planned and heavily shaped by your feedback — keep it coming

## 1.6.5 — Fetch Reliability, Parallel Sync & Session Resilience (March 18, 2026)

### Added

- Parallel fetch mode added as experimental opt-in — fetches data in 3 ordered parallel pairs for faster syncs
- Token refresh mechanism added to study plan and transcript — on login redirect, re-hits info page for a fresh dump= token instead of retrying the stale URL
- Parallel Fetch added as experimental setting — off by default, opt-in for faster sync at the cost of session ordering
- Several major improvements and new features are currently in development but held back due to build limitations — planned for release in the first week of April

### Improved

- fetchData fully refactored — skip flags computed once upfront, no more scattered inline conditions causing silent partial failures
- Marks and attendance now throw on failure instead of silently returning empty — partial success no longer possible
- Study plan fetched immediately after profile load while session token is freshest — dramatically reduces redirect-to-login failures
- Transcript elevated to second priority fetch — also benefits from early session freshness
- Soft refresh upgraded — marks and attendance now run via Promise.all, redundant promise chaining removed
- User stats now reliably synced at the end of both fetchData and softRefresh — previously fire-and-forget

### Fixed

- Datesheet skip condition restored in partial refresh — correctly skips if all exams passed and last exam was within 30 days
- All skip flags now logged in a single block at fetch start for easier debugging
- PARTIAL refresh correctly falls back to FULL if no previous data is available
- Fixed missing import issues that caused repeated silent failures on launch
- Fatal errors in fetchData now always surface via toast and rethrow — no more swallowed exceptions
- Non-critical fetches (transcript, study plan, historical) warn explicitly on failure without breaking the main fetch flow
- Token refresh failures now logged clearly instead of silently returning null
- Various minor error boundary improvements and silent failure resolutions throughout data layer
- Fixed faculty detail sheet rendering incorrectly due to professor object being stored as name string instead of full object
- Fixed broken image in faculty detail sheet — was referencing undefined variable instead of selected professor
- Fixed faculty deep link matching — now correctly matches by ID instead of generated name slug
- Minor improvements and fixes will continue to roll out in between

### Tweaked

- Keep your feedback coming — it directly shapes what gets prioritised next

## 1.6.4 — Settings Polish, Profile Stats & UI Refinements (March 17, 2026)

### Added

- Labels (New, Beta, Heavy) now render on a separate row below each setting — no longer shift icon or control alignment
- Added missing handlers for Reset UI Preferences and Manage Notifications actions
- AMOLED Background option added to Appearance settings
- Toast stack repositioning now uses spring animations — toasts slide smoothly to their new positions when a peer is added or dismissed

### Improved

- Minor layout and spacing improvements across several dashboard cards
- Smoother transitions on several navigation flows with reduced jank

### Fixed

- Fixed disabled state on action rows incorrectly referencing wrong variable
- Status row now correctly reflects blocked state instead of always showing Active
- Toast component now correctly requires an active channel before showing warnings or errors
- Soft Refresh early-exit paths now properly show feedback via an open toast channel
- Minor error boundary improvements and silent failure handling throughout

### Tweaked

- Settings groups reorganised into cleaner, more logical categories for easier navigation
- Scale setting now renders as a non-pressable row — no accidental ripple on font size controls
- Profile screen now displays additional account stats pulled from the server
- Stats are now synced fresh from the database on app startup in the background
- Semester Progress card now updates instantly on theme change — no longer delayed by debounce

## 1.6.3 — Ramadan Toggle, Settings Cleanup & UI Polish (March 16, 2026)

### Added

- New experimental Soft Refresh — refreshes marks and attendance within your active session window without requiring a full re-login
- Added Markdown support to Note component descriptions via new useMarkdown prop

### Improved

- Expand/collapse animations on Insights cards refined for smoother, less jarring transitions
- Card layout and visual hierarchy improved across marks and attendance groups
- Layout restructured with improved information hierarchy and spacing
- Full-mode Note layout refactored — icon and title now occupy Row 1, description stretches full width in Row 2 with no indentation
- All non-compact Notes in the References screen upgraded with Markdown-formatted descriptions and contextual icons

### Fixed

- Timetable end times now correctly populate when Ramadan Mode is disabled
- Fixed brief blank screen that appeared after CAPTCHA verification and before navigation — replaced with a polished "Login Successful" overlay
- Fixed rare double-navigation issue after login success where Dashboard could be pushed twice
- Attendance presence detection fixed — present and absent entries now correctly identified and labelled
- Minor fixes to pill rendering, unread state tracking, and dismissed card persistence
- Toast component border and progress bar gap fixed — blur layer now clips flush against the border with no visible seam
- Fixed incorrect notification cancellation during data refresh — exam notifications no longer wiped when rescheduling class notifications
- Notification cache bypass fixed — notifications now correctly detected as scheduled before skipping reschedule
- Minor fixes to data merging, stale closure handling, and async storage reads throughout

### Tweaked

- Top navigation bar reorganised — cleaner layout with better visual hierarchy and spacing
- Profile menu options consolidated and grouped by category for easier scanning
- All refresh actions (full sync, soft refresh, partial refresh) merged into a single dedicated Refresh button in the top bar
- Refresh button now has its own prominent treatment instead of being buried as a menu option
- Soft Refresh and Full Sync clearly distinguished in the refresh flow with separate labels and descriptions
- Ramadan Mode toggle moved from Developer Options to Settings > Interaction & Behavior — now accessible to all users
- Toggling Ramadan Mode now shows a countdown toast and automatically restarts the app after 5 seconds for a clean recalculation
- Courses in the timetable are now sorted by start time for consistent ordering
- Dashboard now shows an informational note about the Ramadan toggle with a direct link to the setting
- Runs in the background without disrupting the current view or wiping existing data
- Automatically skipped if a full sync is already in progress
- Shows contextual toasts for success, partial failure, and expired session
- Popup handling refined — sheets and dialogs dismiss more reliably on navigation
- Minor visual tweaks to grade badges, progress indicators, and category headers
- Link icon repositioned to the far-right end of the header row for cleaner alignment
- Notification rows in Settings now display on a single line with dots replacing newlines, and date/type pills are right-aligned
- Dean's List and Rector's List notes now use bullet points and bold text for better readability
- Expanded experimental glass/blur effects across more UI surfaces for a more cohesive visual language
- Theme color changes now propagate instantly to all dashboard cards without debounce delay

## 1.6.2 — Share App Feature, Toast Markdown & UI Optimizations (March 11, 2026)

### Added

- Added a new "Share App" option in the SideNav — spread the word with fellow FASTians
- Integrated QR Code generator for quick and offline sharing of the repository link
- Integrated native platform share dialog for direct social and messaging sharing
- Branded sharing sheet with app repository link and scan-to-download instructions
- Markdown support added to Toast notifications — descriptions now support bolding and rich formatting
- SideNav layout refined with new icons and descriptive subtitles for the share feature

### Improved

- Optimized toast triggers in Summary component to prevent overlapping with sheet closures

### Tweaked

- Toast description styles standardized across the app for consistent information hierarchy
- Reduced the vertical gap between title and description in ScreenWrapper for a tighter, more professional look
- Summary component sheets updated with markdown-supported subtitles and better action labels

## 1.6.1 — Reviews Improvements, Timetable Fix & Professor Index Update (March 11, 2026)

### Added

- Professor index updated with newly added professors from NucesRate
- Unhide all professors option added to the stats menu on the reviews screen
- Intro dialog added on first visit explaining data source, fuzzy matching caveats and how to hide professors
- Keyboard-aware scroll added to login screen — view adjusts smoothly when focusing inputs

### Improved

- Improved edge case handling for schedule changes and missing period data

### Fixed

- Match confidence indicator now correctly reflects exact matches with 90–100% scores instead of fuzzy approximations
- Hide professor feature now correctly persists and skips hidden professors on future syncs
- Fixed timing calculation bug affecting Ramadan schedule — period offsets now compute correctly under adjusted timetable
- Background color now correctly fills the area below the scroll view when the keyboard is dismissed
- Minor stability improvements across reviews sync flow
- Several small edge cases addressed in data handling and display

### Tweaked

- Exact name matching now runs before fuzzy search — reduces mismatch rate for professors with identical or near-identical names
- Match confidence badge now shows green, amber or red depending on score threshold
- Input chaining from roll number to password skips scroll entirely when keyboard is already open

## 1.6.0 — Insights Engine, Login Overhaul, Marks Redesign & Performance (March 10, 2026)

### Added

- Introduced a live diff-checking engine that detects changes in marks and attendance between refreshes
- Semester change detection automatically resets the baseline when a new semester begins
- App icon, tagline and feature list now appear on the login screen for a stronger first impression
- Progress bar track added, height reduced slightly and overflow clipping improved
- Finalising toast added at the end of the fetch pipeline for clearer progress feedback
- Context value no longer creates a new object on every render — significant render reduction across all consumers

### Improved

- Smart deduplication ensures the same insight is never shown twice — timestamps refresh on re-detection instead
- Fuzzy matching handles course code mismatches and portal inconsistencies gracefully
- Baseline is built from locally stored data on first app start for accurate first-refresh diffing
- Completely redesigned login screen with a cleaner three-zone layout — branding, form and footer
- CAPTCHA WebView sheet redesigned with app icon header, dynamic status banner and smooth loading overlay
- Loading overlay now enforces a minimum 500ms display time with a 300ms fade-out for readability
- Login sheet closes instantly on success with no blank-sheet flash during navigation
- Eliminated redundant credential load and save cycles causing unnecessary component noise
- Marks screen rebuilt with redesigned subject header, tabs, activity rows and performance cards
- Assessment cards completely redesigned — now use a unified accordion layout where header and content form one connected card with no nested box feel
- Multiple expanded cards are visually distinct and clearly separated — no more ownership confusion between headers and content
- Collapsed cards now clearly communicate tapability with consistent primary color text and visible chevrons
- Thin animated divider appears between header and content on expand for clean visual separation
- Subject total average now accurately reflects weighted contributions from every individual assessment
- ActivityRow redesigned to match the unified card language — flat rows inside the parent card with no redundant borders
- Total rows get a subtle elevated background and divider instead of a separate border box
- Min/Max stats rendered in tertiary color, average in secondary — clearer visual hierarchy in stats row
- Grade pill updated to match app-wide pill style with consistent border and radius
- Smart number formatting — trailing zeros removed across all marks displays (9.00 shows as 9, 3.80 as 3.8)
- Assessments table redesigned for cleaner data presentation and better readability
- Dashboard now surfaces pending insights with a dedicated sheet for quick review after each refresh
- Stale data warning appears when data is older than 72 hours with a one-tap refresh shortcut
- Semester progress card flipped — now shows time elapsed with a filling progress bar instead of time remaining, which felt counterintuitive
- Semester card value now shows relative format like 7 / 16w for instant context without mental math
- Returning users skip redundant network calls on every fetch — only runs on genuine first login
- Datesheet screen completely redesigned with improved layout, spacing and visual hierarchy
- Dev screen redesigned for better internal tooling experience
- Intro slides redesigned with improved flow and visual presentation
- Poor network handling improved — version checks and refresh logic skip gracefully without leaving the app in a broken state
- Display, Summary and Timetable screens memoized to prevent cascade re-renders on context updates
- StyleSheet moved outside ActivityRow component — no longer recreated on every render
- OTA update logic refactored in App.js with a cleaner and more reliable auth flow

### Fixed

- Insights screen now shows actionable notifications when new marks are posted, attendance is corrected, or scores change
- Input cards now show real-time valid and error states with squircle badges and color-coded borders
- All error sheets upgraded with rich markdown descriptions, subtitles and actionable guidance per error type
- Class average calculation fixed — now correctly uses weighted formula across all assessments instead of raw sum
- MarksPreview semester now self-resolves without requiring manual selection in most cases
- Fast and full fetch paths both correctly update the lastUpdated timestamp
- Notification icon extracted and resized for correct display across all contexts
- Intro slides check now runs before any changelog or data clear logic — fresh installs no longer risk hitting the wrong route
- Changelog refresh skipped entirely on fresh installs with no existing data — no unnecessary clears on first launch
- Failsafe splash timer now also sets a Login fallback route if initialRoute was never resolved
- Datesheet now loads correctly on first login — selected courses from timetable are passed explicitly instead of reading stale state
- DataContext value object stabilized with useMemo — prevents unnecessary re-renders across the entire app
- Over 20 inline functions extracted to useCallback with correct dependency arrays
- FolderCard ripple effect fixed for correct touch feedback behavior
- Toast orphaning on sheet close fixed across multiple screens
- Timeout useEffect dependency array corrected — no longer includes non-reactive ref values
- Old superseded functions removed from DataContext reducing dead code
- Duplicate hook calls merged into single destructures throughout the codebase
- All debug console logging gated behind a dev-only flag — zero noise in production builds
- Icon font loading stabilized across all screens and build profiles
- Multiple minor bug fixes across screens, components and edge case flows

### Tweaked

- AboutApp screen rebuilt with section subtitles and a cleaner information structure
- TopNav refresh descriptions updated for clarity across all screens
- Sheet component now supports markdown rendering with subtitles across all sheets in the app
- App tagline updated — "Your academics and potential, finally as prime as your ambitions"

## 1.3.1 — Enhanced Toast System, Attendance Preview & UI Refinements (February 18, 2026)

### Added

- Added queue management for multiple toasts
- Added subtle animations to attendance indicators

### Improved

- Removed test code that was accidentally in production
- Improved positioning and timing for better visibility
- Refined attendance card UI with better visual hierarchy
- Improved preview subject layout and spacing
- Enhanced visual feedback when viewing attendance records
- Enhanced subject cards with micro-interactions
- Smoother transitions between different marks views
- Optimized animation performance across multiple screens
- Improved state management for smoother transitions
- Refined gesture handling for interactive components
- Improved color contrast for accessibility

### Fixed

- Enhanced toast notification system with better stability
- Better error boundaries and fallback UI

### Tweaked

- Better empty states and loading skeletons
- Refined spacing consistency throughout the app
- Small visual polish to various UI elements

## 1.3.0 — UI Revamp, Ramadan Timings & Toast Notifications (February 12, 2026)

### Added

- Added micro-interactions and subtle tappable animations throughout
- New interactive components for smoother navigation
- Intelligent schedule adjustment for Ramadan timings
- Toggle to enable/disable Ramadan mode (temporary display only)
- Classes automatically shift earlier with cumulative 30-min cuts
- Visual indicators when Ramadan mode is active
- Preserves original schedule data - no permanent modifications
- Added global toast system for better user feedback
- Non-intrusive design with auto-dismiss functionality
- Seamless integration with data fetch operations

### Improved

- Completely redesigned interface across multiple screens
- Enhanced visual feedback with shimmer effects and micro-animations
- Refined spacing, typography, and component consistency
- Still in experimental phase - improvements ongoing
- Significantly reduced initial load times
- Optimized re-renders across the app
- Smarter update handling with better version checks
- Improved state management for faster screen transitions
- Enhanced data caching strategy
- Redesigned login experience with bottom sheet
- Smoother authentication flow
- Improved visual feedback during login

### Fixed

- Context-aware success, error, and info toasts
- Better session handling and error states

## 1.2.5 — Datesheet Restoration & Smarter Updates (February 07, 2026)

### Improved

- Improved Excel parsing logic for more accurate course matching
- Enhanced transcript-aware exam mapping for better auto-selection
- Stronger version validation checks for both Timetable and Datesheet
- Improved comparison logic to prevent unnecessary re-downloads
- Better fallback handling when update metadata is unavailable
- Improved spacing and content grouping for faster navigation
- Further UI optimizations planned across dashboard and planner

### Tweaked

- Re-enabled full Datesheet processing and remote handling pipeline
- Cleaner metadata management for versioning and update timestamps
- Reorganized dashboard components for quicker visual scanning
- Prioritized actionable sections over static informational data
- Removed always-on-top static blocks that provided low context value
- Your feedback matters — report any issues or inconsistencies

### Notes

- More refinements to update handling and data sync logic coming soon

## 1.2.4 — Dynamic GPA Planning & Menu Restoration (February 02, 2026)

### Added

- Roadmap Aesthetic Refresh: New pin-style visuals for target CGPA and difficulty status
- New "Export Results" feature: Easily share a high-quality snapshot of your GPA Roadmap

### Improved

- Weighted SGPA Math: Improved calculation accuracy for future targets based on remaining credits
- Restored 3ndot Popup Menu with Batch Grades and Export functionality
- Balanced Header Design: Space-efficient tabs with 28% width for better menu visibility
- Text-Only Tab Navigation: Cleaner look with "SGPA", "CGPA", and "Planner" labels
- Contextual Menu Colors: Primary color highlighting for important action triggers
- Enhanced Batch Grades: Assign grades across multiple courses simultaneously from any semester

### Fixed

- Fixed activity indicator sizing during the login authentication phase
- Updated difficulty indicators with consistent semantic colors (Tip, Info, Warning, Error)
- Refined line-height and typography across the roadmap flow for better readability

### Tweaked

- Dynamic Semester Mapping: The planner now contextually identifies your remaining degree path
- Adaptive Target Selection: "Target Semester" chips now reflect real-time progress from your transcript
- Unified Clear All: One-tap reset for all simulation data across current and planner tabs

## 1.2.3 — Storage Insights, Performance Boost & UI Polish (February 02, 2026)

### Added

- New Storage Breakdown section in Settings with detailed category insights
- Added recursive directory scanning for accurate storage reporting
- New "Clear Files" action specifically for your downloaded documents
- Introduced unified UIProvider for consistent theme and sheet management
- New Shimmer/Skeleton loading UI for Storage and other heavy sections
- Expanded Campus Support: Added support for additional campus codes and older batches

### Improved

- Safe Cache Clearing: Optimize storage without affecting your academic data
- Completely refactored DataContext fetching logic for 2-3x faster data sync
- Implemented parallel network requests using Promise.allSettled
- Optimized dashboard stat calculations for instant loading
- Improved blur synchronization and state handling across screens
- Reduced unnecessary re-renders in heavy components like Timetable
- Improved action sheets with destructive and successive highlighting
- Zero-Flicker Transition: Refined viewport hiding for a smoother portal experience

### Fixed

- Fixed text cutoff and line-height issues across several screens
- Fixed critical ReferenceErrors and syntax issues in core modules
- Moved app flags like "Intro Completed" to persistent preferences
- Standardized border logic and rounding for all setting rows
- Enhanced error boundaries and fallback UI throughout the app
- Intelligent Auto-Formatting: App automatically corrects roll numbers to university standards

### Tweaked

- Integrated Filesystem scanning to track downloaded papers and exported files
- Relative path display for local files makes it easier to identify stored content
- Refined row layouts in Settings for a more premium and spaced-out feel
- Flexible Roll Number Handling: No more strict dash requirements during entry

## 1.2.2 — Login Improvements, Course Recommendations & Enhanced Calculators (January 26, 2026)

### Added

- Introducing intelligent course recommendation system (Beta)
- Currently in testing phase - your feedback will help shape final features
- Major new features planned for the next few weeks
- Community features and peer insights (under consideration)
- More users = better features for everyone through feedback and testing

### Improved

- Smart algorithms analyze your transcript to prioritize high-impact courses
- Improved SGPA/CGPA calculators with better visualizations
- Enhanced user interface for easier data input and results interpretation

### Fixed

- Resolved password forgetting issues during login process
- Fixed several minor errors and boundary cases in the login system
- Fixed numerous minor bugs and edge cases throughout the app
- Continued work on overall app stability and reliability

### Tweaked

- More integration with university systems and data sources
- Help us grow! Recommend FlexPrime to your Android-using friends
- Share your Prime experience with classmates and peers
- Together we can build the ultimate academic companion for FASTians
- Stay tuned for more exciting updates in the coming weeks!
- Your academic success is our mission.

### Notes

- Thank you for being part of the FlexPrime journey - your support makes all the difference
- Special thanks to our active testers and feedback providers

## 1.2.0 — Major Stability Update, FSM Timetable & Customization Overhaul (January 21, 2026)

### Added

- Many new features and enhancements are planned

### Improved

- Core application logic has been reworked for better reliability and performance
- This update lays the foundation for a stable and scalable build going forward
- Improved timetable data handling for accuracy and consistency
- Significant enhancements and rework in customization options
- Improved data handling and state consistency across screens
- Multiple UI and UX refinements for smoother interactions
- Further optimizations will build on this stable foundation
- Ongoing performance optimizations and quality improvements

### Fixed

- Multiple major bugs have been fixed across the app
- FSM timetable is now fully available and correctly parsed
- Resolved issues affecting timetable loading on fresh installs and logins
- Major internal logic refactors for improved stability
- This release marks the first truly stable build direction
- Overall app behavior is now more predictable and reliable

### Tweaked

- Additional customization options are in development

### Notes

- Thank you for your patience and continued support — it plays a huge role in shaping FlexPrime

## 1.1.6 (Alpha) — Latest Timetables & Stability Improvements (January 20, 2026)

### Added

- Latest timetables have been added for accurate reference
- Added smart subject deduplication for Papers (e.g. NLP = Natural Language Processing)
- Many new features, enhancements, and optimizations are coming

### Improved

- Some temporary glitches may still occur as updates are reworked for quick access
- Core logic reworked for faster and more stable access to app functionality
- Optimizations applied to improve performance and responsiveness
- Smoother Login page transition (preventing content flash)
- Stay updated to get the latest improvements as they release

### Fixed

- Many major bugs and issues have been fixed
- Minor fixes and enhancements will continue to be rolled out
- Multiple major bugs addressed
- Ongoing attempts to fix edge cases and improve stability
- Fixed data availability checks preventing unnecessary auth warnings
- Fixed stale statistics in Papers library
- Polished Changelog styling and layout consistency
- Fixed critical bug causing timetable to fail on fresh login

### Tweaked

- First fully stable build expected shortly after Mids 1

### Notes

- Thank you for your continued patience and support — it helps make FlexPrime better for everyone

## 1.1.5 (Alpha) — Stability Notices & Minor Fixes (January 14, 2026)

### Added

- More features and enhancements coming next semester

### Improved

- Avoid refreshing or logging out during registration period
- Improved guest mode handling

### Fixed

- Temporary instability, delays, or errors may occur
- Login issues are expected and will resolve gradually
- Added confirmation dialogs explaining login and crash issues
- Clear messaging for causes and expected resolution
- Fixed semester calculation logic
- Ongoing stability and experience improvements

### Tweaked

- Stay tuned for updates

### Notes

- Thanks for your patience and continued support

## 1.1.4 (Alpha) — UI Polish, Logic Refinements & Code Cleanup (January 14, 2026)

### Improved

- Reduced visual clutter across all screens for cleaner experience
- Improved card designs with more breathing room
- Simplified navigation elements for clarity
- Improved changelog screen with better formatting and organization
- Improved semester status boundary checks
- Enhanced data freshness validation
- Faster dashboard loading with optimized calculations
- Reduced unnecessary re-renders
- Better memory management
- Improved empty state messaging
- Enhanced visual feedback for user actions

### Fixed

- Fixed stale data detection logic showing false warnings
- Better handling of missing or incomplete data
- Corrected dashboard stat calculations
- Fixed minor layout issues on smaller screens
- Improved error message clarity

### Tweaked

- Fast Sync still experimental - occasional issues may occur
- Some edge cases in timetable matching under investigation
- Minor display inconsistencies on some small screens
- Universal timetable support for all faculties
- More dashboard customization options
- Additional analytics and insights

## 1.1.3 (Alpha) — Major Backend Overhaul, Materials Rewrite & Enhanced Analytics (January 13, 2026)

### Added

- Added more insightful data and analytics to dashboard
- New features for better material organization and discovery
- Added experimental Fast Sync feature for faster updates
- New timetable implementation with universal support
- Expanded features for materials and course management
- Additional analytics and insights features
- Foundation laid for major upcoming features

### Improved

- Faster access to your complete academic progress at a glance
- Enhanced visualization of degree requirements and completion status
- Improved navigation between semesters and course history
- Better data handling with improved calculations and metrics
- Enhanced quick insights with more relevant academic information
- Improved visual representation of key statistics
- Smarter data aggregation for meaningful summaries
- Implemented "Best Of" logic for more accurate grade calculations
- Better handling of repeated courses and grade replacements
- Improved SGPA/CGPA approximations with edge case handling
- Enhanced grade prediction accuracy
- Completely reworked materials logic from the ground up
- Seamless browsing experience with faster load times
- Enhanced search and filtering capabilities
- Improved categorization and metadata handling
- Reworked timetable backend logic for better reliability
- Improved course matching and schedule generation
- Better handling of venue information and time slots
- Improved handling of semester transitions
- Enhanced validation for academic periods and dates
- Major backend restructuring for better performance
- Enhanced conditional logic and data handling throughout
- Better state management across complex operations
- Optimized data processing pipelines
- More robust API integrations and data fetching
- Enhanced loading states with better user feedback
- Smoother overall experience with reduced lag
- Enhanced caching strategies for faster data access
- Optimized rendering and component lifecycle
- Better memory management and resource utilization
- Enhanced notification system
- This is one of the largest backend overhauls since launch
- Many under-the-hood improvements may not be immediately visible
- Your feedback drives every improvement

### Fixed

- Fixed calculation inconsistencies in marks display
- Fixed major issue with timetable data handling and processing
- Fixed many semester end issues and edge cases
- Better boundary checks across all academic modules
- Resolved data inconsistencies at semester boundaries
- Improved error handling and recovery mechanisms
- Improved empty states and error displays
- Major fixes and bugs removed throughout the app
- Improved app stability and reliability
- Focus on stability, performance, and data accuracy
- Still in alpha - occasional bugs may occur

### Tweaked

- Merged Transcript and Study Plan into one "Academic Journey" page
- Better degree overview with comprehensive semester-by-semester breakdown
- Better file type detection and display
- Syncs only dynamic/relative data instead of full refresh
- Significantly reduced sync times for frequently changing data
- Smart detection of what needs updating vs what stays cached
- Option to fall back to full sync if needed
- Better UI handling across all screens
- Solved numerous edge cases in data presentation
- More consistent visual feedback for user actions
- Better responsive behavior across device sizes
- More customization options and personalization
- Continuous refinement based on user feedback
- Fast Sync is experimental - report any sync issues
- Restart app if you experience any stuck screens
- Clear cache if data appears inconsistent
- Report any breaking issues through in-app feedback
- Special recognition to early adopters who reported edge cases
- Community support makes this development possible
- Keep the feedback coming - it matters!

### Notes

- New timetable features coming soon with expanded support
- New timetable support coming soon for all faculties
- Huge thanks to all testers and active users

## 1.1.2 (Alpha) — Minor Font Adjustments & UI Tweaks (December 13, 2025)

### Improved

- Minor rendering optimizations
- Small improvements to screen transitions

### Fixed

- Tweaked some text that was appearing too small
- Minor adjustments to font scaling in a few screens
- Fixed minor layout issues
- Cleaned up small visual inconsistencies

### Tweaked

- Small tweaks to spacing and alignment
- Adjusted some button states for better visibility
- Just a small maintenance update
- Nothing major—keeping things polished
- Report any font issues you still notice

## 1.1.1 (Alpha) — Font Resize & Minor Optimizations (December 12, 2025)

### Added

- Added app intro/developer info page
- About page for curious users interested in app details
- Community reached 60+ active users!
- Focus shifting to enhancing existing features
- No new features until absolutely needed

### Improved

- Improved readability across all screens and components
- Various performance enhancements across modules
- Working on restoration with improved integration
- Community feedback driving all improvements

### Fixed

- Fixed minor UI inconsistencies and bugs
- Better state management in several screens
- Improving stability and performance of current tools

### Tweaked

- Finished thorough font adjustments throughout entire app
- Text now properly scales without breaking layouts
- Temporarily closed reviews page due to API issues
- Font adjustments should work universally
- Report any text/layout issues immediately
- Have fun and always provide feedback!

## 1.1.0 (Alpha) — Screen Adaptability, Major Optimizations & Stability Improvements (December 10, 2025)

### Added

- Added font scaling customization in Appearance settings
- New implementation will handle all sections and course types
- Some features still being refined and optimized

### Improved

- Rewrote major logic components for significant performance gains
- Fastened up multiple data processing and fetching operations
- Better state management across all screens for smoother interactions
- Reduced unnecessary re-renders and optimized component lifecycle
- Improved app load times and transition speeds
- Improved data consistency across modules
- Refined layouts and component positioning across screens
- Better visual consistency and theme application
- Improved button states and interaction feedback
- Enhanced card layouts and spacing for cleaner appearance
- Polished animations and transitions throughout the app
- Major code refactoring and optimization efforts
- Improved caching strategies for faster data access
- Enhanced background processing logic
- Long way to go, but substantial improvements made
- All feedback, criticism, and enhancement suggestions highly appreciated

### Fixed

- Fixed overflow and text cutoff issues across all devices
- Fixed numerous navigation and materials linking bugs
- Better error handling and edge case management
- Fixed major state handling issues that caused crashes or freezes
- Still in alpha but approaching first stable release
- Major foundation work completed for stable transition
- Significant progress in reliability and consistency
- Most critical bugs and issues have been addressed
- Reach out immediately if you encounter any issues or errors

### Tweaked

- Full support for different screen sizes - text now adjusts dynamically
- Adjust text size up or down based on your preference and readability needs
- Better layout responsiveness for tablets and smaller devices
- Better memory management and resource utilization
- Cleaner code architecture for easier future maintenance
- Timetable scripts will be rewritten next semester for universal support
- Planning full support for FSM, EE, and other schools currently limited
- Current timetable works best for FCS-related schedules
- Your support and usage means everything to this project
- Timetable support limited for non-FCS schools (temporary)
- Restart app if you experience any stuck screens
- Report any breaking issues through in-app feedback

### Notes

- Resolved many known issues and broken code segments
- Thank you to everyone who has been testing and providing feedback
- Special thanks to all early adopters and active testers
- Still an alpha build - occasional bugs may occur

## 1.0.9 (Alpha) — Unified Timetable, UI Enhancements & Notes (November 28, 2025)

### Added

- Added support for fetching previous semester data (experimental)
- Introduced new Notes page (currently in early development)
- Notes feature will be enhanced based on user feedback
- Better course support and integration

### Improved

- Improved timetable matching logic and course support
- Enhanced UI and performance for timetable views
- Massive UI enhancements across the application
- General speed-ups and performance optimizations
- Open to collaboration and feedback for improvements

### Fixed

- Better stability and error management

### Tweaked

- Integrated EE/FSM (BBA, BSBA, BSFT, BSAF, etc.) into a unified timetable
- Refined typography and icon usage for better theme consistency
- Minor visual adjustments and polish throughout
- Alpha phase closing soon - shifting to stable releases
- Enrolled testers will receive special entitlements in stable build
- Star us on GitHub and share with others!

### Notes

- Improved bug handling and fixed minor/major known issues

## 1.0.8 (Alpha) — Fresh Materials, UI Overhaul & Performance Boost (November 13, 2025)

### Added

- Separated feature sections in navigation for improved clarity
- Quick report and suggestions feature now accessible from side nav
- Better feature discoverability with improved menu structure
- Enhanced navigation flow between related features
- Use the quick report feature in side nav for issues

### Improved

- Enhanced classification system with better paper type detection
- Improved categorization for Course Outline, Guide, Materials and more
- Redesigned side navigation with dual-column layout for better organization
- Enhanced visual hierarchy and spacing throughout the app
- Polished card layouts and component styling
- Reviews page now available to all users with 20-30x faster loading
- Significantly improved data handling and processing logic behind the scenes
- Faster initial app load times and smoother transitions
- Optimized rendering for better responsiveness
- Enhanced caching strategies for frequently accessed data
- Improved SGPA approximation logic to avoid invalid or inaccurate results
- Note: Calculator screen improvements coming in next update
- General code optimizations and cleanup
- Clearer separation between academic, utility, and settings sections
- Calculator screen overhaul with improved SGPA/CGPA calculations
- Further performance optimizations to reduce minor lags
- Some minor lags expected - further optimizations planned
- Your input helps shape future updates and improvements

### Fixed

- Fixed major UI inconsistencies across multiple screens
- Fixed several bugs and caveats in marks screen display
- Resolved major data handling issues across multiple modules
- Fixed inconsistencies in SGPA and CGPA calculations
- Improved error handling and edge case management
- Better stability across different screen sizes and devices
- Minor bug fixes and calculation inconsistencies resolution
- Please report any inconsistencies, errors, or mistakes you encounter
- Breaking features or critical bugs should be reported immediately

### Tweaked

- Complete materials data refresh with accurate file sizes and metadata
- Better file organization with standardized naming conventions
- Materials now load with proper size information (KB/MB format)
- Better handling of edge cases in grade calculations
- More reliable grade predictions and estimations
- Additional timetable support for EE, FSM, and other faculties
- More visual polish and animation refinements
- Timetable currently limited to FCS-related schedules only
- If you cannot see your timetable, please reach out for potential solutions
- All criticism and feedback highly appreciated

### Notes

- Still an alpha build - occasional instability and breaking changes possible
- Thank you for your patience during alpha development

## 1.0.7 (Alpha) — Enhanced Views & UI Improvements (November 07, 2025)

### Added

- Added separate dedicated screen for adding timetable courses with improved layout
- Introduced standalone attendance preview screen for better detail visibility
- Better typography and text alignment throughout new screens
- Improved empty state handling for new screens
- Notes feature temporarily under development - will be rebuilt from scratch
- Focus on improving core academic tracking features
- Some features may be limited or under active development

### Improved

- Enhanced course addition flow with clearer input fields and validation
- Improved attendance tracking with dedicated fullscreen view
- Refined card layouts and spacing for better visual hierarchy
- Improved button styling and interaction feedback
- Enhanced color consistency across timetable and attendance modules
- Polished transitions between list and detail views
- Optimized rendering performance for timetable and attendance screens
- Reduced unnecessary re-renders in course addition forms
- Improved data loading and caching strategies
- Enhanced memory management for better app responsiveness
- Smoother animations and transitions between screens

### Fixed

- Fixed layout inconsistencies in course addition workflow
- Resolved minor visual bugs in attendance preview
- Better error messaging and validation feedback
- Gradual improvements to overall app stability and polish
- Still in alpha - occasional bugs and performance variations expected
- Feedback and bug reports appreciated via in-app reporting

### Tweaked

- Continued refinement of user experience based on feedback
- Restart app if screens appear unresponsive

## 1.0.6 (Alpha) — UI Polish, New Features & Refined Interactions (November 02, 2025)

### Added

- Added interactive Tic-Tac-Toe game with AI opponent (Easy, Medium, Hard difficulty levels)
- Game features local 2-player mode and statistics tracking with win streaks
- Introduced comprehensive Faculty browser for Lahore campus
- Faculty profiles include teaching assignments, contact info, education, and research details
- Smart matching system links faculty with their current courses from your timetable
- Focus shifted to UX refinements and new utility features
- Game and faculty features serve as foundation for more interactive tools
- Some features still in planning/development stage

### Improved

- Improved popup menu styling with better visual hierarchy
- Enhanced control cards with consistent sizing and proportions
- Implemented proper turn validation for game logic
- Optimized faculty search and filtering with better performance
- Enhanced popup menus with cleaner option rendering and dividers
- Improved state management for smoother transitions
- Improved disabled state consistency across all interactive elements
- Enhanced markdown rendering for faculty profiles
- Major speed optimizations and performance improvements
- Enhanced caching strategies for faster load times

### Fixed

- Fixed rapid tap issues preventing double-input across interactive elements
- Resolved AI turn issues in game mode - player now always goes first
- Fixed visual feedback for invalid moves in interactive components
- Better handling of empty states and loading conditions
- Better error handling and recovery mechanisms
- Feedback and bug reports highly appreciated via in-app reporting

### Tweaked

- Refined card layouts and spacing across multiple screens
- Polished game board interface with smooth animations and better feedback
- Better typography consistency and color usage throughout the app
- Faculty database now includes profiles, research, and publications
- Course-instructor mapping for better context in faculty profiles
- Game statistics persist across sessions with AsyncStorage
- Support for multiple campuses in faculty data (Lahore available, more coming)
- Additional visual polish and animations
- More campus support for faculty browsing
- Assessment tracking and exam utilities
- Post-mids update will bring significant performance gains
- Minor adjustments and visual polish ongoing
- Solo development continues - updates may vary in pacing
- Faculty data currently limited to Lahore campus only
- Game statistics may reset if app data is cleared
- Restart app if screens appear stuck or unresponsive
- Clear cache/data as last resort for persistent issues

### Notes

- Still an alpha build - expect occasional bugs and performance variations

## 1.0.5 (Alpha) — Performance Boost, UI Refinements & Solo Dev Updates (October 28, 2025)

### Added

- Direct in-app feedback and reporting options added
- Planning additional utilities and features for future releases
- User patience is appreciated — major upcoming update will be substantial but will take time to polish

### Improved

- Massive load-time improvements on key screens
- Enhanced consistency across modules
- Optimized caching and background processing for smoother experience
- Note: Solo development has been intense — some updates are delayed due to burnout/exhaustion, affecting pacing
- Improved adaptive behavior across devices and screen sizes
- On Android 12+, true glass-like frosted effects enabled for overlays where possible
- Better handling of datesheet data and related updates
- Internal logic refined to reduce calculation discrepancies
- Continuous improvements guided by user suggestions
- Further blur and UI enhancements to be implemented gradually
- App has been optimized to be as smooth and fluid as possible for everyone
- Overlay and blur effects are subtle to maintain performance, with improvements planned in future updates

### Fixed

- Fixed several deadlocks and runtime errors
- Minor UI fixes and layout refinements for better clarity
- Common fixes for stuck screens or long waits: restart the app, clear cache; if persistent, clear app data and log in again (usually not needed)

### Tweaked

- Notifications, assessments, and advanced utilities still being refined
- Ongoing efforts to polish caching, responsiveness, and edge-case handling
- Next update may take some time due to resource constraints and solo dev workload

### Notes

- Implemented subtle blur effects on overlays (more coming soon)
- Preparations made for upcoming push notifications for updates and reminders
- This is still an alpha build — expect bugs, errors, and some performance/display issues across devices (platform-independent)

## 1.0.4 (Alpha) — Refinements, Responsiveness & Smarter UI Decisions (October 25, 2025)

### Added

- Added better edge-case handling for smoother experience across modules
- Introduced selective visibility for certain details to enhance clarity
- Added new components for better modularity and design flexibility

### Improved

- Improved overall responsiveness and UI snappiness
- Optimized various calculations for faster updates and transitions
- Removed older scraped sources with limited materials to improve reliability
- Enhanced load times and reduced unnecessary background processing
- Improved adaptive behavior across different screen sizes
- Reworked internal calculation methods for better accuracy (still under refinement)
- Dashboard and calculator values now align more closely with expected logic
- Further improvements to mark and grade approximation methods planned for next release
- Further refinement of caching and load-time improvements ongoing
- Still an alpha-stage build, but one built with care for smoother upcoming exam cycles

### Fixed

- New bug-detection and debugging methodologies being implemented gradually

### Tweaked

- Refined layout to feel more consistent and less overwhelming
- Made subtle adjustments for a cleaner and more cohesive interface feel
- Notifications and Assessments sections currently under active consideration
- Continuous user feedback appreciated — it plays a huge role in polishing future updates

## 1.0.3 (Alpha) — Smoothness, Optimizations & UI Revamp (October 21, 2025)

### Added

- Added better internal optimizations and animation handling
- Introduced improved animations and more cohesive motion design
- Added a few hidden easter eggs

### Improved

- Enhanced overall app smoothness and responsiveness
- Improved logical flow for more natural screen transitions
- Reduced micro-lags and enhanced gesture fluidity
- Refined and modernized several interface components
- Enhanced Timetable UI with restored venue information on cards
- Converted long cards into collapsible, customizable expandables for focused viewing
- Continuing work on faster app load and better caching behavior
- Further animation optimization and smoother screen mounting

### Fixed

- Resolved several visual and logical bugs across screens
- Improved stability in data handling and transitions
- Fine-tuned minor inconsistencies in layouts and colors

### Tweaked

- Gathering user feedback to guide upcoming customization and theme options
- Preparing more snappier and responsive UI configurations for the next release

## 1.0.2 — Modernization & Experience Enhancements (October 18, 2025)

### Added

- Added skeleton loaders and improved loading states for better responsiveness
- Introduced a new unified Materials page combining multiple sources efficiently
- Expanded customization options and personalization features

### Improved

- Redesigned login, materials, and reviews pages with a more modern and cohesive look
- Improved overall visuals and alignment across screens
- Enhanced transitions, animations, and layout consistency
- Faster and smoother navigation experience
- Optimized data fetch logic for faster screen loads
- Improved data handling and UI responsiveness on resource-heavy pages
- General improvements for a smoother, more stable user experience

### Fixed

- Fixed rendering issues and visual inconsistencies
- Reduced visual lag and improved stability under low network conditions
- Resolved multiple bugs, errors, and inconsistencies across components
- Fixed minor layout and alignment issues
- Limited Notifications page functionality temporarily for backend restructuring

### Tweaked

- Refined guest mode for a seamless login-free experience
- Temporarily paused Assignments page development until future release
- More pages and tools for both logged-in and guest users
- Additional visual polish and advanced theme controls

## 1.0.1 (Alpha) — Major UI & Data Overhaul (September 17, 2025)

### Added

- Timetable share functionality in multiple formats
- Past papers and reviews (moderators only)
- Additional moderator tools and features

### Improved

- Complete UI redesign with modern layouts
- Enhanced grids and quick insights visibility
- Improved timetable with calendar and tabular views
- Reworked settings screen with better organization
- Current semester data fetch instead of last semester
- Improved data handling and processing
- Code optimizations for smoother experience
- Enhanced quick insights and visibility options

### Fixed

- Better edge case and error handling throughout
- Enhanced stability and optimizations
- Removed errors and bugs from marks page
- Fixed attendance page issues
- General bug fixes and performance improvements

### Tweaked

- Updated changelog sheet design
- Assessments with Google Classroom integration

### Notes

- Datesheet integration (coming soon)

## 1.0.0 (Alpha) — Performance & Experience Update (September 3, 2025)

### Added

- New and efficient timetable fetching
- Welcome sheet introduced
- Changelog sheet added (under development)

### Improved

- Improved login with auto input capability
- Better optimizations in Subjects page
- Transcript improvements
- Code reworks for smoother performance

### Fixed

- Minor and major bug fixes

### Tweaked

- Study Plan refinements
