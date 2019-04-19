<a href='https://www.learntocodeonline.com/'>![Learn To Code Online By Clicking Here](../../../../Images/learn-to-code-online.png?raw=true "Learn To Code Online")</a>

# PROJECTNAME - Project Plan

- [Introduction](#Introduction)
- [Business Problem](#Business-Problem)
- [Analytics Strategy](#Analytics-Strategy)
- [Project Plan](#Project-Plan)
- [Assessment of Tools and Techniques](#Assessment-of-Tools-and-Techniques)

# Introduction

Within this phase of CRISP-DM you will outline your project plan.

Within your project plan, you will outline:
- deliverables, milestones, phases
- resources, dependencies
- review and commit gates
- data security, privacy, governance

You will also provide estimate of schedules:
- data acquisition and preparation typically take the most time
- it is reasonable for further-out dates to have higher uncertainty
- distinguish beterr estimates and committed dates

# Business Problem

TBD

# Analytics Strategy

TBD

# Project Plan

- engagement is organized around [CRISP-DM](../../../README.MD#Table-Of-Contents)
- project documentation and source code is tracked in (whatever reop you are storing it in)
- work activities are tracked in Github projects with the Github repository

## Agile Approach

Our plan is to use an Agile development mehodology, where we proceed on a high-touch, high-relationship journey with transparency, incremental results delivery, and opportunity to adjust based on results and new insights.

Through the CRISP-DM data science lifecycle, we will:
- meet with stakeholder POC every 2 weeks
- report status to the stakeholder POC every week
- meet as a pod at least every week
- deliver on commitments for the week

At pod meetings:
- sync on status of goals from the previous week
- evaluate what new insights mean in terms of goals
- identify blockages or prerequisites for progress
- decide direction for next week
- assign action items and deliverables

This allows for the client to make informed decisions among alternatives at every step.

## Deliverables Overview

Deliverables are aligned with the Data Science Life Cycle. They ahve the following goals/benefits:
- demonstrate progress to the client
- focus and clarify work effort for both analysts and client
- provide opportunity to identify miscommunication
- inform others

The deliverables mainly consist of:
- CRISP-DM documentation
- weekly status reports
- deployed solution
- daily team check ins

The solution is planned to consist of 4 main components:
1. Official upstream databases to which the solution will have read-only access
2. A solution-specific production database to which the solution will have read-write access
3. A solution-specific web application or Tableau dashboard

In keeping with the Agile approach, a minimal-function full-stack version of the solution will be developed initially, which will then be improved incrementally. This is intended to facilitate early feedback & to avoid issues associated with late integration.

## Estimated Timeline

We plan to develop and deploy the solution in 3 phases (or however many is needed for your project).

### Phase 0 - Q3 FY2019

This will be the planning and setup phase.

The following will be identified:
- identification of key personnel (executive leadership, business owner, programmers, etc)
- needs & requirements for this project
- data pipelines and their POCs
- visual design of final project

### Phase 1 - Q3-Q4 FY2019

We plan to start with a single ___. This will be identified with leadership. Later, we will plan to deploy for multiple ___.

In this phase, we intend to develop initial versions of all components:
- infrastructure such as database access credentials, source code control, development environment
- data pipeline to ___ (data sources)
- scheduled job processes to pull data and/or send alerts
- simplified view-only dashboard
- simplified thresholds & workflow for setting alert thresholds

### Phase 2 - Q4 FY2019

We plan to evaluate the performance of the solution and solicit feedback on the overall approach with the initial service owner and other stakehodlers. If results are favorable, we plan to:
- expand a number of additional services and/or regions
- develop more comprehensive versions of all copmonents, particularly to support multiple services
- provide an enhanced dashboard or web applications with 2-way read-write interaction
- more sophisticated thresholds and workflow for setting alert thresholds
- incorporate user feedback

This will be for a small pilot.

### Phase 3 - Q1 FY2020

This phase will be a reiteration of phase 2 with a larger pool of users. If all feedback is postiive, there will simply be maintenance from here out.

### Operationalization

The operationalization plan needs to be confirmed with the client organization and leadership, but the solution is currently planned to run on the __ platform and, if necessary, on a web server.

- all infrastructure will be provided by __
- no __ servers will be used

**Service Level Requirements**

TBD

**On-Call Support**

TBD

**Long Term Maintenance**

TBD

**Future**

Future partnerships between the client and the programming & analytics team will be in the form of future engagements. Each will have their own intake and evaluation process.

# Assessment of Tools and Techniques

We plan to use the ___ platform for both development and deployment. We intend to use this platform for the following tasks:
1. The __ data pipeline that reads from official upstream databases and performs data analytics
