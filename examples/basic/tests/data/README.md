# Independent reference vectors

The decoded `reference.jsonl` fixture contains 1,938 deterministic cases, one JSON object per line with `input` and `expected` fields. Source: CPython 3.12 arbitrary-precision `int`, `math.gcd`/`math.lcm`, modular `pow`, and independently encoded radix/two’s-complement representations. Seed: 781963120. Arithmetic rows cover 20 results per input, up to 4096-bit operands and 4097-bit shifts.

These values were exported once from the independent reference implementation used by `ecosystem/bigint/interop.py` at repository revision `27f8b1649561504bbe61d5247500e7cadc6eef42`, before removing that helper. No expected arithmetic or rendering result was captured from the GoML implementation under test. The reference source remains available in that historical revision for provenance; running these tests needs neither Python nor NumPy nor a downloaded reference runtime.

SHA-256 of this vector file: `749dc193cbc49983f2559adb1c0f8e31bd6cd5b4b3184510f65f1f89e1828b3c`.

Run `goml test --example basic` from the library root after resolving its development dependencies. `tests/reference_test.goml` evaluates each case directly through the GoML example API and asserts both the case count and results. New behavior should receive independently calculated expected values or a small native reference model; do not regenerate expectations from the implementation being tested.
