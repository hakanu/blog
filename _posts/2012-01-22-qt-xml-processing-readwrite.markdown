---
layout: post
title: Qt XML Processing - Read/Write
date: '2012-01-22 15:33:07'
---

<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2011/11/back-to-the-future-part-iii-mp4_20110916_013856-873.jpg"><img class="aligncenter" title="hey gidi delorean" src="http://devdala.files.wordpress.com/2011/11/back-to-the-future-part-iii-mp4_20110916_013856-873.jpg" alt="" width="691" height="374" /></a></p>
A basic post for describing the usage of QDom. RIP Delorean :-0

I'm writing this for myself in fact. Because in the beginning of every project i forget how to do these.

Btw, in my opinion QDom is better than original Dom:)

Little tip: For platform independency, in Qt programs you can write the whole file path with '/' char. Qt replaces it with system's seperator. If you are compiling the code in Windows, it will be replaced with '\' and in Linux, it will stay same.
<h2>Xml Reading</h2>
<code>
<pre lang="cpp" line="1">
void Util::xmlReader()
{
    QDomDocument doc("Root");
//here is my xml file. it is in the project.
    QString sFilePath("dene1.xml");
    QFile file( sFilePath );
//Read the file first
    if (!file.open(QIODevice::ReadOnly))
        return;
    if (!doc.setContent(&file))
    {
//Transforming QString to C's string is a little costly
        printf("File not found : %s\n", sFilePath.toStdString().c_str() );
        file.close();
        return;
    }
    file.close();

    QDomElement docElem = doc.documentElement();

    QDomNode n = docElem.firstChild();
    while(!n.isNull()) {
        QDomElement e = n.toElement();
        if(!e.isNull()) {
            cout << "tag  : " << e.tagName().toStdString() << endl;
            cout << "value: " << e.text().toStdString() << endl;
        }
        n = n.nextSibling();//don't forget this is important!
    }
}
</pre>
</code>
<h2>Xml Writing</h2>
<code>
<pre lang="cpp" line="1">

void Util::xmlWriter()
{
    QDomDocument doc("Root");
    QDomElement root = doc.createElement("Root");
    doc.appendChild(root);

    QDomElement tag = doc.createElement("Child");//Directly creates an element
    root.appendChild(tag);

    QDomText t = doc.createTextNode("Hello World");//Content of element
    tag.appendChild(t);

    QString xml = doc.toString();
    qDebug() << "xml : " << xml << endl;

    xmlDosyayaYazdir("dene1.xml",doc);
}
</pre>
</code>
<h2>Writing File to Disk</h2>
<code>
<pre lang="cpp" line="1">

bool Util::xmlWriteFileToDisk(QString par_sFilePath, QDomDocument par_qXmlDoc)
{
    QFile dosya( par_sFilePath );

    if (dosya.open(QFile::WriteOnly | QFile::Truncate))
    {
        QTextStream out(&dosya);
        out << par_qXmlDoc.toByteArray(6);
        return true;
    }else
    {
        return false;
    }
}
</pre>
</code>
Cheerios