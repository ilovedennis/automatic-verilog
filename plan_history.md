# Plan History

## Request / Opinions
- The user requested to remove the "rtltree" feature from this Vim plugin project.

## Approved Plan
1. **Remove Files**: Delete `plugin/automatic/rtl.vim` and the demo file `demo/rtl.gif`.
2. **Clean Code**: Remove references to the `Rtl Tree` from `plugin/automatic.vim`.
3. **Clean Documentation**: Remove all references, instructions, FAQs, and demos of `RtlTree` from `README.md`, `README_en.md`, `docs/README.md`, `docs/faq.md`, and `docs/handbook.md`.

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
