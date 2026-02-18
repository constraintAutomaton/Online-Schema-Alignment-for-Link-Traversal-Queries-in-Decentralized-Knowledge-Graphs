# Query Evaluation Times

## Online Schema Alignment

| Query                                           | Run 1 (s) | Run 2 (s) | Run 3 (s) | Run 4 (s) | Run 5 (s) | Run 6 (s) | Run 7 (s) | Run 8 (s) | Run 9 (s) | Run 10 (s) | Avg (s) | Med (s) | Std (s) |
| ----------------------------------------------- | --------: | --------: | --------: | --------: | --------: | --------: | --------: | --------: | --------: | ---------: | ------: | ------: | ------: |
| Request the messages of liked users             |       4.7 |       4.8 |       5.9 |       8.5 |       7.7 |       7.4 |       8.2 |       5.8 |       6.9 |        9.1 |    6.90 |    7.05 |    1.58 |
| Request the forums a user posted                |         — |         — |         — |         — |         — |         — |         — |         — |         — |          — |       — |       — |       — |
| Request the information of a user               |       1.2 |       1.1 |       1.0 |       1.1 |       1.2 |       1.1 |       1.0 |       1.1 |       1.0 |        1.1 |    1.09 |    1.10 |    0.07 |
| Requests the post of a user                     |       0.4 |       0.3 |       0.3 |       0.4 |       0.4 |       0.4 |       0.4 |       0.3 |       0.3 |        0.3 |    0.35 |    0.35 |    0.05 |
| Request the distribution of tags used by a user |       2.8 |       2.5 |       2.5 |       2.5 |       2.6 |       2.9 |       2.8 |       2.9 |       3.1 |        3.1 |    2.77 |    2.80 |    0.22 |

> **Note:** "—" indicates a TIMEOUT (180 s).

## Normal Processing

| Query                                           | Run 1 (s) | Run 2 (s) | Run 3 (s) | Run 4 (s) | Run 5 (s) | Run 6 (s) | Run 7 (s) | Run 8 (s) | Run 9 (s) | Run 10 (s) | Avg (s) | Med (s) | Std (s) |
| ----------------------------------------------- | --------: | --------: | --------: | --------: | --------: | --------: | --------: | --------: | --------: | ---------: | ------: | ------: | ------: |
| Request the messages of liked users             |         — |         — |         — |         — |         — |         — |         — |         — |         — |          — |       — |       — |       — |
| Request the forums a user posted                |         — |         — |         — |         — |         — |         — |         — |         — |         — |          — |       — |       — |       — |
| Request the information of a user               |       1.0 |       1.0 |       1.1 |       1.1 |       1.0 |       1.1 |       1.1 |       1.1 |       1.0 |        1.0 |    1.05 |    1.05 |    0.05 |
| Requests the post of a user                     |       0.2 |       0.2 |       0.2 |       0.2 |       0.2 |       0.2 |       0.2 |       0.2 |       0.2 |        0.2 |    0.20 |    0.20 |    0.00 |
| Request the distribution of tags used by a user |       1.9 |       1.8 |       1.7 |       1.9 |       2.2 |       2.2 |       2.6 |       2.2 |       2.4 |        2.2 |    2.11 |    2.20 |    0.27 |

> **Note:** "—" indicates a TIMEOUT (180 s).

## Analysis

Comparing queries that completed under both methods (excluding timeouts):

| Query                                           | Alignment Avg (s) | Normal Avg (s) | Difference (s) |
| ----------------------------------------------- | -----------------: | -------------: | --------------: |
| Request the information of a user               |               1.09 |           1.05 |           +0.04 |
| Requests the post of a user                     |               0.35 |           0.20 |           +0.15 |
| Request the distribution of tags used by a user |               2.77 |           2.11 |           +0.66 |

**Overall:** The online schema alignment method introduces an average overhead of **0.28 &plusmn; 0.31 s** compared to normal processing.
