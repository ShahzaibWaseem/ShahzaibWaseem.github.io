---
title: Wikipedia Search Engine
date: 2018-01-10
categories:
  - Project
tags: 
  - Python
  - XML
toc: true
toc_label: "Table of Contents"
toc_icon: "th-list"
toc_sticky: true
---

**Language Used**: Python2

**Source Code**: [GitHub Link](https://github.com/ShahzaibWaseem/Project-DSA)

## Goal
The goal of this project was to make a search engine capable of forward indexing the contents of a particular file or article and search through the indexed files to make the process whole lot smooth. One of the goals of the project was to make the searcher should work in real time.**Backwards indexing was not in the scope of this project**.

## Tools & Libraries
- Pickle
- Wikipedia Dump XMLs
- xml.etree.cElementTree
- heapq

## Description
### Project Flow
The flow of the project is as follows:
- Wikipedia Dump XML files
- Pre-processing (`importing.py`)
- Forward Indexing (heapify() in `indexer.py`)
- Serialization
- Saving the indexed files
- Maintaining a log file (`indexTime.txt`)

After this the piece of code expects the user to run the other python script `searcher.py` to search for the words, from their the flow looks like:
- Load indexed files
- Ask the user for a query
- Maintaining a log file (`searchTime.txt`)

### SAX Parsing vs DOM Parsing
The `indexer.py` employes SAX (Simple API for XML) parsing, instead of DOM (Document Object Model) parsing, to parse the xml files because SAX parser does not load the whole xml file into the memory because it won't be physically possible to load the whole file (can be over 20 GBs) into the memory and then perform the indexing techniques, SAX parser is an event based XML parser and does not load the whole file into the memory.

### Indexing
The script file `indexer.py` does a lot of things, like shaving the xml tags so they won't appear in the final indexed files and the stop words were taken care of to lessen the amount of words to be processed and indexed. The script heapifies the contents after they are preprocessed and then it serializes it so that the words are saved in a serial order. The script saved 2000 words in one file and creates a new file when the 2000 word mark is up. One thing to note is that the title of the articles, inside the huge xml file, were separately indexed, but all of the locations of the words were maintained in a special file (`word_positions.pickle` and `title_positions.pickle`). This process is totally RAM and CPU dependent and it takes around 160-170 seconds to process a 608 MBs file and created 245 text files.

### Searching
The `searcher.py` script has a relatively simpler job and that was to ask the user for a query, which was broken using the same rules as was the xml file (see `importing.py`) and then the words were sought in the files created and the results were fetched and shown onto the screen. This process has to be seem less and should fetch results in real time, which it does. It returns when it could not find a single hit (the query "nothing" returns 0 results. see `searchTime.txt`) in 0.00004 seconds and a very frequent query like "wolf lion den" (56 hits) in 0.03 seconds. It is pretty evident that it takes less than a fraction of second which asserts the claim that it forward indexes the content of the .xml file and then searches for it. **Backwards indexing was not in the scope of this project**.

### Project Demo Video
<video width="606" height="364" controls>
	<source src="/assets/images/ProjectAssets/WikipediaSearchEngine/demo.mp4" type="video/mp4">
</video>

In case the video player does not work go to this [link](https://github.com/ShahzaibWaseem/Project-DSA/blob/master/demo.ogv).

## How to run the project
```python
$ python indexer.py
$ python searcher.py
```

## References
Visit this article from [GeeksForGeeks](https://www.geeksforgeeks.org/understanding-python-pickling-example/) or [Data Camp](https://www.datacamp.com/community/tutorials/pickle-python-tutorial) to learn more about Pickle.

For DOM vs SAX you can visit this article on [Knowledge Hut](https://www.knowledgehut.com/tutorials/python-tutorial/python-xml#:~:text=DOMentire%20file%20is%20read%20into,changes%20to%20the%20XML%20file.) or this question from [Stack Overflow](https://stackoverflow.com/questions/192907/xml-parsing-elementtree-vs-sax-and-dom).

You can fork the project on [GitHub](https://github.com/ShahzaibWaseem/Project-DSA) to add more features to the project.