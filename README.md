# Getting Started with Masterfile

This interview problem set has 2 items to complete. It shouldn't take more than 30-45 minutes to complete. If any of the instructions are unclear, just leave a comment with your interpretation of the problem and continue to solve from there. Once complete, please create a zip folder containing all files execpt for `node_modules` and email to garrett@masterfile.co with your `Frontend Interview - Your Name` in the subject line.

All components must be functional components. You may handle the state of components any way you see fit. Feel free to add any dependencies you see fit. Don't worry about styling. Please add comments where you see fit to document your thought process for solving these problems.

## Problem #1

For this problem we want to fetch data from the SpaceX graphql endpoint and display it in a table.

Endpoint: https://api.spacex.land/graphql/

Query Parameters:

1. We want the past 10 rocket launches (`launchesPast`)
2. We want the offset of our query to be an input that defaults to 0 (we will use this in a bit)
3. We want the following properties:

- id
- mission_name
- launch_date_local
- site_name (property of launch_site)
- rocket_name (property of rocket)
- launch_success

4. We don't want any extra data

Hint:
the first line in your query should look something like this:
`launchesPast(limit: 10, offset: $offset)`

Desired output:

| Mission Number | Mission Name | Launch Date       | Launch Site | Rocket Name | Successful?    |
| -------------- | ------------ | ----------------- | ----------- | ----------- | -------------- |
| id             | mission_name | launch_date_local | site_name   | rocket_name | launch_success |
| ...            | ...          | ...               | ...         | ...         | ...            |

## Problem #2

We now want to make the data in our table dynamic. To do this we will create a button that when pressed, increments the `offset` variable used in our query in the previous question. This should cause the table element to re-render with the updated data.

Example table before button press:

| Mission Number | Mission Name | Launch Date       | Launch Site | Rocket Name | Successful?    |
| -------------- | ------------ | ----------------- | ----------- | ----------- | -------------- |
| 100            | Mission_100  | launch_date_local | site_name   | rocket_name | launch_success |
| 99             | Mission_99   | launch_date_local | site_name   | rocket_name | launch_success |
| ...            | ...          | ...               | ...         | ...         | ...            |

Example table after one button press:

| Mission Number | Mission Name | Launch Date       | Launch Site | Rocket Name | Successful?    |
| -------------- | ------------ | ----------------- | ----------- | ----------- | -------------- |
| 99             | Mission_99   | launch_date_local | site_name   | rocket_name | launch_success |
| 98             | Mission_98   | launch_date_local | site_name   | rocket_name | launch_success |
| ...            | ...          | ...               | ...         | ...         | ...            |
