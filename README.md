

# Calculate Total Target

## Description
The `calculateTotalTarget` function calculates the distribution of a total annual target across the months within a specified date range, excluding Fridays. It returns a JSON object detailing the number of working days (excluding Fridays) per month, the monthly targets, and the total target achieved.

## Instructions to Run the Code
1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/repositoryname.git
   cd repositoryname
   ```

2. **Run the Code:**
   You can run the code using Node.js. Make sure you have Node.js installed on your machine.
   ```bash
   node index.js
   ```

## Explanation of the Function
The function `calculateTotalTarget` takes three parameters:
- `startDate`: The starting date of the range (format: YYYY-MM-DD).
- `endDate`: The ending date of the range (format: YYYY-MM-DD).
- `totalAnnualTarget`: The total target for the year.

### How It Works
1. It initializes an array `daysExcludingFridays` to count the number of working days for each month (12 months).
2. It iterates through each date in the specified range:
   - If the day is not Friday (`getDay() !== 5`), it increments the count for that month.
3. It calculates the `monthlyTarget` by dividing the `totalAnnualTarget` by 12.
4. It creates an array of `monthlyTargets`, assigning the monthly target to months that have working days.
5. It sums the monthly targets to confirm the total matches the annual target.
6. Finally, it returns a formatted JSON object containing the results.

## Example of Usage
Here is an example of how to use the function:

```javascript
console.log(calculateTotalTarget('2024-01-01', '2024-03-31', 5220));
```

### Expected Output
```json
{
  "daysWorkedExcludingFridays": [22, 20, 21],
  "monthlyTargets": [435, 435, 435],
  "totalTarget": 1305
}
```

## Assumptions and Limitations
- The function assumes that the input dates are valid and in the correct format (YYYY-MM-DD).
- It only excludes Fridays from the working days count; other holidays are not considered.
- The total annual target is evenly distributed across the months, which may not reflect actual working conditions or target achievement nuances.
- This function does not account for varying numbers of workdays per month due to holidays other than Fridays.

