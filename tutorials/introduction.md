# Introduction to Rapido Flutter Library
## TOC
 * Introduction to Rapido
 * [1: Make a complete app with a few lines of code](./flutter_app_in_few_lines.md)
 * [2: Brand and light customization](./customize_flutter_app.md)
 * [3: Input and Display Types](./rapido_input_types.md)
 * [4: Providing your own widgets](./custom_flutter_widgets.md)
 * [5: Adding maps and location](./flutter_maps_and_location.md)
 * [6: Adding images](./flutter_images.md)
 * [7: Document and DocumentList](./rapido_documents.md)
 * [8: Storing Secrets](./secrets_persistence.md)
 * [Full Code Example](./main.dart)

# Overview of Rapido for Flutter
Rapido is an open source library that intends to make cross platform development easy and fun. We do this by taking a document-centric approach to development, and by following Rapid Application Development (RAD) principles whenever possible.

Skip this page and head to the [tutorial](flutter_app_in_few_lines.md) if you just want to get to the code. 

## What do you mean by "document-centric?"
Many, if not most, applications are centered around a collection of data, whether entered by the the user, or from a central source, often, but not always, on the Internet somehwere. Applications are designed to allow users to create, retrieve, update, and delete this data, or perform some subset of these actions. In a document centric view, each "entity" that the user can perform these actions on, along with the properties of those  is considered a "document."

Take, for example, an application that allows users to collaborate on listing good places to eat in a city for people who cannot eat gluten. Each document would be a restaurant, and it would have certain properties such as address, ratings, an image etc...

In code, each document is represented as a Map with each property having a string for the key, and some other data type for the value. This would be called a dictionary in Python, or an Object in Javascript.

## What is RAD?
Rapid Application Development means that, as a developer, you should get a lot of functionality for not very much work. However, this should not come at the expense of power and flexibility. RAD means that you should only be spending your time as a developer focused on the parts of your application that are unique.

## What does Rapido do for you?
With Rapido, all you need to do is define the kind of documents that you want in a very easy way, and rapido will provide all of the UI that your users need to interact with those documents at run time. 

Rapido also handles persistence for you in a very easy way. Every change to a [Document](https://pub.dartlang.org/documentation/rapido/latest/rapido/Document-class.html) or a [DocumentList](https://pub.dartlang.org/documentation/rapido/latest/rapido/DocumentList-class.html) is automatically saved on the user's device with no extra code required.

### Just show me some code already
In a nutshell, Rapido let's you define documents you care about in a simple way. Either by simply creating documents, or you can define labels for those documents in the UI. The latter way is handy if your app starts without any documents.

In this code, we are creating a [DocumentList](https://pub.dartlang.org/documentation/rapido/latest/rapido/DocumentList-class.html), which, you may guess, is a list of documents. As we create the list, we are supplying some optional information for how we want to display the fields of the documents in the UI:

```dart
  DocumentList documentList = DocumentList(
    "Tasker",
    labels: {
      "Date": "date",
      "Task": "title",
      "Priority": "pri count",
      "Note": "subtitle",
    },
  );
  ```

  This is enough information for Rapido to create all of the UI that users need to manage those documents. The easiest way is to use a [DocumentListScaffold](https://pub.dartlang.org/documentation/rapido/latest/rapido/DocumentListScaffold-class.html), which will create all the UI all at once:

  ```dart
  @override
  Widget build(BuildContext context) {
    return DocumentListScaffold(
      documentList
    );
  }
  ```
This code creates this full application:
![full app](../assets/basic-ui.png)

This will make a lot more sense if you look at the code, so head over to the [tutorial](flutter_app_in_few_lines.md).
