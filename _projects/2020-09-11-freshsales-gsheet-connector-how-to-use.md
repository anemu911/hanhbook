---
title: 'Freshsales GSheet Connector How to use'
subtitle: ''
date: 2020-09-11
description: ''
featured_image: '/images/projects/freshsales-gsheet-connector.png'
group: article
---
### Problem
My job requires me to monitor our website leads performance and sales agents' activities. Although all of these data is coming from Freshsales (our current CRM), I can't use Freshsales interface to do advanced analysis. Freshsales only provides raw data and simple visualisation that doesn't meet my use case. Google Sheet (GSheet) is my best friend here. With this, I face with 2 issues:
1. I can't just keep downloading reports and uploading to GSheet. It's troublesome.
2. For any new report that I need to retrieve, I have to create a new report in Freshsales so that I can download. (And take a mental note to delete it later as I don't want to mess up the report list).

Since there's no online solution that allows me to sync data from Freshsales to GSheet automatically, I decided to create one: [Freshsales Connector](https://gsuite.google.com/marketplace/app/freshsales_connector/180524350522). This add-on will run in GSheet.

### How to generate report
**Step 0:** Access add on
After downloading from GSuite marketplace, you should be able to access the add-on
1. Open a preferred GSheet
2. Click `Add-ons` in navigation
3. You will see `Freshsales Connector`
4. You can either choose `Create report` (to create a new report and update data in GSheet) or `Manage saved reports` to run previously saved reports.

![How to access Freshsales GSheet Connector](/images/projects/fs-how-to-use/fs-navigation.png)

**Step 1:** Key in company name, token and report type

1. Company name here refers to the part of the URL prior to `.freshsales.io`. For example: abc.freshsales.io, then company name is `abc`.
2. Token can be retrieved from API settings in Freshsales. This is the direct link: *https://company_name.freshsales.io/personal-settings/api-settings*. Remember to replace `company_name` with your actual company.
3. Choose report type. In Freshsales, there are quite a number of report types but I choose to sync 3 types: (1) Leads with converted, (2) Deals, and (3) Deals with Contacts. Other report types are not in my current use case so I haven't added them in.

Upon clicking `Retrieve details`, the add-on will try to access Freshsales and generate existing columns and filters. My trick is to let Chrome remember my token so I don't have to find it again the next time I run report.

![How key in names, token in Freshsales GSheet Connector](/images/projects/fs-how-to-use/fs-users.png)

**Step 2:** Search and add columns

They are actually fields in Freshsales. Depending on the reports you choose, fields here refer to those in `Leads` or `Deals`. They will be constructed as columns of your report in GSheet.

Search by typing the field name in Freshsales. By clicking on the field, it will be added to the list of selected columns.

![How to search column in Freshsales GSheet Connector](/images/projects/fs-how-to-use/fs-search-column.png)

The `List of selected columns` box below to refer to what you choose and order of the columns.

![How to see selected columns in Freshsales GSheet Connector](/images/projects/fs-how-to-use/fs-selected-columns.png)

To remove any field, just click on the field again at the box.

Please note that if you don't see any fields in Search box. That is due to either wrong combination of company name and token or no field settings in Freshsales.

**Step 3:** Filters

Now, the columns are added. It's time to add filters.

Mandatory filters: Time frame
You can choose to retrieve results based on created at, closed date or stage updated at with fix time frame (i.e. manually put in start date and end date) or dynamic time frame (e.g. last week, last month). Without this filter, the report is unable to be retrieved.

![How to update time filter in Freshsales GSheet Connector](/images/projects/fs-how-to-use/fs-mandatory-filter.png)

Optional: Filters based on fields
You can optionally add filters based on fields like territory, owners by clicking `Add`. Right now, the fields you can choose are limited to dropdown fields.

Optional: Filter logic type
Once you have more than 1 optional filter, you can change the logic type: `AND/OR` or a combination of both (applicable to 3 filters and above). This is helpful in case you want to retrieve data from 2 territories for example.

![How to update optional filters in Freshsales GSheet Connector](/images/projects/fs-how-to-use/fs-optional-filter.png)

Please note that you can't remove filter one by one but you can reset all filters by clicking `Reset`.

**Step 4:** Get report

Now, all left is to click on `Get report` button to retrieve data from Freshsales. Note that the add on will:

Show report in active tab. Meaning when the system is able to get data from Freshsales and ready to update GSheet, it will determine the active tab at that point. So you might want to wait instead of switching to different tab.

Clear existing data in the active tab, starting from column A to the column that it needs to show. The rest of the data in that sheet still remains.

Once the report is done, you will be notified which sheet is updated.

![How to see report added in Freshsales GSheet Connector](/images/projects/fs-how-to-use/fs-report-added.png)

### How to save report
Once you construct the report by adding columns and filters, you can save report so that next time you come back, the report is already set up and ready to run.

**Step 1:** Create report name

Scroll down to the bottom at `Filters` tab and create a name in `Report Name`.

You have an option to `Append data`, which will tell the system to append data after the last row that has content in the active sheet. This is helpful when for example, you want the system to retrieve leads of yesterday, then append it to previous days' data. If you don't choose `Append data`, it will just replace data in that sheet.

![How to save report in Freshsales GSheet Connector](/images/projects/fs-how-to-use/fs-save-report.png)

**Step 2:** Save report

Click `Save report`.

![How to know report is saved in Freshsales GSheet Connector](/images/projects/fs-how-to-use/fs-save-report-added.png)

**Step 3:** Manage Saved Reports

You can access this by clicking `Add-ons` in navigation, choose `Freshsales` and then `Manage saved reports`. If there are no reports yet, you will see this.

![No saved in Freshsales GSheet Connector](/images/projects/fs-how-to-use/fs-no-saved-report.png)

If there is at least 1, you will see the reports that you save before and those that are saved by people who have access to the documents and have Freshsales installed. If you want to run report, just click on the `play` icon. The report will be shown in the current active tab. If you want to delete it, click on the `trash` icon.

![How to see saved reports in Freshsales GSheet Connector](/images/projects/fs-how-to-use/fs-list-saved-reports.png)

### Others
I actually created a trigger function to help run reports automatically but after testing, I saw a number of edge cases that the triggers do not perform well so I remove them from the code.
