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

## Files

The benchmark holds 50 game state pairs, one folder per pair (`OJN-Pass-EPV-benchmark/modification_1` to
`modification_50`). Each folder contains:

- `game_state_1.csv` and `game_state_2.csv`: one tracking snapshot each, with one row per player (22) plus one row
  for the ball. Columns: `team` (1 or 2; 0 for the ball), `player` (player id; 0 for the ball), `pos_x`, `pos_y`,
  `pos_z`, `smooth_x_speed`, `smooth_y_speed`, `event_player` (id of the player making the pass) and
  `playing_direction_event`.
- `modification.csv`: one column, `higher_state_id`, giving the state (1 or 2) that the experts judged to have the
  higher pass EPV.

## Benchmark Creation Process

1. **Pass-specific state selection**: Game states involving pass events were selected from our database, ensuring they were not included in the training, validation, or test sets used for model development.
2. **Pass state modification**: Modified pass states were created by realistically altering aspects of real game states relevant to passing, such as player positions and player velocities.
3. **Expert input**: Football experts with expertise in pass evaluation provided relative EPV assignments for each pass-specific game state pair.

## Benchmark Usage

To evaluate the pass component of an EPV model using the current OJN-EPV benchmark:

1. Access the modified pass states in the `OJN-Pass-EPV-benchmark` folder.
2. Compute the EPV for each game state pair using your EPV model.
3. Compare the model's predicted relative EPV with the expert-assigned relative EPV (`higher_state_id` in
   `modification.csv`).
4. Aggregate the results to assess the model's performance in evaluating pass value.

## Contribution and Feedback

We invite the research community to:

- Provide feedback on the pass-specific benchmark.
- Suggest new pass-related game state pairs.
- Contribute to improving the benchmark's relevance for pass evaluation.

By working together, we can enhance the OJN-EPV benchmark and support the development of better EPV models for analyzing and evaluating passes in football.

## License

The benchmark is licensed under CC BY-SA 4.0; see [LICENSE.md](LICENSE.md).
