[TOC]

Getting started
===================

Olympus is a monitor system for P13n apps. It has a rest-api where you can see spec (alpha version) from http://backoffice.despegar.com/olympus/docs


Status
-------------

A status is a set of alarms that an application instance notify to olympus.

####Example
```
  {
    "app_details": {
      "app_name": "euler",
      "env": "prod",
      "host_name": "euler-web-00"
    },
    "data": {
      "general": "RED",
      "properties": {
          "alarm_name" : "RED",
          "alarm_name2" : "GREEN",
          "alarm_name3" : "YELLOW"
      }
    }
  }

```

The `properties` object has the alarms that an application notify, possible values of that properties are [RED, YELLOW,GREEN] like a semaphore. `general` is an optional field , refers to app general status based on the other alarms


Jobs
-------------

You can also notify a job execution.  First you have to submit the gracetime that you want a job to run, later when the job runs you have to notify olympus that the job run.

####Example

```sequence
Euler->Olympus: gracetime(ranking,30)
Note right of Olympus: Save gracetime
Olympus-->Olympus: check job execution
Note right of Olympus: ranking status RED
Euler-->Olympus: notifyJob(ranking)
Olympus-->Olympus: check job execution
Note right of Olympus: ranking status GREEN
```


Metrics
-------------

You can submit metrics to olympus 
####Example
```
{
  "app_details": {
    "app_name": "euler",
    "env": "prod",
    "host_name": "euler-web-00"
  },
  "data": [
    {
      "name": "rejected_events",
      "value": 100
    },
    {
      "name": "received_events",
      "value": 500
    }
  ]
}
```

 
> **Note:**

> - Check java api https://github.com/despegar/olympus
