---
layout: post
title: My notes - Python tutorial for beginners
date: '2013-05-20 23:45:44'
---

<a href="http://devdala.files.wordpress.com/2013/05/mad-max-2-1981-720p-brrip-a-release-lounge-h264-mp4_20120206_212752-320.jpg"><img class="aligncenter" alt="" src="http://devdala.files.wordpress.com/2013/05/mad-max-2-1981-720p-brrip-a-release-lounge-h264-mp4_20120206_212752-320.jpg" width="1280" height="528" /></a>

I found my notes from the time when I was learning python. They are not quite tidy but might be useful. So I created this small python tutorial for newbies.

Python is a hybrid language which is interpreted by interpreter in the shell (or cmd). it has its own shell. You can easily switch to python shell from terminal by just writing "python".
<div>Python is a scripting language just like bash. It is high level and functional. This makes it readable. Nearly every job has a function in python. You can handle so many things in one line.</div>
<div>Python scripts can be run from python shell and they can be also run from python modules which are files with "py" extension. Every line in the module is interpreted and run by python shell and if there is an error, the operation stops. If the error is in a condition which is not reachable during that runtime, this error won't be seen by python shell. That's an interesting feature of python.</div>
<div>
<ul>
	<li>Open a new file. Name it. For ex: hello and Change its extension to "py". For my ex: hello.py</li>
	<li>On linux you need to change its permission level. because it is a runnable script. So we need to give it execute permissions.
<ul>
	<li>chmod +wx hello.py</li>
</ul>
</li>
	<li>Run it like a normal executable file:
<ul>
	<li>./hello.py</li>
</ul>
</li>
	<li>Recommended way:
<ul>
	<li>python hello.py</li>
</ul>
</li>
</ul>
</div>
<div>Syntax is based on indentation. That's nice because it is forcing programmer to indent their lines carefully and of course helping readability.</div>
<div>There is no ";" to indicate line endings. newline is enough. There is also no brackets "{", "}". Again this is helping readability.</div>
<div>For strings both " " and ' ' could be used.</div>
<div>The variables has no types in python. In fact they have but while defining there is no variable type definition in front of them. The type is revealed on runtime.</div>
<h3 style="text-align: center;"><strong>Some action</strong></h3>
<div>
<div>
<pre><span style="font-family: 'courier new', monospace;">#!/usr/bin/env python</span>
<span style="font-family: 'courier new', monospace;"># encoding: utf-8</span>
<span style="font-family: 'courier new', monospace;">"""</span>
<span style="font-family: 'courier new', monospace;">untitled.py</span>

<span style="font-family: 'courier new', monospace;">Created by Hakan Uysal on 2012-01-29.</span>
<span style="font-family: 'courier new', monospace;">Copyright (c) 2012 __MyCompanyName__. All rights reserved.</span>
<span style="font-family: 'courier new', monospace;">"""</span>

<span style="font-family: 'courier new', monospace;">def main():</span>
<span style="font-family: 'courier new', monospace;">    print ('i love hakanu.net')</span>

<span style="font-family: 'courier new', monospace;">if __name__ == '__main__':</span>
<span style="font-family: 'courier new', monospace;">    main()</span></pre>
</div>
</div>
<div>
<ul>
	<li>#!/usr/bin/env python
<ul>
	<li>This means that this is a python script and it must be run by python shell</li>
</ul>
</li>
	<li># encoding: utf-8
<ul>
	<li>This is for character encoding. Not mandatory</li>
