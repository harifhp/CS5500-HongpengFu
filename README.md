Gilded Rose Refactoring Kata (CS5500)

## Overview

This project is a refactoring exercise for the Gilded Rose Kata, focused on improving code structure using design patterns and Test-Driven Development (TDD) principles.
The goal was to make the legacy code more modular, readable, maintainable, and extensible — without changing the Item class or the items attribute of the GildedRose class.

## Testing Setup
Prerequisites

Python 3.11+

approvaltests and texttest installed

Virtual environment activated

Run Approval Tests
python tests/test_gilded_rose_approvals.py


All 30-day tests pass ✅ indicating behavior has been preserved during refactoring.

## Refactoring Strategy
## Design Pattern Used

This refactor applies the Strategy Pattern combined with a Registry/Factory:

Each item type (e.g., normal item, Aged Brie, Backstage pass, Sulfuras, Conjured) has its own strategy class implementing the update rule.

A central registry maps item names to their corresponding strategies.

GildedRose.update_quality() delegates logic to the correct strategy at runtime.

## Key Benefits

No changes to Item or items attribute (requirement satisfied).

Cleaner and more modular code.

Easier to add new item types in the future.

All legacy behavior preserved through Golden Master testing.

## Code Structure
python/
│
├─ gilded_rose.py                 # Refactored core using Strategy + Registry
├─ texttest_fixture.py
└─ tests/
   ├─ test_gilded_rose_approvals.py
   └─ approved_files/
      └─ test_gilded_rose_approvals.test_gilded_rose_approvals.approved.txt

## Test-Driven Development Workflow

Establish Golden Master: run text tests and save 30-day output.

Refactor in small steps: modify one part, run tests, keep them green.

Add strategies incrementally: NormalItem → AgedBrie → Backstage → Sulfuras → Conjured.

Verify after each step: python tests/test_gilded_rose_approvals.py

✅ All tests passed after refactor.

## How to Run
# Run for 2 days
python texttest_fixture.py
<img width="1316" height="600" alt="image" src="https://github.com/user-attachments/assets/914bdb81-af46-49f5-b002-fb7345563521" />

# Run for 10 days
python texttest_fixture.py 10
<img width="819" height="959" alt="image" src="https://github.com/user-attachments/assets/e38c3edc-2a90-4770-bf57-e8ea40cc26ef" />
<img width="800" height="960" alt="image" src="https://github.com/user-attachments/assets/9654c962-1fd6-447a-9ef6-9acbcc6dafb0" />

# Run Approval Tests (30 days)
python tests/test_gilded_rose_approvals.py
<img width="1444" height="88" alt="image" src="https://github.com/user-attachments/assets/f91103bf-2683-4b9f-9be0-048bd735fe35" />
