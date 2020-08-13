====================================================================================
Assignment 2: Semantic Coupling using Vector State Model
====================================================================================

1. Introduction
------------------------------------------------------------------------------------
The tool is used to measure semantic coupling between two java classes.
a. It created a TF.IDF weight vector to represent each java class.
b. Calculayes cosing similarity between given class and all other classes.
c. Ranks all classes based on cosine similarity.
 
 
2. Design
------------------------------------------------------------------------------------
Template Project structure:
Class : SemanticCOupling
		-documentsPath
		-maxPrintResults
		-targetFileName
		-javaClasses
		-run()
Class: Utility
	-initializeStanfordCoreNLP
	-findDocumentByFilename
	-getDocumentSimilarities
	-rankSimilarDocuments
	-printTopKSimilarDocuments
	-dumpDictionaryToDisk
	-dumpJavaClassToDisk

Class: JavaClass
	-readDocument
	-preprocessDocument
	-tokenizeAndStemDocument
	-splitIdentifiers
	-removePunctuation
	-claculateTfs
	-claculateTfIdfs
	-claculateCosineSimilarity
	
Class:Dictionary
	-buildIntvertedIndex
	-calculateIdfs
 

 
The output format is:
 {java class}-{cosine similarity}
 
 Eg: The top 1 Java class(es) ranked by semantic coupling is 
	 CanWriteFileFilter.java	0.66
 
3. Instructions to run:
-------------------------------------------------------------------------------------------------------
The project requires maven to be installed, run the folloing commands:
a. Extract and go into assignment-2 folder
b. mvn clean
c. mvn install
d. java -jar target/assignment-2.0.jar {path-to-classes} {java-class-name} {count-required}