</ul>
</li>
	<li>"""
<ul>
	<li>This is multiline comment start/stop indicator. It must match with same char.</li>
	<li>For one line comments you need to use "#" char</li>
</ul>
</li>
	<li>def main():
<ul>
	<li>As you know, main func where everyting starts.</li>
</ul>
</li>
	<li>print ('i love hakanu.net')
<ul>
	<li>This is printing the line onto screen function. it is so flexible. You can write whatever you want by using "print"</li>
</ul>
</li>
	<li>if __name__ == '__main__':</li>
</ul>
</div>
<div>
<ul>
	<li>This is for providing reusability by other modules. Sure i have my main func. That means im gonna use other functions. But somebody(some other module) may want to use my main. Not so big deal. It will be understood after experiencing more.</li>
</ul>
<h3 style="text-align: center;"><strong>Write your own function:</strong></h3>
<div>
<div>def func1():</div>
<div>    a = 5</div>
<div>    print ('im func1 and im calling func2 with parameter : ' + str(a))</div>
</div>
<ul>
	<li>def func1():
<ul>
	<li>define the name of function. Not use a function name such as mine. It is bad example.</li>
</ul>
</li>
	<li>    a = 5
<ul>
	<li>Don't forget to indent the line. Define a variable. We are assigning it to an integer. This means that a will be an integer</li>
</ul>
</li>
	<li>print ('im func1 and im calling func2 with parameter : ' + str(a))
<ul>
	<li>str(a) converts a from integer to string.</li>
</ul>
</li>
</ul>
<h3 style="text-align: center;"><strong>How to system functions and how to get command line arguments?</strong></h3>
</div>
<div>import sys</div>
<div>
<ul>
	<li>put this at the top your module. it is like "import" from java or "#include" from C/C++ or "using" from C# etc</li>
	<li>Command line arguments are like the other languages:
<ul>
	<li>sys.argv[0] --&gt; name of the program</li>
	<li>sys.argv[1] --&gt; 1st command line argument</li>
	<li>sys.argv[2] --&gt; 2nd command line argument</li>
	<li>...</li>
</ul>
</li>
</ul>
</div>
<div>
<div>if len(sys.argv) == 2:</div>
<div>if sys.argv[1] == 'deli':</div>
<div>greeting = "Welcome" + sys.argv[1]</div>
</div>
<div>
<ul>
	<li>len measures the length of arrays. it is so generic just like the other functions. If the command line arguments more than 2, run this condition</li>
	<li>We can see the basic usage of "if" conditions</li>
</ul>
</div>
<h3 style="text-align: center;"><strong>Strings</strong></h3>
<pre><strong>#</strong>Immutable objects. You can not change its elements.

<span style="font-family: 'courier new', monospace;">sName = 'hakanu.net'</span>
<span style="font-family: 'courier new', monospace;">#some cool functions</span>
<span style="font-family: 'courier new', monospace;">len(sName)  #length of string</span>

<span style="font-family: 'courier new', monospace;">print(sName[0])  #d</span>
<span style="font-family: 'courier new', monospace;">print(sName[1])  #e</span>
<span style="font-family: 'courier new', monospace;">print(sName[-1])  #m</span>
<span style="font-family: 'courier new', monospace;">print(sName[-2])  #o</span>

<span style="font-family: 'courier new', monospace;">print(sName[0:3])  #len</span>
<span style="font-family: 'courier new', monospace;">print(sName[0:-1])  #hakanu.net</span>
<span style="font-family: 'courier new', monospace;">find('dev')              #0</span></pre>
<div></div>
<div><span style="font-family: 'courier new', monospace;">sName.replace('devdala', 'hakanu') #sName will be 'hakanu.com'</span></div>
<div></div>
<div><span style="font-family: 'courier new', monospace;">#printing with parameters</span></div>
<div><span style="font-family: 'courier new', monospace;"> print '%s got: %s expected: %s' % (sName, "five", "three")</span></div>
<div></div>
<div>sSentence = 'this is a sentence'      #define a string with whitespaces</div>
<div>lWords = []    #define a list to keep the words in the sentence</div>
<div>lWords = sSentence.split()</div>
<h3 style="text-align: center;"><strong>Loops</strong></h3>
<div>
<pre><span style="font-family: 'courier new', monospace;"> list1 = [1,2,3]</span>
<span style="font-family: 'courier new', monospace;"> list2 = ['deli', 'coban', 'devdala']</span>
<span style="font-family: 'courier new', monospace;"> i = 0</span>
<span style="font-family: 'courier new', monospace;"> while i &lt; len(list1):</span>
<span style="font-family: 'courier new', monospace;"> print 'Yo ' + list2[i]</span>
<span style="font-family: 'courier new', monospace;"> i = i + 1</span></pre>
</div>
<pre></pre>
<div>
<pre><span style="font-family: 'courier new', monospace;"> for aName in list2:</span>
<span style="font-family: 'courier new', monospace;"> print 'Yo ' + aName</span>
<span style="font-family: 'courier new', monospace;">#</span>Look at the list definition list1 = [1,2,3] and list2 = ['deli', 'coban', 'devdala']</pre>
</div>
<h3 style="text-align: center;"><strong>Lists and List of lists</strong></h3>
<pre><span style="font-family: 'courier new', monospace;">#Enumarate lists</span></pre>
<div><span style="font-family: 'courier new', monospace;">bigList = [['deli', 1], ['Peter', 2], ['coban', 3]]</span></div>
<div></div>
<div><span style="font-family: 'courier new', monospace;"> for elem in bigList:</span></div>
<div><span style="font-family: 'courier new', monospace;"> print elem</span></div>
<div><span style="font-family: 'courier new', monospace;"> print 'Yo %s is %s years old' % (elem[0], elem[1])</span></div>
<div><span style="font-family: 'courier new', monospace;"> </span></div>
<pre><span style="font-family: 'courier new', monospace;">#cooler</span></pre>
<div><span style="font-family: 'courier new', monospace;"> for i, name in enumerate(bigList):</span></div>
<div><span style="font-family: 'courier new', monospace;"> print i, name</span></div>
<pre><span style="font-family: 'courier new', monospace;">#list operations</span></pre>
<div>
<pre><span style="font-family: 'courier new', monospace;">        empty_list = []</span>
<span style="font-family: 'courier new', monospace;"> teammates = []</span>
<span style="font-family: 'courier new', monospace;"> #appending a single new item to the list</span>
<span style="font-family: 'courier new', monospace;"> teammates.append('deli')</span>
<span style="font-family: 'courier new', monospace;"> teammates.append('coban')</span>
<span style="font-family: 'courier new', monospace;"> teammates.insert(0, 'hakan')</span>
<span style="font-family: 'courier new', monospace;"> print "Before appending: " , teammates</span>

<span style="font-family: 'courier new', monospace;"> #appending another list to the list</span>
<span style="font-family: 'courier new', monospace;"> other_team = ['ali', 'veli', 'kirkdokuz', 'elli']</span>
<span style="font-family: 'courier new', monospace;"> for other_person in other_team:</span>
<span style="font-family: 'courier new', monospace;"> teammates.append(other_person)</span>
<span style="font-family: 'courier new', monospace;"> print "After appending: " , teammates</span>

<span style="font-family: 'courier new', monospace;"> #removing from list - only works with name</span>
<span style="font-family: 'courier new', monospace;"> teammates.remove('elli')</span>
<span style="font-family: 'courier new', monospace;"> #removing from list - by id</span>
<span style="font-family: 'courier new', monospace;"> teammates.pop(0)</span>
<span style="font-family: 'courier new', monospace;"> print 'After removing: ' , teammates</span>

<span style="font-family: 'courier new', monospace;"> #lists like strings</span>
<span style="font-family: 'courier new', monospace;"> print 'first 3 of list : ', teammates[0:3] </span></pre>
</div>
<h3 style="text-align: center;"><strong>Tuples</strong></h3>
<pre>#the most asthounishing feature for myself</pre>
<div>
<pre>#tuples can not be modified in place like strings
#tuples are good for small elements which are diffrent

t = ('John', 'Peter', 'Susan')
print len(t)
#t.append('coban') #AttributeError: 'tuple' object has no attribute 'append'

l = [('peter', 28), ('coban', 31), ('deli', 30)]     #dont mess with elements - all of them needs to be in similar shape
for name, age in l:
print 'Printing tuple : ' , name , age</pre>
</div>
<h3 style="text-align: center;"><strong>Sorting</strong></h3>
<div>
<pre><span style="font-family: 'courier new', monospace;"> teammates = ['ali', 'veli', 'kirkdokuz', 'elli']</span>
<span style="font-family: 'courier new', monospace;"> print 'Teammates before sorting : ' , teammates</span>
<span style="font-family: 'courier new', monospace;"> teammates.sort() #modified the list in place -- IMPORTANT</span>
<span style="font-family: 'courier new', monospace;"> sorted_teammates = sorted(teammates) #sorted is another function provided by python</span>
<span style="font-family: 'courier new', monospace;"> print 'Sorted teammates : ' , sorted_teammates</span>

<span style="font-family: 'courier new', monospace;"> #tuple has no sort but sorted can be used</span>
<span style="font-family: 'courier new', monospace;"> t = ('John', 'Peter', 'Susan') </span>
<span style="font-family: 'courier new', monospace;"> tuple(sorted(t))</span>
<span style="font-family: 'courier new', monospace;"> print 'Sorted tuple : ' , t</span></pre>
</div>
<h3 style="text-align: center;"><strong>Yes everyting is reference like Java</strong></h3>
<div>
<pre><span style="font-family: 'courier new', monospace;"> #everything is reference</span>
<span style="font-family: 'courier new', monospace;"> a = [1,2,3]</span>
<span style="font-family: 'courier new', monospace;"> b = a</span>
<span style="font-family: 'courier new', monospace;"> print a</span>
<span style="font-family: 'courier new', monospace;"> print b</span>
<span style="font-family: 'courier new', monospace;"> a.append(4)</span>
<span style="font-family: 'courier new', monospace;"> print b #it will be [1,2,3,4] a and b are pointing to same explicit copy</span>

<span style="font-family: 'courier new', monospace;"> c = list(a)</span>
<span style="font-family: 'courier new', monospace;"> a.append(5)</span>
<span style="font-family: 'courier new', monospace;"> print a #[1,2,3,4,5]</span>
<span style="font-family: 'courier new', monospace;"> print b #same as a [1,2,3,4,5]</span>
<span style="font-family: 'courier new', monospace;"> print c #[1,2,3,4]</span></pre>
</div>
<h3 style="text-align: center;"><span style="font-family: arial, sans-serif;"><strong>Cool sorting, Sort by specified attribute</strong></span></h3>
<div>
<pre><span style="font-family: 'courier new', monospace;">def SortBySpecifiedAttribute():</span>
<span style="font-family: 'courier new', monospace;"> l = ['Yellow', 'Blue', 'Red', 'Green'] #l is a list</span>
<span style="font-family: 'courier new', monospace;"> print 'l unsorted : ', l</span>
<span style="font-family: 'courier new', monospace;"> sorted(l)</span>
<span style="font-family: 'courier new', monospace;"> print 'l sorted alphabetically : ', sorted(l)</span>
<span style="font-family: 'courier new', monospace;"> #sort by length of the word</span>
<span style="font-family: 'courier new', monospace;"> #len('Blue') = 4, len('Green') = 5, len('Red') = 3, len('Yellow') + 6</span>
<span style="font-family: 'courier new', monospace;"> l.sort(key=len) #key is the key of sorting</span>
<span style="font-family: 'courier new', monospace;"> print 'l is sorted by element length : ' , l</span>

<span style="font-family: 'courier new', monospace;"> l = ['Yellow', 'blue', 'rED', 'Green'] #l is a list</span>
<span style="font-family: 'courier new', monospace;"> #sort by upper/lowercase</span>
<span style="font-family: 'courier new', monospace;"> #lower it func to make the string's elements lowercase str.lower()</span>
<span style="font-family: 'courier new', monospace;"> #lower is not like len. lower needs a string object. So we need a global func to give a key</span>
<span style="font-family: 'courier new', monospace;"> #Normally capitals comes first</span>
<span style="font-family: 'courier new', monospace;"> l.sort(key=MyLower) </span>
<span style="font-family: 'courier new', monospace;"> print 'l is sorted by lowercase : ', l</span>

<span style="font-family: 'courier new', monospace;">def MyLower(str):</span>
<span style="font-family: 'courier new', monospace;"> return str.lower()</span></pre>
</div>
<h3 style="text-align: center;"><strong>Dictionaries, cooler than tuples</strong></h3>
<div>
<pre><span style="font-family: 'courier new', monospace;">def DictionariesInPython():</span>
<span style="font-family: 'courier new', monospace;"> ages = {} #keys have to be unique</span>
<span style="font-family: 'courier new', monospace;"> ages['John'] = 30</span>
<span style="font-family: 'courier new', monospace;"> ages['Peter'] = 27</span>
<span style="font-family: 'courier new', monospace;"> ages['Susan'] = 28</span>

<span style="font-family: 'courier new', monospace;"> print ages</span>
<span style="font-family: 'courier new', monospace;"> print ages['Susan']</span>

<span style="font-family: 'courier new', monospace;"> if 'Joe' in ages:</span>
<span style="font-family: 'courier new', monospace;"> print 'Print joes age' , ages['Joe']</span>
<span style="font-family: 'courier new', monospace;"> else:</span>
<span style="font-family: 'courier new', monospace;"> print 'No ages!'</span>

<span style="font-family: 'courier new', monospace;"> print 'Printing keys : ' , ages.keys()</span>
<span style="font-family: 'courier new', monospace;"> ages['Susan'] = 26</span>

<span style="font-family: 'courier new', monospace;"> keys = ages.keys()</span>
<span style="font-family: 'courier new', monospace;"> keys.sort() </span>

<span style="font-family: 'courier new', monospace;"> for name in keys:</span>
<span style="font-family: 'courier new', monospace;"> print name, ages[name]</span>

<span style="font-family: 'courier new', monospace;"> print 'printing values: ', ages.values()</span>

<span style="font-family: 'courier new', monospace;"> for name, age in ages.items():</span>
<span style="font-family: 'courier new', monospace;"> print name, age</span>

<span style="font-family: 'courier new', monospace;"> print 'Printing age items as tuples: ' , ages.items()</span>

<span style="font-family: 'courier new', monospace;"> all_ages = ages.values()</span>
<span style="font-family: 'courier new', monospace;"> print 'Mathops on ages(average age) : ' , sum(all_ages) / len(all_ages)</span>

<span style="font-family: 'courier new', monospace;"> print 'More precision : ' , sum(all_ages) / float(len(all_ages))</span>

<span style="font-family: 'courier new', monospace;"> print ages</span>

<span style="font-family: 'courier new', monospace;"> l = [('peter', 28), ('coban', 31), ('deli', 30)]</span>
<span style="font-family: 'courier new', monospace;"> print 'before deletion l :' , l</span>
<span style="font-family: 'courier new', monospace;"> del l[0]</span>
<span style="font-family: 'courier new', monospace;"> print 'after deletion l : ' , l </span>

<span style="font-family: 'courier new', monospace;"> mk = {}</span>
<span style="font-family: 'courier new', monospace;"> if 'John' in mk:</span>
<span style="font-family: 'courier new', monospace;"> mk['John'] += 1</span>
<span style="font-family: 'courier new', monospace;"> else:</span>
<span style="font-family: 'courier new', monospace;"> mk['John'] = 1</span>
<span style="font-family: 'courier new', monospace;"> print 'John check : ' , mk</span>

<span style="font-family: 'courier new', monospace;"> print 'print mk items as tuples : ' , mk.items()</span>

<span style="font-family: 'courier new', monospace;"> #RuntimeError: dictionary changed size during iteration</span>
<span style="font-family: 'courier new', monospace;"> #for name in mk:</span>
<span style="font-family: 'courier new', monospace;"> for name in mk.keys():</span>
<span style="font-family: 'courier new', monospace;"> if mk[name]&lt;= 1:</span>
<span style="font-family: 'courier new', monospace;"> del mk[name]</span>

<span style="font-family: 'courier new', monospace;"> print 'printing mk after deletion : l ', mk</span></pre>
</div>
<h3 style="text-align: center;"><strong>Reading text file</strong></h3>
<div>
<pre><span style="font-family: 'courier new', monospace;">def ReadTextFile():</span>
<span style="font-family: 'courier new', monospace;"> f = open('filePy.txt', 'r') #open for reading - opening does not load the file into memory</span>
<span style="font-family: 'courier new', monospace;"> print 'File content: ' , f.read()</span>
<span style="font-family: 'courier new', monospace;"> print 'Read again the file content: ' , f.read() #the reader pointer is at the end of the file</span>
<span style="font-family: 'courier new', monospace;"> f.close()</span>
<span style="font-family: 'courier new', monospace;"> f = open('filePy.txt', 'r')</span>
<span style="font-family: 'courier new', monospace;"> print 'Read file appropriately : ' , f.readlines()</span>
<span style="font-family: 'courier new', monospace;"> f.close()</span>

<span style="font-family: 'courier new', monospace;"> f = open('filePy.txt', 'r')</span>
<span style="font-family: 'courier new', monospace;"> contents = f.read()</span>
<span style="font-family: 'courier new', monospace;"> print 'Show the # of ' , contents.count('salt')</span>
<span style="font-family: 'courier new', monospace;"> print 'Show the # of ' , contents.count('line')</span></pre>
</div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>