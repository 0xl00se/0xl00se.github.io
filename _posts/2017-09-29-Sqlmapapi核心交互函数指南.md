---
layout:     post
title:      Sqlmapapi核心交互函数指南
subtitle:   札记
date:       2017-09-29
author:     0xl00se
header-img: img/post-bg-web.jpg
catalog: true
tags:
    - Sqlmapapi
    - 参考指南
    - 札记
---
### Users’ methods
```
@get("/task/new")
def task_new():

说明：Create new task ID
```
```
@get("/task/<taskid>/delete")
def task_delete(taskid):

说明：Delete own task ID
```
### Admin functions 
```
@get("/admin/<taskid>/list")
def task_list(taskid=None):

说明：List task pull
```
```
@get("/admin/<taskid>/flush")
def task_flush(taskid):

说明：Flush task spool (delete all tasks)
```
### sqlmap core interact functions 
#### Handle task’s options
```
@get("/option/<taskid>/list")
def option_list(taskid):

说明：List options for a certain task ID
```
```
@post("/option/<taskid>/get")
def option_get(taskid):

说明：Get the value of an option (command line switch) for a certain task ID
```
```
@post("/option/<taskid>/set")
def option_set(taskid):

说明：Set an option (command line switch) for a certain task ID
```
#### Handle scans
```
@post("/scan/<taskid>/start")
def scan_start(taskid):

说明：Launch a scan
```
```
@get("/scan/<taskid>/stop")
def scan_stop(taskid):

说明：Stop a scan
```
```
@get("/scan/<taskid>/kill")
def scan_kill(taskid):

说明：Kill a scan
```
```
@get("/scan/<taskid>/status")
def scan_status(taskid):

说明：Returns status of a scan
```
```
@get("/scan/<taskid>/data")
def scan_data(taskid):

说明：Retrieve the data of a scan
```
#### Functions to handle scans’ logs
```
@get("/scan/<taskid>/log/<start>/<end>")
def scan_log_limited(taskid, start, end):

说明：Retrieve a subset of log messages
```
```
@get("/scan/<taskid>/log")
def scan_log(taskid):

说明：Retrieve the log messages
```
#### Function to handle files inside the output directory
```
@get("/download/<taskid>/<target>/<filename:path>")
def download(taskid, target, filename):

说明：Download a certain file from the file system
```
