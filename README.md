# PySchedulerForDoctors 自動化產生醫師班表，解救總醫師

# Overview
📅 This program is designed to automate the scheduling of doctors in your department based on various constraints. It utilizes linear programming and integrates with Google Sheets for easy manipulation of scheduling parameters by end-users without any coding knowledge.

![Doctor Schedule](https://raw.githubusercontent.com/nps798/PySchedulerForDoctors/main/demo/demoImage2.png)

## Program Overview 

How end-user without coding skill tell the program how to make an appropriate schedule

This program is designed to automate the scheduling of doctors in your department based on various constraints. It utilizes linear programming and integrates with Google Sheets for easy manipulation of scheduling parameters by end-users without any coding knowledge.

### Sheet 1: Tasks and Personnel 業務與人員

This sheet lists the different tasks or businesses that need to be scheduled and the personnel available to perform each task.

### Sheet 2: Daily Task Schedule 每日業務

This sheet defines the daily schedule for each task. Users need to mark whether a task requires personnel by entering the Chinese character "必" (required) or "可" (optional) in the corresponding cell.

### Sheet 3: Recurring Activities (ex. attending's weekly out-patient time) 固定活動 (ex.門診)

This sheet defines recurring activities that happen on a weekly basis, such as a doctor's regular outpatient clinic. These activities are fixed and do not require scheduling. They serve as constraints when scheduling other tasks to ensure doctors' fixed activities are not overlapped.

### Sheet 4: Preventing same person for two conficting tasks

In this sheet, you define which two tasks cannot be assigned to the same person simultaneously. This prevents the linear programming algorithm from scheduling the same person for two conflicting tasks.

### Sheet 5: Off-day Constraints

This sheet defines constraints where certain tasks should not be scheduled for a doctor on the following day. For example, if Doctor A is scheduled for a particular task today, Doctor B should not be scheduled for a specific task tomorrow.

### Sheet 6: Desired Assigned Tasks Count (of a person)

In this sheet, you specify the desired number of times each doctor should be assigned to a specific task within the given month. This helps achieve a balanced distribution of tasks among doctors and prevents workload imbalances.

### Sheet 7: Negative Constraints

This sheet accounts for pre-scheduled off-days for doctors due to personal reasons or other commitments. It ensures that these doctors are not scheduled for any duties on those specific dates.

### Sheet 8: Positive Constraints

This sheet captures special scheduling requests where a doctor has already made arrangements with external units for specific dates. This information helps the program prioritize and assign the doctor to the requested tasks.

## How to Use

1. Create a Google Sheets document with the above-mentioned sheet structure.
2. Populate the sheets with the necessary information as explained above.
3. Run the Python program, providing the appropriate Google Sheets credentials.
4. The program will retrieve the data from the Google Sheets document and generate the optimized doctor schedule based on the defined constraints.
5. Review and distribute the generated schedule to doctors and relevant stakeholders.

Please note that this program relies on linear programming techniques to optimize the scheduling process. Therefore, it is recommended to review the generated schedule to ensure it aligns with any specific requirements or adjustments that may be necessary.

For detailed instructions on setting up the Google Sheets document and running the program, please refer to the accompanying documentation in the `docs/` directory.

## Dependencies

The program requires the following Python dependencies. You can install them using `pip`:

- requests
- pandas
- pulp
- numpy
- tkinter
- xlsxwriter

To install the dependencies, run the following command:


## Dependencies

The program requires the following Python dependencies. You can install them using `pip`:

- requests
- pandas
- pulp
- numpy
- tkinter
- xlsxwriter

To install the dependencies, run the following command:
