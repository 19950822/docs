---
title: "[WS] Verify Response Status Code" 
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/ws_verify_response_status_code.html 
description: 
---
Description
-----------

Verify status code in the returned data from a web service call.

Parameters
----------

<table class="wrapped confluenceTable"><colgroup><col><col><col><col></colgroup><tbody><tr class="xtr-0"><th class="xtd-0-0 confluenceTh">Parameter</th><th class="xtd-0-1 confluenceTh">Parameter Type</th><th class="xtd-0-2 confluenceTh">Mandatory</th><th class="xtd-0-3 confluenceTh">Description</th></tr><tr class="xtr-1"><td class="xtd-1-0 confluenceTd"><span style="color: rgb(0,0,0);">responseObject</span></td><td class="xtd-1-1 confluenceTd"><span style="color: rgb(0,0,0);">ResponseObject</span></td><td class="xtd-1-2 confluenceTd">Required</td><td class="xtd-1-3 confluenceTd"><span style="color: rgb(52,52,55);">The object represents an HTTP Response, the user can get responded content type, header properties (sometimes the user may want to get cookies from response header)</span></td></tr><tr class="xtr-2"><td class="xtd-2-0 confluenceTd">expectedStatusCode</td><td class="xtd-2-1 confluenceTd"><span style="color: rgb(0,0,0);">int</span></td><td class="xtd-2-2 confluenceTd"><span>Required</span></td><td class="xtd-2-3 confluenceTd">The expected status code</td></tr><tr class="xtr-3"><td class="xtd-3-0 confluenceTd"><span style="color: rgb(0,0,0);">flowControl</span></td><td class="xtd-3-1 confluenceTd"><span style="color: rgb(0,0,0);">FailureHandling</span></td><td class="xtd-3-2 confluenceTd">Optional</td><td class="xtd-3-3 confluenceTd"><span style="color: rgb(0,0,0);">Spec</span><span>ify </span><a href="https://docs.katalon.com/x/qAAM" rel="nofollow">failure handling</a><span> schema to determine whether the execution should be allowed to continue or stop.</span></td></tr></tbody></table>

Returns
-------

*   **true** if the response status code is the same as the expected status code, otherwise **false**.

Example
-------

You want to verify if the response from "REST\_Status Codes/POST\_201" object returns the 201 status code.

```groovy
import static com.kms.katalon.core.checkpoint.CheckpointFactory.findCheckpoint
import static com.kms.katalon.core.testcase.TestCaseFactory.findTestCase
import static com.kms.katalon.core.testdata.TestDataFactory.findTestData
import static com.kms.katalon.core.testobject.ObjectRepository.findTestObject
import com.kms.katalon.core.checkpoint.Checkpoint as Checkpoint
import com.kms.katalon.core.checkpoint.CheckpointFactory as CheckpointFactory
import com.kms.katalon.core.mobile.keyword.MobileBuiltInKeywords as MobileBuiltInKeywords
import com.kms.katalon.core.mobile.keyword.MobileBuiltInKeywords as Mobile
import com.kms.katalon.core.model.FailureHandling as FailureHandling
import com.kms.katalon.core.testcase.TestCase as TestCase
import com.kms.katalon.core.testcase.TestCaseFactory as TestCaseFactory
import com.kms.katalon.core.testdata.TestData as TestData
import com.kms.katalon.core.testdata.TestDataFactory as TestDataFactory
import com.kms.katalon.core.testobject.ObjectRepository as ObjectRepository
import com.kms.katalon.core.testobject.TestObject as TestObject
import com.kms.katalon.core.webservice.keyword.WSBuiltInKeywords as WSBuiltInKeywords
import com.kms.katalon.core.webservice.keyword.WSBuiltInKeywords as WS
import com.kms.katalon.core.webui.keyword.WebUiBuiltInKeywords as WebUiBuiltInKeywords
import com.kms.katalon.core.webui.keyword.WebUiBuiltInKeywords as WebUI
import internal.GlobalVariable as GlobalVariable
 
'Send a request and returns its response'
def response = WS.sendRequest(findTestObject('REST_Status Codes/POST_201'))

'Verify if the response from "REST_Status Codes/POST_201" object returns the 201 status code'
WS.verifyResponseStatusCode(response, 201)
```