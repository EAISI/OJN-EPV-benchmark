# OJN-EPV Benchmark

This repository hosts the **OJN-EPV benchmark**, the first publicly available benchmark specifically designed for evaluating the pass component of Expected Possession Value (EPV) models in football. In its current version, the benchmark focuses on modified pass scenarios and provides pairs of game states with human-assigned relative EPV judgments.

## Current Benchmark Scope

The current version of the OJN-EPV benchmark (located in the `OJN-Pass-EPV-benchmark` folder) focuses on:

- **Modified pass states**: Real game states with altered aspects relevant to passing (e.g., player positions, player velocities) to evaluate a model's sensitivity to changes in pass scenarios.

The benchmark focuses on relative EPV differences rather than absolute EPVs, as relative judgments are generally less debatable and provide a clearer measure of a model's ability to assess pass quality.

## Future Extensions

We plan to expand this benchmark to include:

1. **Additional action types**: Expanding beyond passing to evaluate other on-ball actions like dribbling and shooting.
2. **More complex scenarios**: Including multi-action sequences and strategic decision-making situations.

## Data Source

The benchmark was created using pass-specific data from various matches in our database.

**Important**: The data for the benchmark are from matches that were not in either train, validation, or test sets to ensure an unbiased evaluation. The data includes a tracking snapshot for player and ball positions, as well as player velocities. **All x coordinates range from -52.5 to 52.5, and all y coordinates range from -34 to 34.** The ball is annotated as 0 in both the team and player columns. `playing_direction_event` is `True` when the event took place from left to right, otherwise `False`.

## Benchmark Creation Process

1. **Pass-specific state selection**: Game states involving pass events were selected from our database, ensuring they were not included in the training, validation, or test sets used for model development.
2. **Pass state modification**: Modified pass states were created by realistically altering aspects of real game states relevant to passing, such as player positions and player velocities.
3. **Expert input**: Football experts with expertise in pass evaluation provided relative EPV assignments for each pass-specific game state pair.

## Benchmark Usage

To evaluate the pass component of an EPV model using the current OJN-EPV benchmark:

1. Access the modified pass states in the `OJN-Pass-EPV-benchmark` folder.
2. Compute the EPV for each game state pair using your EPV model.
3. Compare the model's predicted relative EPV with the expert-assigned relative EPV.
4. Aggregate the results to assess the model's performance in evaluating pass value.

## Contribution and Feedback

We invite the research community to:

- Provide feedback on the pass-specific benchmark.
- Suggest new pass-related game state pairs.
- Contribute to improving the benchmark's relevance for pass evaluation.

By working together, we can enhance the OJN-EPV benchmark and support the development of better EPV models for analyzing and evaluating passes in football.
