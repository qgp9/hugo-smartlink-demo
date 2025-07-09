---
title: "Performance"
weight: 4
---

Hugo SmartLink is designed to be fast and efficient, even on large sites. This page details the performance benchmarks and how you can run them yourself.

## Performance Benchmarks

We have conducted extensive performance testing to measure the impact of Hugo SmartLink on build times. The results show that the module adds minimal overhead.

| Configuration | Build Time | Performance vs Baseline | SmartLink Overhead |
|---------------|------------|------------------------|-------------------|
| **SmartLink Disabled** | 141ms | 1.0x (baseline) | - |
| **SmartLink Enabled (HTML)** | 164ms | 1.16x | +23ms (+16%) |
| **SmartLink Enabled (Markdown)** | 220ms | 1.56x | +79ms (+56%) |

*Results from a test with 200 content files, each containing 166 SmartLinks.*

**Key Takeaways:**

- The **`html`** output format is significantly faster than `markdown`.
- The performance impact is linear and scales predictably with the amount of content.
- For most sites, the overhead of Hugo SmartLink will be negligible.

## Performance Testing

The `hugo-smartlink` project includes a `Makefile` and scripts to run your own performance tests.

### How to Run Tests

1.  Navigate to the `test` directory within the `hugo-smartlink` module.
2.  Run the following command:

```bash
# Run a performance test with 500 content files
make test-perf N_COPIES=500
```

You can adjust the `N_COPIES` variable to simulate different numbers of content files.

This allows you to measure the performance of Hugo SmartLink with a content volume that is representative of your own site.
