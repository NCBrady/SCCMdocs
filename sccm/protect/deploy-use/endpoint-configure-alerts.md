---
title: "Configure Endpoint Protection alerts | Microsoft Docs"
description: "Learn how to configure Endpoint Protection alerts in Microsoft System Center 2012 Configuration Manager."
ms.custom: na
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
  - configmgr-other
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: f504de3e-4caf-455c-80d7-a63f13f4c5d9
caps.latest.revision: 21
author: NathBarnms.author: nathbarnmanager: angrobe

---

#  Configure Alerts for Endpoint Protection in Configuration Manager*Applies to: System Center Configuration Manager (Current Branch)*
 You can configure Endpoint Protection alerts in Microsoft System Center Configuration Manager to notify administrative users when specific events, such as a malware infection, occur in your hierarchy. Notifications display in the Endpoint Protection dashboard in the Configuration Manager console in the **Alerts** node of the **Monitoring** workspace, or can be emailed to specified users.

 Use the following steps and the supplemental procedures in this topic to configure alerts for Endpoint Protection in Configuration Manager.

> [!IMPORTANT]
>  You must have the **Enforce Security** permission for collections to configure Endpoint Protection alerts.

## Steps to Configure Alerts for Endpoint Protection in Configuration Manager

1.  In the Configuration Manager console, click **Assets and Compliance**.

2.  In the **Assets and Compliance** workspace, click **Device Collections**.

3.  In the **Device Collections** list, select the collection for which you want to configure alerts, and then on the **Home** tab, in the **Properties** group, click **Properties**.

    > [!NOTE]
    >  You cannot configure alerts for user collections.

4.  On the **Alerts** tab of the *<Collection Name\>***Properties** dialog box, select **View this collection in the Endpoint Protection dashboard** if you want to view details about antimalware operations for this collection in the **Monitoring** workspace of the Configuration Manager console.

    > [!NOTE]
    >  This option is unavailable for the **All Systems** collection.

5.  On the **Alerts** tab of the *<Collection Name\>***Properties** dialog box, click **Add**.

6.  In the **Add New Collection Alerts** dialog box, in the **Generate an alert when these conditions apply** section, select the alerts that you want Configuration Manager to generate when the specified Endpoint Protection events occur, and then click **OK**.

7.  In the  **Conditions** list of the **Alerts** tab, select each Endpoint Protection alert, and then specify the following information:

    -   **Alert Name** - Accept the default name or enter a new name for the alert.

    -   **Alert Severity** - In the list, select the alert level to display in the Configuration Manager console.

8.  Depending on the alert that you select, specify the following additional information:

    -   **Malware detection** - This alert is generated if malware is detected on any computer in the collection that you monitor. The **Malware detection threshold** specifies the malware detection levels at which this alert is generated:

        -   **High - All detections** - The alert is generated when there are one or more computers in the specified collection on which any malware is detected, regardless of what action the Endpoint Protection client takes.

        -   **Medium - Detected, pending action** - The alert is generated when there is one or more computers in the specified collection on which malware is detected, and you must manually remove the malware.

        -   **Low - Detected, still active** - The alert is generated when there are one or more computers in the specified collection on which malware is detected and is still active.

    -   **Malware outbreak** - This alert is generated if specified malware is detected on a specified percentage of computers in the collection that you monitor.

        -   **Percentage of computers with malware detected** - The alert is generated when the percentage of computers with malware that is detected in the collection exceeds the percentage that you specify. Specify a percentage from **1** through **99**.

            > [!NOTE]
            >  The percentage value is based on the number of computers in the collection, but excludes computers that do not have a Configuration Manager client installed. It includes computers that do not yet have the Endpoint Protection client installed.

    -   **Repeated malware detection** - This alert is generated if specific malware is detected more than a specified number of times over a specified number of hours on the computers in the collection that you monitor. Specify the following information to configure this alert:

        -   **Number of times malware has been detected:** - The alert is generated when the same malware is detected on computers in the collection more than the specified number of times. Specify a number from **2** through **32**.

        -   **Interval for detection (hours):** Specify the detection interval (in hours) in which the number of malware detections must occur. Specify a number from **1** through **168**.

    -   **Multiple malware detection** - This alert is generated if more than a specified number of malware types are detected over a specified number of hours on computers in the collection that you monitor. Specify the following information to configure this alert:

        -   **Number of malware types detected:** The alert is generated when the specified number of different malware types are detected on computers in the collection. Specify a number from **2** through **32**.

        -   **Interval for detection (hours):** Specify the detection interval, in hours, in which the number of malware detections must occur. Specify a number from **1** through **168**.

9. Click **OK** to close the *<Collection Name\>***Properties** dialog box.  

> [!div class="button"]
[Next step >](endpoint-definition-updates.md)

> [!div class="button"]
[Back >](endpoint-protection-site-role.md)
