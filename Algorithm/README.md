# FLOODCONNECT SL – STEP-BY-STEP ALGORITHM

## 1. Main System Navigation

1. Start the system.
2. Display the main menu.
3. Ask the user to select a category.
4. If the user selects Resident, open the Resident Module.
5. If the user selects Administrator, open the Administrator Module.
6. If the user selects Response Team, open the Response Team Module.
7. If the selection is invalid, display an error message.
8. End the session.

## 2. Administrator Login and Report Verification

1. Start the Administrator Module.
2. Request the administrator's username and password.
3. Check the login details.
4. If the details are invalid, display Access Denied.
5. If the details are valid, grant access.
6. Display submitted flood reports.
7. Allow the administrator to select a report.
8. Review the report details.
9. If the report is approved, update its status and assign a response team.
10. If the report is rejected, update its status to Rejected and close it.
11. End the module.

## 3. Resident Flood Reporting

1. Start the Resident Module.
2. Request the resident's name.
3. Request the incident location.
4. Request the flood incident category.
5. Request a description of the incident.
6. Check whether all required details are provided.
7. If details are missing, request the information again.
8. If all details are complete, generate a report ID.
9. Save the report with Pending status.
10. Display a submission confirmation and report ID.
11. End the module.

## 4. Response Team Task Management

1. Start the Response Team Module.
2. Request team login details.
3. Display assigned tasks.
4. Allow the team to select a task.
5. Update the task status to In Progress.
6. Carry out the assigned activity.
7. Update the task status to Completed.
8. Save the updated task information.
9. Display a completion message.
10. End the module.

