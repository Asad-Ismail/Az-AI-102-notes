## Document Intelligence

Azure AI Document Intelligence uses Azure AI Services to analyze the content of scanned forms and convert them into data. It can recognize text values in both common forms and forms that are unique to your business.

In Azure AI Document Intelligence, three of the prebuilt models are for general document analysis:

Read (Use this model to extract words and lines from both printed and hand-written documents. It also detects the language used in the document)

General document (Use this model to extract key-value pairs and tables in your documents.)

Layout (Use this model to extract text, tables, and structure information from forms. It can also recognize selection marks such as check boxes and radio buttons.)


The other prebuilt models expect a common type of form or document:

Invoice (Use this model to extract key information from sales invoices in English and Spanish.)

Receipt (Use this model to extract data from printed and handwritten receipts.)

W-2 US tax declaration

ID Document

Business card

Health insurance card


## Azure Docmnet Intelligence VS OCR

Azure AI Vision with its Optical Character Recognition (OCR) feature, you can submit photographed or scanned documents and extract their words and text in JSON format. This functionality is similar to Azure AI Document Intelligence and can make it difficult to choose from these services.

If you want to extract simple words and text from a picture of a form or document, without contextual information, Azure AI Vision OCR is an appropriate service to consider. You might want to use this service if you already have your own analysis code, for example. However, Azure AI Document Intelligence includes a more sophisticated analysis of documents. For example, it can identify key/value pairs, tables, and context-specific fields. If you want to deploy a complete document analysis solution that enables users to both extract and understand text, consider Azure AI Document Intelligence.

## Custom Models

A custom model, trained on forms with similar structures and key-value pairs, you will obtain more predictable and standardized results from your unusual form types.
To train a custom model, you must supply at least five examples of the completed form but the more examples you supply, the greater the confidence levels Azure AI Document Intelligence will return when it analyzes input. The more varied your documents are in terms of structure and terminology, the greater the number of example documents you will need to supply to train a reliable model.

There are two kinds of custom model:

### Custom template models.
 A custom template model is most appropriate when the forms you want to analyze have a consistent visual template. If you remove all the user-entered data from the forms and find that the blank forms are identical, use a custom template model. Custom template models support 9 different languages for handwritten text and a wide range of languages for printed text. If you have a few different variations of the form templates, train a model for each of the variations and then compose the models together into a single model. The service will invoke the model best suited to analyze the document.
### Custom neural models.
 A custom neural model can work across the spectrum of structured to unstructured documents. Documents like contracts with no defined structure or highly structured forms can be analyzed with a neural model. Neural models work on English with the highest accuracy and a marginal drop in accuracy for Latin based languages like German, French, Italian, Spanish, and Dutch. Try using the custom neural model first if your scenario is addressed by the model.

## Composed models

A composed model is one that consists of multiple custom models. Typical scenarios where composed models help are when you don't know the submitted document type and want to classify and then analyze it. They are also useful if you have multiple variations of a form, each with a trained individual model. When a user submits a form to the composed model, Document Intelligence automatically classifies it to determine which of the custom models should be used in its analysis. In this approach, a user doesn't have to know what kind of document it is before submission. That can be helpful when you're using lots of similar forms or when you want to publish a single endpoint for all your form types.

Standard pricing tier, you can add up to 100 custom models into a single composed model. Free pricing tier, you can only add up to 5 custom models.

The Standard tier supports up to 15 concurrent requests 
