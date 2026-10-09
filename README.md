# ARCHIVE 2719

Case: LTN-002
Classification: RESTRICTED

The deployment system produced several conflicting snapshots.

Some evidence was recovered from a separate incident branch.
Not every recovered snapshot belongs to the official release line.

## Objective

Find the one valid build snapshot in the history of `main`.

A snapshot is valid only when ALL conditions are satisfied:

1. status is PASS.
2. tests_failed equals 0.
3. tests_passed equals 42.
4. The sum of the decimal digits in build_id is prime.

Evaluate all fields as they existed in the same commit.
Do not combine values from different snapshots.

Only commits reachable from `main` count.
A snapshot existing exclusively on another branch is not
part of the official release history.

The valid snapshot contains an artifact identifier.

Use the artifact identifier exactly as recorded, in lowercase,
to form the next repository name:

lantern-<artifact>

Do not trust the latest snapshot merely because it is latest.
