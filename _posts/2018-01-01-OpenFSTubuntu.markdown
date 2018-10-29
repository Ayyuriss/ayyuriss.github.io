---
layout: post
title:  "Openfst how-to install"
date:   2018-01-01
categories: posts
author: "Ayoub"
tag: "HowTo"
description : "How to Install OpenFST (Ubuntu)"
---

Short story short, here's a short guide for essential steps to install OpenFst for Python under Ubuntu (with wrapper pywrapfst):
This is for version 1.6.6, but it should work for all versions. I assumed all C+11 building libraries/tools are installed.
<ol>
 	<li>Download openfst-*version*.tar.gz and open terminal in its location: <a href="http://www.openfst.org/twiki/bin/view/FST/FstDownload">http://www.openfst.org/twiki/bin/view/FST/FstDownload</a></li>
	<li>Install dependency GraphViz (for dot binary) <pre class="lang:sh decode:true "> sudo apt install graphviz</pre></li>
 	<li><pre class="lang:sh decode:true ">tar -xzf openfst-1.6.6.tar.gz </pre></li>
 	<li><pre class="lang:sh decode:true ">cd openfst-1.6.6/ </pre></li>
	<li><pre class="lang:sh decode:true ">./configure --enable-far=true</pre></li>
	<li><pre class="lang:sh decode:true ">make -j4</pre>(Replace 4 by number of threads to use) </li>
	<li><pre class="lang:sh decode:true ">sudo make install</pre></li>
	<li>Now the library is installed, but accessible for sudo environement only. Add the following line to user profile ~/.bashrc and source it:
<pre class="lang:sh decode:true ">echo "export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:/usr/local/lib" >> ~/.bashrc
source ~/.bashrc</pre></li>
	<li>Test the installation:
<pre class="lang:sh decode:true ">fstinfo --help</pre></li>
	<li>All that remains is to install python package and test:
<pre class="lang:sh decode:true ">sudo pip install openfst
python -c "import pywrapfst" </pre></li>
</ol>
