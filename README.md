# Faster CPython Ideas

Discussion and work tracker for Faster CPython project.

New ideas should be created as new [issues](https://github.com/faster-cpython/ideas/issues/new/choose).  It is ok if the idea is not fully formed -- we treat them as discussions to arrive at something actionable.  (We had previously used discussions for this, but that is now deprecated).

The [CPython issue tracker](https://github.com/python/cpython/issues) should be used for actual work-in-progress. 

Some links to presentations and other preliminary documentation:

- [Guido's slides at the 2021 Python Language Summit](FasterCPythonDark.pdf)
- [Mark's slides explaining Tiers of Execution](https://docs.google.com/presentation/d/1_cvQUwO2WWsaySyCmIy9nj9by4JKnkbiPCqtluLP3Mg)
- [PEP 659](https://peps.python.org/pep-0659/)

## Published Results

<!-- START table -->
## linux x86_64 (linux)
| date | fork | ref | version | hash | vs. 3.10.4: | vs. 3.11.0: | vs. base: |
| --- | --- | --- | --- | --- | ---: | ---: | ---: |
| [2023-03-21](results/bm-20230321-3.12.0a6%2B-12595f6) | iritkatriel | remove_JUM | 3.12.0a6+ | 12595f6 | [1.30x faster \*](results/bm-20230321-3.12.0a6%2B-12595f6/bm-20230321-linux-x86_64-iritkatriel-remove_JUMP_IF_FALSE-3.12.0a6%2B-12595f6-vs-3.10.4.md) | [1.03x faster \*](results/bm-20230321-3.12.0a6%2B-12595f6/bm-20230321-linux-x86_64-iritkatriel-remove_JUMP_IF_FALSE-3.12.0a6%2B-12595f6-vs-3.11.0.md) | [1.01x slower](results/bm-20230321-3.12.0a6%2B-12595f6/bm-20230321-linux-x86_64-iritkatriel-remove_JUMP_IF_FALSE-3.12.0a6%2B-12595f6-vs-base.md) |
| [2023-03-21](results/bm-20230321-3.12.0a6%2B-7f760c2) | python | 7f760c2fca | 3.12.0a6+ | 7f760c2 | [1.31x faster \*](results/bm-20230321-3.12.0a6%2B-7f760c2/bm-20230321-linux-x86_64-python-7f760c2fca3dc5f46a51-3.12.0a6%2B-7f760c2-vs-3.10.4.md) | [1.04x faster \*](results/bm-20230321-3.12.0a6%2B-7f760c2/bm-20230321-linux-x86_64-python-7f760c2fca3dc5f46a51-3.12.0a6%2B-7f760c2-vs-3.11.0.md) |  |
| [2023-03-20](results/bm-20230320-3.12.0a6%2B-094cf39) | python | 094cf392f4 | 3.12.0a6+ | 094cf39 | [1.31x faster \*](results/bm-20230320-3.12.0a6%2B-094cf39/bm-20230320-linux-x86_64-python-094cf392f49d3c16fe79-3.12.0a6%2B-094cf39-vs-3.10.4.md) | [1.04x faster \*](results/bm-20230320-3.12.0a6%2B-094cf39/bm-20230320-linux-x86_64-python-094cf392f49d3c16fe79-3.12.0a6%2B-094cf39-vs-3.11.0.md) |  |
| [2023-03-20](results/bm-20230320-3.12.0a6%2B-bcf40dc) | itamaro | eager_task | 3.12.0a6+ | bcf40dc | [1.31x faster \*](results/bm-20230320-3.12.0a6%2B-bcf40dc/bm-20230320-linux-x86_64-itamaro-eager_tasks_factory-3.12.0a6%2B-bcf40dc-vs-3.10.4.md) | [1.04x faster \*](results/bm-20230320-3.12.0a6%2B-bcf40dc/bm-20230320-linux-x86_64-itamaro-eager_tasks_factory-3.12.0a6%2B-bcf40dc-vs-3.11.0.md) | [1.00x slower](results/bm-20230320-3.12.0a6%2B-bcf40dc/bm-20230320-linux-x86_64-itamaro-eager_tasks_factory-3.12.0a6%2B-bcf40dc-vs-base.md) |
| [2022-10-24](results/bm-20221024-3.11.0-deaf509) | python | v3.11.0 | 3.11.0 | deaf509 | [1.26x faster](results/bm-20221024-3.11.0-deaf509/bm-20221024-linux-x86_64-python-v3.11.0-3.11.0-deaf509-vs-3.10.4.md) |  |  |
| [2022-03-23](results/bm-20220323-3.10.4-9d38120) | python | v3.10.4 | 3.10.4 | 9d38120 |  | [1.26x slower](results/bm-20220323-3.10.4-9d38120/bm-20220323-linux-x86_64-python-v3.10.4-3.10.4-9d38120-vs-3.11.0.md) |  |

## windows amd64 (pythonperf1)
| date | fork | ref | version | hash | vs. 3.10.4: | vs. 3.11.0: | vs. base: |
| --- | --- | --- | --- | --- | ---: | ---: | ---: |
| [2023-02-07](results/bm-20230207-3.11.2-878ead1) | python | 878ead1ac1 | 3.11.2 | 878ead1 | [1.11x faster](results/bm-20230207-3.11.2-878ead1/bm-20230207-pythonperf1-amd64-python-878ead1ac16519651263-3.11.2-878ead1-vs-3.10.4.md) | [1.00x faster](results/bm-20230207-3.11.2-878ead1/bm-20230207-pythonperf1-amd64-python-878ead1ac16519651263-3.11.2-878ead1-vs-3.11.0.md) |  |
| [2022-12-06](results/bm-20221206-3.11.1-a7a450f) | python | a7a450f84a | 3.11.1 | a7a450f | [1.10x faster](results/bm-20221206-3.11.1-a7a450f/bm-20221206-pythonperf1-amd64-python-a7a450f84a0874216031-3.11.1-a7a450f-vs-3.10.4.md) | [1.00x slower](results/bm-20221206-3.11.1-a7a450f/bm-20221206-pythonperf1-amd64-python-a7a450f84a0874216031-3.11.1-a7a450f-vs-3.11.0.md) |  |
| [2022-10-24](results/bm-20221024-3.11.0-deaf509) | python | deaf509e8f | 3.11.0 | deaf509 | [1.11x faster](results/bm-20221024-3.11.0-deaf509/bm-20221024-pythonperf1-amd64-python-deaf509e8fc6e0363bd6-3.11.0-deaf509-vs-3.10.4.md) |  |  |
| [2022-09-11](results/bm-20220911-3.11.0rc2-ed7c3ff) | python | ed7c3ff156 | 3.11.0rc2 | ed7c3ff | [1.11x faster](results/bm-20220911-3.11.0rc2-ed7c3ff/bm-20220911-pythonperf1-amd64-python-ed7c3ff15680c1939fad-3.11.0rc2-ed7c3ff-vs-3.10.4.md) | [1.01x faster](results/bm-20220911-3.11.0rc2-ed7c3ff/bm-20220911-pythonperf1-amd64-python-ed7c3ff15680c1939fad-3.11.0rc2-ed7c3ff-vs-3.11.0.md) |  |
| [2022-08-05](results/bm-20220805-3.11.0rc1-41cb071) | python | 41cb07120b | 3.11.0rc1 | 41cb071 | [1.11x faster](results/bm-20220805-3.11.0rc1-41cb071/bm-20220805-pythonperf1-amd64-python-41cb07120b7792eac641-3.11.0rc1-41cb071-vs-3.10.4.md) | [1.01x faster](results/bm-20220805-3.11.0rc1-41cb071/bm-20220805-pythonperf1-amd64-python-41cb07120b7792eac641-3.11.0rc1-41cb071-vs-3.11.0.md) |  |
| [2022-07-25](results/bm-20220725-3.11.0b5-0771d71) | python | 0771d71eea | 3.11.0b5 | 0771d71 | [1.10x faster](results/bm-20220725-3.11.0b5-0771d71/bm-20220725-pythonperf1-amd64-python-0771d71eea30316020a8-3.11.0b5-0771d71-vs-3.10.4.md) | [1.00x slower](results/bm-20220725-3.11.0b5-0771d71/bm-20220725-pythonperf1-amd64-python-0771d71eea30316020a8-3.11.0b5-0771d71-vs-3.11.0.md) |  |
| [2022-07-11](results/bm-20220711-3.11.0b4-5a7e1e0) | python | 5a7e1e0a92 | 3.11.0b4 | 5a7e1e0 | [1.10x faster](results/bm-20220711-3.11.0b4-5a7e1e0/bm-20220711-pythonperf1-amd64-python-5a7e1e0a92622c605ab2-3.11.0b4-5a7e1e0-vs-3.10.4.md) | [1.01x slower](results/bm-20220711-3.11.0b4-5a7e1e0/bm-20220711-pythonperf1-amd64-python-5a7e1e0a92622c605ab2-3.11.0b4-5a7e1e0-vs-3.11.0.md) |  |
| [2022-06-01](results/bm-20220601-3.11.0b3-eb0004c) | python | eb0004c271 | 3.11.0b3 | eb0004c | [1.08x faster](results/bm-20220601-3.11.0b3-eb0004c/bm-20220601-pythonperf1-amd64-python-eb0004c27163ec089201-3.11.0b3-eb0004c-vs-3.10.4.md) | [1.02x slower](results/bm-20220601-3.11.0b3-eb0004c/bm-20220601-pythonperf1-amd64-python-eb0004c27163ec089201-3.11.0b3-eb0004c-vs-3.11.0.md) |  |
| [2022-05-30](results/bm-20220530-3.11.0b2-72f00f4) | python | 72f00f420a | 3.11.0b2 | 72f00f4 | [1.09x faster](results/bm-20220530-3.11.0b2-72f00f4/bm-20220530-pythonperf1-amd64-python-72f00f420afaba3bc873-3.11.0b2-72f00f4-vs-3.10.4.md) | [1.01x slower](results/bm-20220530-3.11.0b2-72f00f4/bm-20220530-pythonperf1-amd64-python-72f00f420afaba3bc873-3.11.0b2-72f00f4-vs-3.11.0.md) |  |
| [2022-05-06](results/bm-20220506-3.11.0b1-8d32a5c) | python | 8d32a5c8c4 | 3.11.0b1 | 8d32a5c | [1.09x faster](results/bm-20220506-3.11.0b1-8d32a5c/bm-20220506-pythonperf1-amd64-python-8d32a5c8c4e9c90b0a21-3.11.0b1-8d32a5c-vs-3.10.4.md) | [1.01x slower](results/bm-20220506-3.11.0b1-8d32a5c/bm-20220506-pythonperf1-amd64-python-8d32a5c8c4e9c90b0a21-3.11.0b1-8d32a5c-vs-3.11.0.md) |  |
| [2021-11-05](results/bm-20211105-3.11.0a2-e2b4e4b) | python | e2b4e4bab9 | 3.11.0a2 | e2b4e4b | [1.02x faster](results/bm-20211105-3.11.0a2-e2b4e4b/bm-20211105-pythonperf1-amd64-python-e2b4e4bab90b69fbd361-3.11.0a2-e2b4e4b-vs-3.10.4.md) | [1.08x slower](results/bm-20211105-3.11.0a2-e2b4e4b/bm-20211105-pythonperf1-amd64-python-e2b4e4bab90b69fbd361-3.11.0a2-e2b4e4b-vs-3.11.0.md) |  |
| [2021-10-05](results/bm-20211005-3.11.0a1-7c12e48) | python | 7c12e4835e | 3.11.0a1 | 7c12e48 | [1.01x faster](results/bm-20211005-3.11.0a1-7c12e48/bm-20211005-pythonperf1-amd64-python-7c12e4835ebe52287acd-3.11.0a1-7c12e48-vs-3.10.4.md) | [1.09x slower](results/bm-20211005-3.11.0a1-7c12e48/bm-20211005-pythonperf1-amd64-python-7c12e4835ebe52287acd-3.11.0a1-7c12e48-vs-3.11.0.md) |  |
| [2022-03-23](results/bm-20220323-3.10.4-9d38120) | python | 9d38120e33 | 3.10.4 | 9d38120 |  | [1.11x slower](results/bm-20220323-3.10.4-9d38120/bm-20220323-pythonperf1-amd64-python-9d38120e335357a3b294-3.10.4-9d38120-vs-3.11.0.md) |  |

## darwin arm64 (darwin)
| date | fork | ref | version | hash | vs. 3.10.4: | vs. 3.11.0: | vs. base: |
| --- | --- | --- | --- | --- | ---: | ---: | ---: |
| [2023-03-18](results/bm-20230318-3.12.0a6%2B-3adb23a) | python | main | 3.12.0a6+ | 3adb23a | [1.20x faster \*](results/bm-20230318-3.12.0a6%2B-3adb23a/bm-20230318-darwin-arm64-python-main-3.12.0a6%2B-3adb23a-vs-3.10.4.md) | [1.02x slower](results/bm-20230318-3.12.0a6%2B-3adb23a/bm-20230318-darwin-arm64-python-main-3.12.0a6%2B-3adb23a-vs-3.11.0.md) |  |
| [2023-03-11](results/bm-20230311-3.12.0a6%2B-bb396ee) | python | main | 3.12.0a6+ | bb396ee | [1.19x faster \*](results/bm-20230311-3.12.0a6%2B-bb396ee/bm-20230311-darwin-arm64-python-main-3.12.0a6%2B-bb396ee-vs-3.10.4.md) | [1.02x slower](results/bm-20230311-3.12.0a6%2B-bb396ee/bm-20230311-darwin-arm64-python-main-3.12.0a6%2B-bb396ee-vs-3.11.0.md) |  |
| [2023-03-06](results/bm-20230306-3.12.0a5%2B-d3ca042) | python | main | 3.12.0a5+ | d3ca042 | [1.20x faster \*](results/bm-20230306-3.12.0a5%2B-d3ca042/bm-20230306-darwin-arm64-python-main-3.12.0a5%2B-d3ca042-vs-3.10.4.md) | [1.02x slower](results/bm-20230306-3.12.0a5%2B-d3ca042/bm-20230306-darwin-arm64-python-main-3.12.0a5%2B-d3ca042-vs-3.11.0.md) |  |
| [2022-12-11](results/bm-20221211-3.12.0a3%2B-70be5e4) | python | 70be5e42f6 | 3.12.0a3+ | 70be5e4 | [1.24x faster \*](results/bm-20221211-3.12.0a3%2B-70be5e4/bm-20221211-darwin-arm64-python-70be5e42f6e288de32e0-3.12.0a3%2B-70be5e4-vs-3.10.4.md) | [1.02x faster](results/bm-20221211-3.12.0a3%2B-70be5e4/bm-20221211-darwin-arm64-python-70be5e42f6e288de32e0-3.12.0a3%2B-70be5e4-vs-3.11.0.md) |  |
| [2022-12-05](results/bm-20221205-3.12.0a2%2B-e3a3863) | python | e3a3863cb9 | 3.12.0a2+ | e3a3863 | [1.18x faster \*](results/bm-20221205-3.12.0a2%2B-e3a3863/bm-20221205-darwin-arm64-python-e3a3863cb9561705d3dd-3.12.0a2%2B-e3a3863-vs-3.10.4.md) | [1.04x slower](results/bm-20221205-3.12.0a2%2B-e3a3863/bm-20221205-darwin-arm64-python-e3a3863cb9561705d3dd-3.12.0a2%2B-e3a3863-vs-3.11.0.md) |  |
| [2022-11-28](results/bm-20221128-3.12.0a2%2B-594de16) | python | 594de165bf | 3.12.0a2+ | 594de16 | [1.19x faster \*](results/bm-20221128-3.12.0a2%2B-594de16/bm-20221128-darwin-arm64-python-594de165bf2f21d6b28e-3.12.0a2%2B-594de16-vs-3.10.4.md) | [1.03x slower](results/bm-20221128-3.12.0a2%2B-594de16/bm-20221128-darwin-arm64-python-594de165bf2f21d6b28e-3.12.0a2%2B-594de16-vs-3.11.0.md) |  |
| [2022-11-21](results/bm-20221121-3.12.0a2%2B-cdde29d) | python | cdde29dde9 | 3.12.0a2+ | cdde29d | [1.19x faster \*](results/bm-20221121-3.12.0a2%2B-cdde29d/bm-20221121-darwin-arm64-python-cdde29dde90947df9bac-3.12.0a2%2B-cdde29d-vs-3.10.4.md) | [1.03x slower](results/bm-20221121-3.12.0a2%2B-cdde29d/bm-20221121-darwin-arm64-python-cdde29dde90947df9bac-3.12.0a2%2B-cdde29d-vs-3.11.0.md) |  |
| [2022-12-06](results/bm-20221206-3.11.1-a7a450f) | python | a7a450f84a | 3.11.1 | a7a450f | [1.22x faster \*](results/bm-20221206-3.11.1-a7a450f/bm-20221206-darwin-arm64-python-a7a450f84a0874216031-3.11.1-a7a450f-vs-3.10.4.md) | [1.00x faster](results/bm-20221206-3.11.1-a7a450f/bm-20221206-darwin-arm64-python-a7a450f84a0874216031-3.11.1-a7a450f-vs-3.11.0.md) |  |
| [2022-10-24](results/bm-20221024-3.11.0-deaf509) | python | deaf509e8f | 3.11.0 | deaf509 | [1.22x faster \*](results/bm-20221024-3.11.0-deaf509/bm-20221024-darwin-arm64-python-deaf509e8fc6e0363bd6-3.11.0-deaf509-vs-3.10.4.md) |  |  |
| [2022-09-11](results/bm-20220911-3.11.0rc2-ed7c3ff) | python | ed7c3ff156 | 3.11.0rc2 | ed7c3ff | [1.22x faster \*](results/bm-20220911-3.11.0rc2-ed7c3ff/bm-20220911-darwin-arm64-python-ed7c3ff15680c1939fad-3.11.0rc2-ed7c3ff-vs-3.10.4.md) | [1.00x faster](results/bm-20220911-3.11.0rc2-ed7c3ff/bm-20220911-darwin-arm64-python-ed7c3ff15680c1939fad-3.11.0rc2-ed7c3ff-vs-3.11.0.md) |  |
| [2022-08-05](results/bm-20220805-3.11.0rc1-41cb071) | python | 41cb07120b | 3.11.0rc1 | 41cb071 | [1.23x faster \*](results/bm-20220805-3.11.0rc1-41cb071/bm-20220805-darwin-arm64-python-41cb07120b7792eac641-3.11.0rc1-41cb071-vs-3.10.4.md) | [1.01x faster](results/bm-20220805-3.11.0rc1-41cb071/bm-20220805-darwin-arm64-python-41cb07120b7792eac641-3.11.0rc1-41cb071-vs-3.11.0.md) |  |
| [2022-07-25](results/bm-20220725-3.11.0b5-0771d71) | python | 0771d71eea | 3.11.0b5 | 0771d71 | [1.23x faster \*](results/bm-20220725-3.11.0b5-0771d71/bm-20220725-darwin-arm64-python-0771d71eea30316020a8-3.11.0b5-0771d71-vs-3.10.4.md) | [1.01x faster](results/bm-20220725-3.11.0b5-0771d71/bm-20220725-darwin-arm64-python-0771d71eea30316020a8-3.11.0b5-0771d71-vs-3.11.0.md) |  |
| [2022-07-11](results/bm-20220711-3.11.0b4-5a7e1e0) | python | 5a7e1e0a92 | 3.11.0b4 | 5a7e1e0 | [1.23x faster \*](results/bm-20220711-3.11.0b4-5a7e1e0/bm-20220711-darwin-arm64-python-5a7e1e0a92622c605ab2-3.11.0b4-5a7e1e0-vs-3.10.4.md) | [1.01x faster](results/bm-20220711-3.11.0b4-5a7e1e0/bm-20220711-darwin-arm64-python-5a7e1e0a92622c605ab2-3.11.0b4-5a7e1e0-vs-3.11.0.md) |  |
| [2022-06-01](results/bm-20220601-3.11.0b3-eb0004c) | python | eb0004c271 | 3.11.0b3 | eb0004c | [1.21x faster \*](results/bm-20220601-3.11.0b3-eb0004c/bm-20220601-darwin-arm64-python-eb0004c27163ec089201-3.11.0b3-eb0004c-vs-3.10.4.md) | [1.01x slower](results/bm-20220601-3.11.0b3-eb0004c/bm-20220601-darwin-arm64-python-eb0004c27163ec089201-3.11.0b3-eb0004c-vs-3.11.0.md) |  |
| [2022-05-30](results/bm-20220530-3.11.0b2-72f00f4) | python | 72f00f420a | 3.11.0b2 | 72f00f4 | [1.21x faster \*](results/bm-20220530-3.11.0b2-72f00f4/bm-20220530-darwin-arm64-python-72f00f420afaba3bc873-3.11.0b2-72f00f4-vs-3.10.4.md) | [1.01x slower](results/bm-20220530-3.11.0b2-72f00f4/bm-20220530-darwin-arm64-python-72f00f420afaba3bc873-3.11.0b2-72f00f4-vs-3.11.0.md) |  |
| [2022-05-06](results/bm-20220506-3.11.0b1-8d32a5c) | python | 8d32a5c8c4 | 3.11.0b1 | 8d32a5c | [1.21x faster \*](results/bm-20220506-3.11.0b1-8d32a5c/bm-20220506-darwin-arm64-python-8d32a5c8c4e9c90b0a21-3.11.0b1-8d32a5c-vs-3.10.4.md) | [1.01x slower](results/bm-20220506-3.11.0b1-8d32a5c/bm-20220506-darwin-arm64-python-8d32a5c8c4e9c90b0a21-3.11.0b1-8d32a5c-vs-3.11.0.md) |  |
| [2022-04-05](results/bm-20220405-3.11.0a7-2e49bd0) | python | 2e49bd06c5 | 3.11.0a7 | 2e49bd0 | [1.22x faster \*](results/bm-20220405-3.11.0a7-2e49bd0/bm-20220405-darwin-arm64-python-2e49bd06c5ffab7d1540-3.11.0a7-2e49bd0-vs-3.10.4.md) | [1.01x slower](results/bm-20220405-3.11.0a7-2e49bd0/bm-20220405-darwin-arm64-python-2e49bd06c5ffab7d1540-3.11.0a7-2e49bd0-vs-3.11.0.md) |  |
| [2022-03-07](results/bm-20220307-3.11.0a6-3ddfa55) | python | 3ddfa55df4 | 3.11.0a6 | 3ddfa55 | [1.17x faster \*](results/bm-20220307-3.11.0a6-3ddfa55/bm-20220307-darwin-arm64-python-3ddfa55df48a67a5972f-3.11.0a6-3ddfa55-vs-3.10.4.md) | [1.04x slower](results/bm-20220307-3.11.0a6-3ddfa55/bm-20220307-darwin-arm64-python-3ddfa55df48a67a5972f-3.11.0a6-3ddfa55-vs-3.11.0.md) |  |
| [2022-02-03](results/bm-20220203-3.11.0a5-c4e4b91) | python | c4e4b91557 | 3.11.0a5 | c4e4b91 | [1.09x faster \*](results/bm-20220203-3.11.0a5-c4e4b91/bm-20220203-darwin-arm64-python-c4e4b91557f18f881f39-3.11.0a5-c4e4b91-vs-3.10.4.md) | [1.12x slower](results/bm-20220203-3.11.0a5-c4e4b91/bm-20220203-darwin-arm64-python-c4e4b91557f18f881f39-3.11.0a5-c4e4b91-vs-3.11.0.md) |  |
| [2022-01-13](results/bm-20220113-3.11.0a4-9471106) | python | 9471106fd5 | 3.11.0a4 | 9471106 | [1.17x faster \*](results/bm-20220113-3.11.0a4-9471106/bm-20220113-darwin-arm64-python-9471106fd5b47418ffd2-3.11.0a4-9471106-vs-3.10.4.md) | [1.04x slower](results/bm-20220113-3.11.0a4-9471106/bm-20220113-darwin-arm64-python-9471106fd5b47418ffd2-3.11.0a4-9471106-vs-3.11.0.md) |  |
| [2021-12-08](results/bm-20211208-3.11.0a3-2e91dba) | python | 2e91dba437 | 3.11.0a3 | 2e91dba | [1.15x faster \*](results/bm-20211208-3.11.0a3-2e91dba/bm-20211208-darwin-arm64-python-2e91dba437fe5c56c6f8-3.11.0a3-2e91dba-vs-3.10.4.md) | [1.06x slower](results/bm-20211208-3.11.0a3-2e91dba/bm-20211208-darwin-arm64-python-2e91dba437fe5c56c6f8-3.11.0a3-2e91dba-vs-3.11.0.md) |  |
| [2021-11-05](results/bm-20211105-3.11.0a2-e2b4e4b) | python | e2b4e4bab9 | 3.11.0a2 | e2b4e4b | [1.15x faster \*](results/bm-20211105-3.11.0a2-e2b4e4b/bm-20211105-darwin-arm64-python-e2b4e4bab90b69fbd361-3.11.0a2-e2b4e4b-vs-3.10.4.md) | [1.05x slower](results/bm-20211105-3.11.0a2-e2b4e4b/bm-20211105-darwin-arm64-python-e2b4e4bab90b69fbd361-3.11.0a2-e2b4e4b-vs-3.11.0.md) |  |
| [2022-03-23](results/bm-20220323-3.10.4-9d38120) | python | v3.10.4 | 3.10.4 | 9d38120 |  | [1.22x slower \*](results/bm-20220323-3.10.4-9d38120/bm-20220323-darwin-arm64-python-v3.10.4-3.10.4-9d38120-vs-3.11.0.md) |  |


<!-- END table -->

There is also a [complete list of published results](results/README.md) (and [legacy results](benchmark-results/README.md)).
