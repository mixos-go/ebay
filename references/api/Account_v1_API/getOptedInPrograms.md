---
title: getOptedInPrograms
category: Account_v1_API
api_name: getOptedInPrograms
method: GET
path: /program/get_opted_in_programs
---

**Category:** Account_v1_API
**API:** getOptedInPrograms

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/program/get_opted_in_programs

## API Description
This method gets a list of the seller programs that the seller has opted-in to.

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| programs | array<Program> | No | An array of seller programs that the seller's account is opted in to. An empty array is returned if the seller is not opted in to any of the seller programs. |
| programs.programType | string | No | The seller program to opt in to when part of an optInToProgram request, or out of when part of an optOutOfProgram request. When returned in an getOptedInPrograms response, a separate programType field is returned for each seller program that the seller is opted in to. For implementation help, refer  |
