---
type: contact
category:
cycle: 30
institution:
department:
role:
email:
birthday:
connections: []
notes: ""
aliases: []
tags: []
---
<!-- cycle: days between desired interactions (7=weekly, 14=biweekly, 30=monthly, 60=bimonthly, 120=semiannual, 365=annual) -->
<!-- notes: key things to remember — research interests, personal details, conversation threads -->
<!-- connections: list of [[wikilinks]] to related contact notes -->

## Interactions
```base
filters:
  and:
    - or:
      - formula.is_meeting
      - formula.is_daily_interaction
views:
  - type: table
    name: Interactions with this contact
    sort:
      - property: formula.interaction_date
        direction: DESC
    columns:
      - file.name
      - formula.interaction_date
      - formula.interaction_type
formulas:
  contact_name: this.file.name
  is_meeting: |
    type && type.toString().lower().contains("meeting")
    && attendees && attendees.toString().contains("[[" + formula.contact_name + "]]")
  is_daily_interaction: |
    interactions && interactions.toString().contains("[[" + formula.contact_name + "]]")
  interaction_date: |
    if(formula.is_meeting, date,
    if(formula.is_daily_interaction, date))
  interaction_type: |
    if(formula.is_meeting, "Meeting",
    if(formula.is_daily_interaction, "Daily note"))
properties:
  file.name:
    displayName: Note
  formula.interaction_date:
    displayName: Date
  formula.interaction_type:
    displayName: Type
```

<!--
## Papers (uncomment for academic contacts)
Replace YOUR_NAME with your name as it appears in author lists,
and ALIAS1, ALIAS2 with the contact's name variants.

## Papers
```base
filters:
  and:
    - formula.type_norm.contains("journal-article")
    - formula.has_alias_match
formulas:
  type_norm: type.toString().lower()
  authors_str: authors.toString()
  has_alias_match: |
    formula.authors_str.contains("ALIAS1")
    || formula.authors_str.contains("ALIAS2")
  is_coauthor: formula.authors_str.contains("YOUR_NAME")
  relationship: if(formula.is_coauthor, "Co-author", "Read")
views:
  - type: table
    name: Papers by this contact
    sort:
      - property: year
        direction: DESC
    columns:
      - file.name
      - year
      - journal
      - formula.relationship
      - status
properties:
  file.name:
    displayName: Paper
  year:
    displayName: Year
  journal:
    displayName: Journal
  formula.relationship:
    displayName: Relationship
  status:
    displayName: Status
```
-->
