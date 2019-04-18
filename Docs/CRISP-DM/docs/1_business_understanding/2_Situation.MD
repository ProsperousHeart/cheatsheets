<a href='https://www.learntocodeonline.com/'>![Learn To Code Online By Clicking Here](../../../../Images/learn-to-code-online.png?raw=true "Learn To Code Online")</a>

# Situation

- [Inventory Of Resources](#Inventory-Of-Resources)
- [Requirements, Assumptions, & Constraints](#Requirements,-Assumptions,-&-Constraints)
- [Risks & Contingencies](#Risks-&-Contingencies)
- [Terminology](#Terminology)
- [Costs & Benefits](#Costs-&-Benefits)

## Inventory Of Resources

### People Resources

This section will provide information on the people involved in the project, their focus of effort, and how to get in contact with them.

#### Executive Leadership

| Name | Email | Phone |
| --- | :---: | :---: |
| NA | NA | NA |

#### Current Project Team

| Name | Email | Phone | Project Role | Availability<br>hr/week | Location | Notes |
| --- | :---: | :---: | :---: | :---: | :---: | --- |
| Kassandra Keeton | [LinkedIn](https://linkedin.com/in/kkeeton/) | Python Mentor, Data Science Ambassador | Lead Developer | Flexible | TX, USA | TBD |

#### Programming Resources

| Name | Email | Phone | Project Role | Availability<br>hr/week | Location | Notes |
| --- | :---: | :---: | :---: | :---: | :---: | --- |
| Kassandra Keeton | [LinkedIn](https://linkedin.com/in/kkeeton/) | Python Mentor, Data Science Ambassador | Lead Developer | Flexible | TX, USA | TBD |

#### Prior Project Team

| Name | CEC | Cisco Role | Project Role | Availability<br>hr/week | Location | Notes |
| --- | :---: | :---: | :---: | :---: | :---: | --- |
| TBD |  |  |  |  |  | |

### Data Resources

| Name | Email | Phone | Project Role | Availability<br>hr/week | Location | Notes |
| --- | :---: | :---: | :---: | :---: | :---: | --- |
| Kassandra Keeton | [LinkedIn](https://linkedin.com/in/kkeeton/) | Python Mentor, Data Science Ambassador | Lead Developer | Flexible | TX, USA | TBD |

More information can be found in the [Data Understanding](../2_data_understanding/README.MD) section of this CRISP-DM documentation and the [datasets](../../datasets) subfolder of the git repo.

# Source #1

TBD

## Requirements, Assumptions, & Constraints

TBD

### Stakeholder Commitments

- TBD

### Data Dependencies

Required data includes but is not limited to:
- TBD

### Deployment

TBD

## Risks & Contingencies

Be positive and realistic.
It is better to be proactive than reactive.
If you must be reactive, it's better to be prepared than unprepared.

1. Access to data may take longer than estimated.

    - Reasons
        - includes historical and future data
        - security and privacy consideration may be source of delay
        - unclear procedures
        - may require new schema or API to be created
        - maintenance and planning windows may be source of delay
   
    - Mitigation
        - What may need to be done in order to accomplish your goals? Training? Additional personnel?
        - Continue to do what's possible while still growing
        - have personnel trained to support the needs

3. Data may be more difficult to process than expected

    - Reasons
        - unstructured or semi-structured data that requires specialized techniques
        - APIs not yet created
        - lower than expected data quality
        
    - Mitigation
        - proceed in parallel with utilizing current structured data while developing required techniques
        - assess data quality ASAP to identify and implement necessary cleansing techniques

4. Access to personnel assistance (SMEs) may be more difficult than expected

    - Reasons
        - uncertain who to contact (or no longer available)
        - people are busy
        - SMEs can have a negative incentive to assist
        
    - Mitigation
        - get buy-in and commitment from SME
        - schedule regular engagement touch-base meetings (think Agile)
        - (if possible) coach on possible growth opportunities

5. Access to current metrics, rule/methodology definitions, and other business understanding information may take longer than expected.

    - Reasons
        - may not be readily available
        - change in business plan
        
    - Mitigation
        - develop high-touch relationship through regular touch-base meetings
        - track dependencies to raise visibility of progress blockers
        - have a central repository to record business understanding knowledge, avoid loss, and allow new team members to be on-boarded easier
        - if metrics do not currently exist or are needed, retrofit metrics to curent operations in parallel with new engagement work

6. Available data may not yield as much actionable insight as expected.

    - Reasons
        - wrong data sources
        - no APIs available to get data
        
    - Mitigation
        - New data from other sources may be needed.
        - Aggressively pursue initial prototype modeling to see if available data is compatible with goals
        - Research industry appraoches to the same or similar issues to see what kinds of data are typically or innovatively used


7. Time to develop models may take longer than estimated.

    - Reasons
        - range of potential techniques is large
        - model development is typically iterative
        
    - Mitigation
        - Aggressively pursue initial prototype modeling to see if available data is compatible with goals
        - Research industry appraoches to the same or similar issues to see what kinds of data are typically or innovatively used
        - Let client make an informed decision of when model performance is "good enough" in regular high-touch engagement meetings

8. Time to deply may take longer than estimated.

    - Reasons
        - resources may take longer to deliver than expected
        - systems integration and deployment may require revisements
        
    - Mitigation
        - Try to deploy over course of project so no large transition at the end
        - Prepare detailed requirements and design documentation throughout course of project vs at the end so information is not lost and can be handed to someone else for maintenance
        
9. Cost to deploy may be higher than estimated

    - Reasons
        - specific hardware/software requirements of the operationalized solution may not be known yet
    - Mitigation
        - develop familiarity with range of services/hardware costs available
        - develop famliarity with range of relevant commercial software offerings and their cost
        - use knowledge gained in early portion of project to rapidly clarify range of deployment options and costs to allow client to make an informed decision

10. Information gained at any stage of development may drive changes to the requirements/goals, but this may occur more than expected.

    - Reasons
    - Mitigation
        - high-touch engagement with regular touch base meetings with client
        - frequently share results with client & stakeholders so they:
            - can see they're getting what they really want
            - can make informed decisions about cost/time/functionality tradeoffs
        - spend extra effort on high quality business problem statement & associated requirements/goals at the beginning of project
        - ensure all affected stakeholders are informed & consulted at the beginning of the project
        - aggressively drive to an initial modeling prototype so major changes can be identified as early as possible

11. Business conditions or external changes may drives changes to requirements/goals ir execution/implentation of strategy

    - Reasons
        - difficult to predict the future
    - Mitigation
        - high-touch engagement with regular touch base meetings involving the client
        - align business goals with driving the engagement of the company's strategic initiatives at as high level as possible
        - keep informed of hte ever-changing technology landscape

## Terminology

This section will lay out information on :
- acronymns
- projects
- teams
- data sources
- applications in service
- business terms
- metrics
- technology terms
- compliance terms

### General

| Term | Definition | Extra |
| :---: | :---: | :---: |
| CI | Continuous Improvement | |
| CRISP-DM | Cross Industry Standard Process for Data Mining | Industry standards for data analytic practitioners |
| POC | Point Of Contact | |

### Project Specific

| Term | Definition | Extra |
| :---: | :---: | :---: |
| Lifecycle Lead | Designated person who is responsible for the tactical decisions associated with a service | |
| Service Offering | A defined kind of service that is supported by a particular team | Has a Service Owner |
| Service Owner | Designated contact for a Service Offering | Typically from the business unit associate with the Service Offering |


## Costs & Benefits

**Costs:**
- engagement cost
- solution deployment cost
- tools cost
- (often) differing inital and reoccurring cost

**Benefits:**
- increased revenue
- decreased operating costs
- improved customer satisfaction, retention
- process improvements 

### Estimated Costs - Developing The Solution

Is there a charge? Expected amount of time spent? Software or infrastructure needed?

### Estimated Costs - Deploying/Operationalizing the Solution

Where is it planned to be hosted/stored? Is there any maintenance requirements? DB server requirements?

### Estimated Benefits

- reduced costs and higher client satisfaction due to _ as a result of _
- reduced costs and higher client satisfaction due to better allocation of personnel to support services