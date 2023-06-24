# Modified Gale Shapley Algorithm for Job-CV Matching

This notebook contains an implementation of the Modified Gale Shapley Algorithm for matching jobs to CVs based on preferences. The algorithm aims to find stable job-CV engagements by considering the preferences of both parties.

For your reading, please visit my blog at: https://medium.com/@kirudang/job-resume-matching-part-2-2-matching-candidates-and-vacancies-using-the-modified-37e39c3bf0a

## Algorithm Overview

The Modified Gale Shapley Algorithm works as follows:

1. Create dummy jobs: If there are fewer jobs than CVs, dummy jobs are generated to balance the data.

2. Initialize participants: All jobs are initially considered free and unchosen.

3. Iterate until all jobs are engaged:
   - Select a free job from the set of free jobs.
   - Retrieve the preference list of the current job and filter out unavailable CVs.
   - Iterate through the job's preference list:
     - If a real CV is available and there are available slots for the job, tentatively engage the job with the CV.
     - If a dummy CV is available, tentatively engage the job with the dummy CV.
     - If the job's preference is not available, continue searching for a suitable CV.

4. Remove dummy job engagements: Filter out dummy job engagements from the final results.

5. Return the final job-CV engagements.

## Code Usage

The code provided in the notebook demonstrates the usage of the Modified Gale Shapley Algorithm for job-CV matching. It includes a function `gale_shapley_matching` that takes the following parameters:

- `jobs`: A list of job identifiers or names.
- `cvs`: A list of CV identifiers or names.
- `job_preferences`: A dictionary representing the preference list of each job, where the keys are job identifiers and the values are lists of CV preferences.
- `cv_preferences`: A dictionary representing the preference list of each CV, where the keys are CV identifiers and the values are lists of job preferences.
- `k`: The number of candidates that each job can select.

The function returns a dictionary of job-CV engagements.

To run the code with your specific data, you can modify the `jobs`, `cvs`, `job_preferences`, `cv_preferences`, and `k` variables accordingly. Then execute the code and print the resulting job-CV engagements.

## Example

The notebook includes an example scenario with sample data to demonstrate the usage of the algorithm. The example data includes a list of jobs, a list of CVs, and their respective preference lists. By running the code with the example data, you can see the job-CV engagements that the algorithm produces.

## License

This code is provided under the [MIT License](https://opensource.org/licenses/MIT). Feel free to use and modify it for your needs.
