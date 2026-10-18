# Contributing to aerospace-security-notes

Thanks for wanting to help! This repo is a beginner-friendly study resource for aerospace and satellite cybersecurity. It grows best when people with different backgrounds (aerospace, RF, satellite comms, security, or just learning) shape it together.

You don't need to be an expert. Fixing a typo, suggesting a source, or pointing out a confusing explanation all count.

## Ways to contribute

- **Add or improve a topic**: fill in a stub file, expand a thin section, or add a missing topic.
- **Fix mistakes**: wrong facts, unclear wording, broken links, formatting problems.
- **Suggest sources**: papers, talks, standards, or write-ups worth reading. Add them to `sources.md` or tell us in an issue.
- **Suggest what to cover next**: open an issue with the topic and why it matters.
- **Review for clarity**: if something was hard to follow as a beginner, that's useful feedback.

## How to contribute

### Quick suggestions (no Git needed)
Open an [issue](https://github.com/eli-cipher/aerospace-security-notes/issues) describing the correction, topic idea or source. Include the file name if it's about existing content.

### Changes to the notes
1. Fork the repo.
2. Create a branch with a clear name, e.g. `add-gps-spoofing-notes` or `fix-orbits-typo`.
3. Make your changes (see the guidelines below).
4. Open a pull request explaining what you changed and why.

For large additions (a whole new topic or section), please open an issue first so we can agree on where it fits.

## Writing guidelines

- **Plain language first.** Explain ideas so a beginner can follow. Define jargon the first time it appears.
- **Your own words.** Synthesize and explain; don't copy text from papers, books or websites. Short quotes are fine if clearly marked and credited.
- **Respect the reading order.** Content flows `fundamentals/` → `attack-surface/` → `offensive-techniques/`. Put new material where a reader would expect it, and keep each folder's `README.md` up to date.
- **Match the depth of the folder.** `fundamentals/` stays lean (short entries, tables); `attack-surface/` is moderate; `offensive-techniques/` goes deep.
- **Cite your sources.** Add anything you used to `sources.md`.
- **Use Markdown.** Keep formatting simple and consistent with nearby files.
- **Mark unfinished work.** A stub file means "planned, not missing". If you start a topic but don't finish it, say so at the top of the file.

## Scope and responsible use

`offensive-techniques/` explains how satellite systems get attacked, so readers can understand and defend them. It is **not** a guide to unauthorized access. Please keep contributions in that spirit:

- Focus on concepts, methodology and defense, not step-by-step instructions to attack live systems.
- Don't include real credentials, private data, or details that expose specific operational systems.
- Remind readers that testing should only happen on systems they own or are authorized to test.

Contributions that go against this may be edited or declined.

## Be kind

Everyone here is learning. Give feedback politely, assume good intent, and help newcomers. Harassment or disrespect isn't welcome.

## Questions?

Open an issue, or reach out to the author, Eli Cipher, via [GitHub](https://github.com/eli-cipher) or [LinkedIn](https://www.linkedin.com/in/elicipher).
