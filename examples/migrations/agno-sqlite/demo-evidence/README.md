# Captured live migration evidence

Run `7981da8f3764` on September 8, 2026 used actual Agno SQLite persistence,
the shipped Memanto CLI, a local Moorcheh server, and local Ollama models.
All source data is the explicitly scripted scenario in `demo_source.py`.

- `live-output-replay.mp4`: 98.5-second paced rendering of captured command output.
  This is a terminal-output replay, not a desktop pixel capture.
- `evidence/demo.cast`: original output with monotonic timestamps.
- `evidence/demo.log`: complete captured output.
- `evidence/generated-answers.json`: four source and destination answers, checked
  against unchanged required fragments; both sides used `qwen2.5:1.5b`.
- `evidence/earlier-0.5b-generated-answers.json`: earlier run in which the smaller
  model omitted CSV in one destination answer. No question or score was changed
  for the later run; these four checks do not establish general model quality.
- `evidence/live-validation.json`: actual retrieval responses and round-trip checks.
- `evidence/input-okf/` and `evidence/roundtrip-okf/`: complete input and output.
- `evidence/timings.json`: observed command durations, not comparative savings.

Four source memories were imported with zero failures. All four complete bodies,
including original metadata, survived export. Four generated-answer checks passed
on both sides with the larger model, and four answer-bearing retrieval checks passed.
The OKF CLI revision used here has no savings report; no savings claim is made.

These artifacts are hosted on a separate branch of the contributor's fork so the
implementation PR does not add a video binary to the upstream repository.
