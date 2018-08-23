---
title: "[Mobile] Scroll To Text" 
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/mobile-scroll-to-text.html 
description: 
---
Description
-----------

Scroll to an element which contains the given text.

Parameters
----------

<table class="" style="table-layout: fixed;"><thead><tr><th class="" style="">Param</th><th class="" style="">Param Type</th><th class="" colspan="1" style="">Mandatory</th><th class="" colspan="1" style="">Description</th></tr></thead><tbody class="" style=""><tr class="" style=""><td class="" colspan="1" style="">text</td><td class="" colspan="1" style="">String</td><td class="" colspan="1" style="">Required</td><td class="" colspan="1" style=""><span style="" class="">Text of the element to scroll to</span></td></tr><tr class="" style=""><td class="" style=""><span style="" class="">flowControl</span></td><td class="" style=""><span style="" class="">FailureHandling</span></td><td class="" colspan="1" style="">Optional</td><td class="" colspan="1" style=""><span style="" class="">Spec</span><span class="" style="">ify </span><a href="https://docs.katalon.com/x/qAAM" rel="nofollow" class="" style="">failure handling</a><span class="" style=""> schema to determine whether the execution should be allowed to continue or stop.</span></td></tr></tbody></table>

Example 
--------

Scroll to the element which the displayed text is Xfermodes.

```
import static com.kms.katalon.core.testcase.TestCaseFactory.findTestCase
import static com.kms.katalon.core.testdata.TestDataFactory.findTestData
import static com.kms.katalon.core.testobject.ObjectRepository.findTestObject
import internal.GlobalVariable as GlobalVariable
import com.kms.katalon.core.configuration.RunConfiguration as RunConfiguration
import com.kms.katalon.core.mobile.keyword.MobileBuiltInKeywords as Mobile
import com.kms.katalon.core.util.internal.PathUtil as PathUtil

'Start application on current selected android\'s device'
Mobile.startApplication(GlobalVariable.G_AndroidApp, false)

Mobile.tap(findTestObject('Application/android.widget.TextView - Graphics'), GlobalVariable.G_Timeout)

'Scroll to element which displayed text is Xfermodes'
Mobile.scrollToText('Xfermodes')

'Get item\'s label'
def itemText = Mobile.getText(findTestObject('Application/Graphics/android.widget.TextView - Xfermodes'), GlobalVariable.G_Timeout)

'Verify if item\'s label is equal to \"Xfermodes\"'
Mobile.verifyEqual(itemText, 'Xfermodes')

'Close application on current selected android\'s device'
Mobile.closeApplication()
```