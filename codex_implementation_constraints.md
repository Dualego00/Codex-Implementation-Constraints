$ponytail  # <-- Invoke the ponytail skill here

# Coding task

- Brief title of Your coding task
- coding only inside /path

# Demand

1. I want xxx
2. Edit xxx

## Additional implementation constraints

1. Remember this is research code, not production code. Precision and readability are crucial, so there's no need to add various 'tighten' and 'safe' operations.  
2. Keep the codebase concise and modular: aim for fewer than 300 lines per Python file; organize code around clear responsibilities with high cohesion and low coupling; avoid unnecessary abstractions and never split files solely to meet the line-count target.
3. Prohibit defensive programming:
   1. Strictly prohibit defensive programming outside the `tests/` directory .  
   2. Explicitly state outside the `tests/` directory : No try...except... No raise xxx error. No fallback. No assert.  
   3. Eliminate `None` validations on variables guaranteed to be initialized upstream or whose execution paths are already deterministic.
   4. Do not rely on defensive programming for correctness. Directly and cleanly edit the code as you consider correct, then run tests. If errors occur, edit and test again.
4. Feature preservation:
   1. You cannot delete any hyperparameters in config files unless I explicitly state to remove them.
   2. You cannot add any hyperparameters in config files unless I explicitly state to add them.
   3. You cannot delete any code realizing the feature defined by hyperparameters in config files unless I explicitly state to  remove it.
   4. Whenever you use the ponytail rule to modify the existing code, double-check that the change won't break any existing features.
5. Do not hardcode alpha or beta version paths in hyperparameters; make paths relative to the project directory.   
5. Smoke test:
   1. The smoke tests are located under `tests`. You may place multiple test files there. 
   2. Ensure that passing the corresponding smoke test verifies that the main pipeline runs normally. Use the real dataset at a minimal scale (e.g., 3 data points each for training, generation/inference, and evaluation). I will not manually inspect the `tests` folder.
   3. If users run the main pipeline or do not select any smoke test (the default), no files in the `tests` folder will be executed or called.
   4. Ensure the smoke test file in the `tests/` directory is compatible with running experiments across different hyperparameters. Values should not be hard-coded; the smoke test must remain adaptive to varying hyperparameters.
   5. Automatically delete the smoke test experiment directory in `experiments/` after smoke test succeeds.
6. Readability stems from the code itself, rather than comments. Adding comments and README.md is strictly prohibited.
7. Avoid unnecessary twists in your words. Answer concisely and directly.

**Reinforcement:** Remember this is research code, not production code. Precision and **readability** are crucial, so there's no need to add various 'tighten' and 'safe' operations.  