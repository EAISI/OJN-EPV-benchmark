# OJN-EPV Benchmark

This repository hosts the **OJN-EPV benchmark**, the first publicly available benchmark specifically designed for evaluating the pass component of Expected Possession Value (EPV) models in football. The benchmark focuses solely on pass scenarios and provides pairs of game states with human-assigned relative EPV judgments to assess the quality and accuracy of EPV models in evaluating pass value.

## Benchmark Overview

The OJN-EPV benchmark consists of two types of pass-specific game state pairs:

1.  **Modified pass states**: Real game states with altered aspects relevant to passing (e.g., player positions, player velocities) to evaluate a model's sensitivity to changes in pass scenarios.
2.  **Comparative pass states**: Pairs of similar real game states with subtle differences in pass-related features to assess a model's ability to discern which state offers a higher EPV for the pass.

The benchmark focuses on relative EPV differences rather than absolute EPVs, as relative judgments are generally less debatable and provide a clearer measure of a model's ability to assess pass quality.

## Data Source

The benchmark was created using pass-specific data from various matches in our database.

**Important**: The data for the benchmark are from matches that were not in either train, validation, or test sets to ensure an unbiased evaluation.

The data includes a tracking snapshot for player and ball positions, as well as player velocities.

## Benchmark Creation Process

1.  **Pass-specific state selection**: Game states involving pass events were selected from our database, ensuring they were not included in the training, validation, or test sets used for model development.
2.  **Pass state modification**: Modified pass states were created by realistically altering aspects of real game states relevant to passing, such as player positions and player velocities.
3.  **Comparative pass state selection**: Pairs of similar game states with subtle differences in pass-related features were selected.
4.  **Expert input**: Football experts with expertise in pass evaluation provided relative EPV assignments for each pass-specific game state pair.

## Benchmark Usage

To evaluate the pass component of an EPV model using the OJN-EPV benchmark:

1.  Obtain the pass-specific game state pairs and their corresponding relative EPV assignments from the repository.
2.  Compute the EPV for each game state in a pair using your EPV model, focusing on the pass evaluation component.
3.  Compare the model's predicted relative EPV with the expert-assigned relative EPV for the pass.
4.  Aggregate the results across all game state pairs to assess the model's overall performance in evaluating pass value.

## Contribution and Feedback

We invite the research community to:

- Provide feedback on the pass-specific benchmark.
- Suggest new pass-related game state pairs.
- Contribute to improving the benchmark's relevance for pass evaluation.

By working together, we can enhance the OJN-EPV benchmark and support the development of better EPV models for analyzing and evaluating passes in football.
