# nrm1_knowledge_graph_agent

The app reads and converts  the rule into below json structure 
Store every NRM rule as JSON.

Example:

{
  "rule_id": "NRM-2.1.1",
  "group_element": {
    "code": "2",
    "name": "Superstructure"
  },
  "element": {
    "code": "2.1",
    "name": "Frame"
  },
  "sub_element": {
    "code": "2.1.1",
    "name": "Steel Frame"
  },
  "measurement_rule": {
    "unit": "m2",
    "description": "Area of floors related to frame",
    "measurement_method": "Measure floor area supported by frame"
  },
  "classification": {
    "nrm_version": "2021",
    "source": "NRM1"
  }
}
