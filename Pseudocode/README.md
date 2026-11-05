# FLOODCONNECT SL – PSEUDOCODE

## 1. MAIN SYSTEM NAVIGATION

BEGIN

    DISPLAY "COMMUNITY FLOOD REPORTING AND RESPONSE MANAGEMENT SYSTEM"

    DISPLAY "SELECT USER CATEGORY"
    DISPLAY "1. RESIDENT"
    DISPLAY "2. ADMINISTRATOR"
    DISPLAY "3. RESPONSE TEAM"

    INPUT userType

    IF userType = 1 THEN
        CALL ResidentModule

    ELSE IF userType = 2 THEN
        CALL AdministratorModule

    ELSE IF userType = 3 THEN
        CALL ResponseTeamModule

    ELSE
        DISPLAY "INVALID USER SELECTION"

    END IF

END


## 2. ADMINISTRATOR LOGIN AND REPORT VERIFICATION

BEGIN AdministratorModule

    DISPLAY "ADMINISTRATOR LOGIN"

    INPUT username
    INPUT password

    IF loginValid = TRUE THEN

        DISPLAY "LOGIN SUCCESSFUL"
        DISPLAY "ACCESS GRANTED"

        DISPLAY "VIEW SUBMITTED FLOOD REPORTS"

        INPUT selectedReport

        DISPLAY selectedReport

        DISPLAY "1. APPROVE REPORT"
        DISPLAY "2. REJECT REPORT"

        INPUT adminDecision

        IF adminDecision = 1 THEN

            SET reportStatus = "Approved"

            DISPLAY "REPORT APPROVED"

            INPUT assignedTeam

            DISPLAY "RESPONSE TEAM ASSIGNED"

        ELSE IF adminDecision = 2 THEN

            SET reportStatus = "Rejected"

            DISPLAY "REPORT REJECTED"
            DISPLAY "REPORT CLOSED"

        ELSE

            DISPLAY "INVALID DECISION"

        END IF

    ELSE

        DISPLAY "INVALID LOGIN DETAILS"
        DISPLAY "ACCESS DENIED"

    END IF

END AdministratorModule


## 3. RESIDENT FLOOD REPORTING

BEGIN ResidentModule

    DISPLAY "RESIDENT FLOOD REPORTING"

    INPUT residentName
    INPUT location
    INPUT incidentCategory
    INPUT description

    SET detailsComplete = FALSE

    WHILE detailsComplete = FALSE DO

        IF residentName IS NOT EMPTY AND
           location IS NOT EMPTY AND
           incidentCategory IS NOT EMPTY AND
           description IS NOT EMPTY THEN

            SET detailsComplete = TRUE

        ELSE

            DISPLAY "SOME DETAILS ARE MISSING"
            DISPLAY "PLEASE ENTER THE REQUIRED INFORMATION"

            INPUT residentName
            INPUT location
            INPUT incidentCategory
            INPUT description

        END IF

    END WHILE

    GENERATE reportID

    SET reportStatus = "Pending"

    SAVE residentName, location, incidentCategory,
         description, reportID, reportStatus

    DISPLAY "REPORT SUBMITTED SUCCESSFULLY"
    DISPLAY "YOUR REPORT ID IS: ", reportID
    DISPLAY "REPORT STATUS: PENDING"

END ResidentModule


## 4. RESPONSE TEAM TASK MANAGEMENT

BEGIN ResponseTeamModule

    DISPLAY "RESPONSE TEAM LOGIN"

    INPUT teamLoginDetails

    DISPLAY "LOGIN SUCCESSFUL"

    DISPLAY "VIEW ASSIGNED TASKS"

    DISPLAY assignedTasks

    INPUT selectedTask

    SET taskStatus = "In Progress"

    DISPLAY "TASK STATUS: IN PROGRESS"

    DISPLAY "CARRY OUT ASSIGNED ACTIVITY"

    SET taskStatus = "Completed"

    SAVE selectedTask, taskStatus

    DISPLAY "TASK COMPLETED SUCCESSFULLY"
    DISPLAY "TASK STATUS: COMPLETED"

END ResponseTeamModule
