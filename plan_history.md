# Plan History

## Request / Opinions
- The user requested to remove the "rtltree" feature from this Vim plugin project.

## Approved Plan
1. **Remove Files**: Delete `plugin/automatic/rtl.vim` and the demo file `demo/rtl.gif`.
2. **Clean Code**: Remove references to the `Rtl Tree` from `plugin/automatic.vim`.
3. **Clean Documentation**: Remove all references, instructions, FAQs, and demos of `RtlTree` from `README.md`, `README_en.md`, `docs/README.md`, [docs/faq.md](file:///home/dennis/github/automatic-verilog/docs/faq.md), and [docs/handbook.md](file:///home/dennis/github/automatic-verilog/docs/handbook.md).

## Request / Opinions (2026-06-18)
- The user requested to stage, commit, and push the changes to GitHub.

## Approved Plan (2026-06-18)
1. Stage all changes using `git add -A`.
2. Commit with the message: "Remove RtlTree feature and clean up documentation".
3. Push changes to origin using `git push`.

## Request / Opinions (2026-06-18 - AutoInst Suffix Removal)
- The user requested to modify the `AutoInst` code to automatically strip `_i` and `_o` suffixes from connection signal names.
- The user requested that we test this change.

## Approved Plan (2026-06-18 - AutoInst Suffix Removal)
1. Modify [plugin/automatic/autoinst.vim](file:///home/dennis/github/automatic-verilog/plugin/automatic/autoinst.vim) at lines 1226 and 1297 to substitute `_i` and `_o` suffixes.
2. Create a test Verilog file in a scratch directory, run Vim in a test script to execute the `:AutoInst` command, and verify the output.

## Request / Opinions (2026-06-18 - Commit Suffix Changes)
- The user approved staging, committing, and pushing the suffix removal modification to GitHub.

## Approved Plan (2026-06-18 - Commit Suffix Changes)
1. Stage all changes (including `plugin/automatic/autoinst.vim` and `plan_history.md`).
2. Commit with the message: "Strip _i and _o suffixes from connection signal names in AutoInst".
3. Push changes to origin using `git push`.

## Request / Opinions (2026-06-22 - Autoinst Specific Target Path & Remove Directory Parsing)
- The user requested to modify AutoInst to support specifying a target search file inside the comment: `/*autoinst target_path.v */`.
- The user requested to completely remove `verilog-library-directories` and `verilog-library-directories-recursive` comment parsing.

## Approved Plan (2026-06-22 - Autoinst Specific Target Path & Remove Directory Parsing)
1. Update AutoInst searching patterns in [plugin/automatic/autoinst.vim](file:///home/dennis/github/automatic-verilog/plugin/automatic/autoinst.vim) to `\/\*autoinst\_.\{-}\*\/`.
2. Implement target path extraction, environment variable expansion, and direct parsing of the specified file, bypassing standard crossdir directory lookups.
3. Remove `verilog-library-directories` and `verilog-library-directories-recursive` parsing from [plugin/automatic/crossdir.vim](file:///home/dennis/github/automatic-verilog/plugin/automatic/crossdir.vim).
4. Run a headless Vim test to verify the implementation.

## Request / Opinions (2026-06-22 - Commit target path & directory parsing changes)
- The user approved staging, committing, and pushing the target path AutoInst and directory parsing removal changes to GitHub.

## Approved Plan (2026-06-22 - Commit target path & directory parsing changes)
1. Stage all changes (including `plugin/automatic/autoinst.vim`, `plugin/automatic/crossdir.vim`, and `plan_history.md`).
2. Commit with the message: "Add specific file path support to AutoInst and remove verilog-library-directories parsing".
3. Push changes to origin using `git push`.

## Request / Opinions (2026-06-22 - AutoInst trailing space fix)
- The user reported that AutoInst does not work when using comments with spaces like `/*autoinst ../rtl/sib_a.v */`.
- We discovered that trailing spaces inside the comment were captured in the path, causing file reading to fail.

## Approved Plan (2026-06-22 - AutoInst trailing space fix)
1. Modify [plugin/automatic/autoinst.vim](file:///home/dennis/github/automatic-verilog/plugin/automatic/autoinst.vim) around lines 251-253 to trim leading and trailing spaces from the captured file path.
2. Verify the fix using a test in the scratch directory.

## Request / Opinions (2026-06-22 - Commit trailing space fix)
- The user approved staging, committing, and pushing the trailing space fix to GitHub.

## Approved Plan (2026-06-22 - Commit trailing space fix)
1. Stage all changes (including `plugin/automatic/autoinst.vim` and `plan_history.md`).
2. Commit with the message: "Fix trailing space handling in AutoInst target path extraction".
3. Push changes to origin using `git push`.
