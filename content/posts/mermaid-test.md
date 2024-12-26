---
title: test
---

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

## Testing H

with stuff written

### Test Conclusion

The performance differences are striking:

- Conform processes failed commits 100x faster than `husky` + `commitlint`
- Successful commits show a 2x speed improvement with `conform`
- Even when using a hook manager, `conform` outperforms `commitlint`
  significantly

**_Fail_ Tests**:

| Configuration        |  Mean [ms]  | Min [ms] | Max [ms] | Rel-Slowdown |
| :------------------- | :---------: | :------: | :------: | :----------: |
| Conform              | 11.4 ± 0.9  |   8.9    |   14.5   |      0%      |
| pre-commit + Conform | 357.2 ± 7.3 |  344.6   |  367.0   |    -3003%    |
| Husky + Conform      | 639.1 ± 3.8 |  631.5   |  644.0   |    -5506%    |
| Husky + commitlint   | 1422 ± 0.14 |   1400   |   1439   |   -12374%    |

**_Pass_ Tests**:

| Configuration        |  Mean [ms]  | Min [ms] | Max [ms] | Rel-Slowdown |
| :------------------- | :---------: | :------: | :------: | :----------: |
| Conform              | 969.4 ± 5.7 |  966.4   |  985.5   |      0%      |
| pre-commit + Conform | 1258 ± 0.19 |   1238   |   1298   |     -30%     |
| Husky + Conform      | 1541 ± 0.16 |   1519   |   1570   |     -59%     |
| Husky + commitlint   | 2338 ± 0.44 |   2285   |   2414   |    -141%     |

Conform is the clear winner in terms of performance.

Based on the results, my decision tree is:

```mermaid
graph LR;
  A{Needs Hook Manager}
  A-- no -->1([Conform])
  A-- yes -->B{Node Project}
  B-- no -->2([pre-commit + Conform])
  B-- yes -->D{Commit Duration Important}
  D-- no -->3([Husky + commitlint])
  D-- yes -->F{Non-Node dependencies}
  F-- no -->3
  F-- yes -->4([Husky + Conform])
```

## Tool Install

While most of these commands will look familiar if you checked out the benchmark
scripts, I wanted to add a more thorough install guide, now that you may have a
better idea of what you might want to use.
