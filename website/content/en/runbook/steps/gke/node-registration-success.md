---
title: "gke/Node Registration Success"
linkTitle: "Node Registration Success"
weight: 3
type: docs
description: >
  Verify Node Registration Checker output
---

**Product**: [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine)\
**Step Type**: AUTOMATED STEP

### Description

None

### Failure Reason

Node {NODE} in zone {LOCATION} is currently running, but it failed registration with kube-apiserver, below is the Node Registration Checker summary:

    {LOG_ENTRIES[0]}
    {LOG_ENTRIES[1]}
    {LOG_ENTRIES[2]}
    {LOG_ENTRIES[3]}
    {LOG_ENTRIES[4]}
    {LOG_ENTRIES[5]}
    {LOG_ENTRIES[6]}
    {LOG_ENTRIES[7]}
    {LOG_ENTRIES[8]}
    {LOG_ENTRIES[9]}
    {LOG_ENTRIES[10]}
    {LOG_ENTRIES[11]}
    {LOG_ENTRIES[12]}
    {LOG_ENTRIES[13]}
    {LOG_ENTRIES[14]}
    {LOG_ENTRIES[15]}

### Failure Remediation

To understand why the node failed registration with kube-apiserver, please check the following documentation page: https://cloud.google.com/kubernetes-engine/docs/troubleshooting/node-registration#use-nrc

### Success Reason

Node {NODE} is currently running and, according to the output from Node Registration Checker, it was registered successfully. Below is the log entry that shows successful registration:

  {LOG_ENTRY}

### Uncertain Reason

The node {NODE} in the zone {LOCATION} is running, but there are no logs generated by Node Registration Checker in the provided time range {START_TIME_UTC} - {END_TIME_UTC}.

### Uncertain Remediation

This runbook looks for logs generated by Node Registration Checker. Because there are no logs from Node Registration Checker for the node {NODE}, but it is running, there could be a different issue with the node.
Please try the runbook with a different node in the same nodepool.


### Failure Reason [Alternative 2]

Node {NODE} in zone {LOCATION} is not currently running. While checking logs it was found that it failed registration with kube-apiserver. Below is the Node Registration Checker summary:

    {LOG_ENTRIES[0]}
    {LOG_ENTRIES[1]}
    {LOG_ENTRIES[2]}
    {LOG_ENTRIES[3]}
    {LOG_ENTRIES[4]}
    {LOG_ENTRIES[5]}
    {LOG_ENTRIES[6]}
    {LOG_ENTRIES[7]}
    {LOG_ENTRIES[8]}
    {LOG_ENTRIES[9]}
    {LOG_ENTRIES[10]}
    {LOG_ENTRIES[11]}
    {LOG_ENTRIES[12]}
    {LOG_ENTRIES[13]}
    {LOG_ENTRIES[14]}
    {LOG_ENTRIES[15]}


### Failure Reason [Alternative 3]

Could not find summary from Node Registration Checker for node {NODE} in zone {LOCATION}. The node might have been deleted before Node Registration Checker could finish running.

### Failure Remediation [Alternative 3]

Try to run the runbook with a node that is currently running.

<!--
This file is auto-generated. DO NOT EDIT

Make pages changes in the corresponding jinja template
or python code
-->