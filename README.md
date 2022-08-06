# Storing, Retrieving & Implementing Objects using AWS S3


This article is intended to be a visual guide for one use case I implemented for a project using Amazon S3. Essentially what this service offers is a simple cloud object storage that can read, retrieve, store and display data from anywhere, as well as import it into projects with a live 'Object URL'.

For this use case, I built a simple e-commerce store and used Amazon S3 to create buckets and store objects in them. The data I uploaded into the bucket is referred to as an object and its metadata is a way to specify what kind of object it is. For my specific use case, I had to enable public access (which is by default blocked to the public), since the objects I stored are meant to be visible on the e-commerce application as product data. I also had to create a policy within my bucket using JSON syntax to grant resource-based public permissions to the bucket data.

_You can think of S3 as a virtual cloud drive where you can create folders (buckets) to store data files (objects) and specify what kind of objects they are by adding tags (metadata)._

