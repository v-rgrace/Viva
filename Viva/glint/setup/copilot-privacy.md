---
title: Data, privacy, and security compliance for Microsoft 365 Copilot in Viva Glint 
description: Microsoft 365 Copilot in Viva Glint summarizes survey comments and employee suggestions to help organizational leaders and managers quickly identify top issues and themes from comments. 
ms.author: JudithWeiner
author: JudyWeiner
manager: MelissaBarry
audience: admin
f1.keywords: NOCSH
keywords: 
ms.collection:  
- m365initiative-viva
- selfserve
- viva-copilot
- magic-ai-copilot
search.appverid: MET150 
ms.topic: article
ms.service: viva-glint
ms.localizationpriority: high
ms.custom: CELA-approved
ms.date: 11/16/2024
---

# Data, privacy, and security compliance for Microsoft 365 Copilot in Viva Glint

[Copilot in Viva Glint](/viva/glint/copilot/copilot-admin-intro) summarizes survey comments and employee suggestions to help organizational leaders and managers quickly identify top issues and themes from comments. This article covers how data privacy and security is handled for Copilot in Viva Glint.

## Foundations, security, and compliance

**Q: How does Microsoft 365 Copilot in Viva Glint work in the backend?**

**A:** Copilot in Viva Glint uses Large Language Model (LLM) technology, which allows users to perform language-based tasks by entering prompts in natural languages. Microsoft uses these LLMs to match users’ prompts to a set of metrics and stories. A story is a product-defined group of calculations, which is based on metrics, aggregations, and other variables.

**Q: Does Microsoft 365 Copilot in Viva Glint use customer data to train?**

**A:** No. Copilot in Viva Glint doesn’t use customer data to train any models. Instead, Copilot in Viva Glint employs generically trained LLM models and supplies the necessary grounding data and context for each request. For this reason, each user's Copilot responses are generated only from their accessible data and current survey results. Users can only access information they have permission to view in Glint, such as dashboards, reports, or exports. 

**Q: Does Microsoft 365 Copilot in Viva Glint store any personal data?**

**A:** No.  Copilot in Viva Glint doesn’t process or store any personal data. Copilot in Viva Glint doesn’t know which employee submitted a survey response or comment.   

**Q: Does Microsoft 365 Copilot in Viva Glint save or store data used in summaries?**

Yes. Copilot in Viva Glint saves and stores comments summarization. It follows the security and compliance for data usage practices in place for Viva Glint so the saved data isn't traceable to a respondent. Copilot in Viva Glint saves only the metadata for each API call, such as the date and time of each prompt. The meta log is only accessed by Glint developers. 

**Q: How does Copilot in Viva Insights comply with GDPR and other privacy regulations?**

**A:** See [GDPR and Generative AI: A Guide for Public Sector Organizations](https://wwps.microsoft.com/blog/GDPR-GenAI) and [Read our publicly shared privacy policy](/../../viva/glint/setup/viva-glint-privacy).

**Q: Can conclusions be drawn about individual employees based on the summaries or displays in Microsoft 365 Copilot in Viva Glint?**

**A:** Copilot only summarizes comments that the user is already authorized to see in Glint. No other insights about individual employees can be inferred beyond what is stated in those comments. 

**Q: If employees name a manager within their comments, can that manager's name be displayed in the Microsoft 365 Copilot in Viva Glint response?**

**A:** If a manager’s name is included in the comments, it's possible their name could appear in a Copilot in Viva Glint summary. Customers can redact or quarantine comments in Glint, so Copilot can't use redacted comments for summarization. [Flag Sensitive comments in Viva Glint | Microsoft Learn] (/viva/glint/setup/glint-sensitive-comments)

**Q: How is bias mitigated?**

**A:** Copilot is tested with realistic dummy data and human subject matter experts to evaluate the accuracy and relevance of the Copilot responses. Evaluation results are used in an improvement feedback loop to update the LLM instructions to improve the accuracy and relevance of the results and to mitigate any detected biases.   

**Q: How is Microsoft 365 Copilot better than ChatGPT when it comes to summarizing comments?**

**A:** **Security and Privacy** - We know that customers are tempted to use AI tools like the publicly available ChatGPT - or even their own company’s AI - to analyze survey comments. ChatGPT doesn't follow confidentiality thresholds the customers set in Glint. Copilot in Viva Glint strictly follows Microsoft’s and Glint’s privacy, security, and confidentiality protection for customers’ data.  

## Data processing  

**Q: What customer data does Copilot in Viva Glint process?**

**A:** Copilot in Viva Glint filters and summarizes comments by accessing customer-uploaded employee attributes from your organization’s Human Resources Information System (HRIS) file. 

Copilot in Viva Glint processes only HR attribute values and survey comments that the user has permissions to view on their Glint dashboard. 

<br>**Q: How is data transferred between Microsoft Copilot in Viva Glint and Microsoft 365 Copilot?**

**A:** Copilot in Viva Glint uses Microsoft 365 LLM technology to process customer data. Microsoft 365 LLM technology follows Microsoft’s security and privacy standards.  
Furthermore, data isn't transferred between US and EU servers.  

<br>**Q: Does Microsoft 365 Copilot in Viva Glint share data with other Microsoft 365 Copilots?**

**A:** No. Copilot in Viva Glint doesn't share data with any other Microsoft 365 Copilot applications.

<br>**Q: Can Microsoft 365 Copilot in Viva Glint access customer data from the M365 Graph?**

**A:** No. Copilot in Viva Glint doesn't have access to customer data with any other Microsoft 365 Graph.  

<br>**Q: Does Microsoft 365 Copilot in Viva Glint surface information from the public internet?**

**A:** No. Copilot in Viva Glint doesn’t access the public internet to generate responses. 

<br>**Q:Can conclusions be drawn about individual employees based on the summaries or displays in Microsoft 365 Copilot in Viva Glint?**

**A:** Copilot in Viva Glint only summarizes comments that the user is authorized to see in Glint. No other insights about individual employees are inferred beyond what is stated in those comments. 

## Integration with other Microsoft Viva applications

<br>**Q: How does Copilot in Viva Glint integrate with other Viva apps?**

**A:** Copilot in Viva Glint is confined to Viva Glint, and its functionality is distinct from other Microsoft 365 Copilots. It doesn’t interact with Microsoft 365 Copilot, Microsoft Graph, or any other Microsoft 365 services. Copilot in Viva Glint can interact with other non-Copilot integrations your organization enables for Viva Glint.

## More information

- [Security and privacy for data usage in Viva Glint](/../../viva/glint/setup/gdpr-special-categories)
- [Microsoft compliance – Viva Glint](/../../viva/viva-compliance)
- [Learn how managers can use Copilot in Viva Glint](https://go.microsoft.com/fwlink/?linkid=2274072)
- [Find answers to technical FAQs](https://go.microsoft.com/fwlink/?linkid=2274071)
- [Copilot for Microsoft 365](https://adoption.microsoft.com/copilot/)



