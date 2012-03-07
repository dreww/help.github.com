---
layout: default
title: Verify Your SSH Keys
description: A quick guide to help you verify your SSH keys using fingerprints
---

<p class="intro">This is the guide to verifying your SSH keys in <strong>Linux</strong>. There are also guides for <strong><a href="/win-verify-ssh">Windows</a></strong> and <strong><a href="/mac-verify-ssh">OS X</a></strong>.</p>

<p>GitHub uses SSH keys to establish a secure connection between your computer and GitHub.</p>

<p>
To verify your SSH keys you need to find the <b>fingerprint</b> of each key on your computer and compare it to the fingerprint displayed on GitHub.
</p>

<p>
If there are keys on your GitHub account that you don't recognize you should <b>delete them immediately</b>.
</p>

##<span class="step">First:</span> What's a Fingerprint?

An SSH key's fingerprint is a sequence of bytes unique to that key. Fingerprints are usually encoded into hexadecimal strings and formatted into groups of characters for readability.

We display SSH key fingerprints on GitHub along with the key's title:

![](https://img.skitch.com/20120307-gy4e74ah5yftbddhmjnsypatnr.png)

##<span class="step">Next:</span> Find and Compare Fingerprints

First, you need to open an app called Terminal.

<img src="/images/bootcamp/bootcamp_1_linux_terminal.jpg" alt="Open the terminal" />

<div class="more-info">
  <h4 class="compressed">Need a quick lesson about Terminal?</h4>
  <div class="more-content">
    <p>Code blocks like those on this page are part of a scripting language called Bash. To use Bash scripts, we need to use an application that comes with Linux called Terminal.</p>

    <h4>Input</h4>
    <pre class="terminal bootcamp">
      <span class="codeline">$ echo 'This is input text'<span>This tooltip tells you what's going on.</span></span>
    </pre>

    <p>A line that begins with the dollar sign ($) indicates a line of Bash script you need to type. To enter it, type the text that follows the $, hitting the return key at the end of each line. You can hover your mouse over each line for an explanation of what the script is doing.</p>

    <h4>Output</h4>
    <pre class="terminal bootcamp">
      <span class="bash-output">This is output text.</span>
    </pre>

    <p>A line that does not begin with a $ is output text that is intended to give you information or tell you what to do next. We&rsquo;ve colored output text green in these bootcamp tutorials.</p>

    <h4>User Specific Input</h4>
    <pre class="terminal bootcamp">
      <span class="codeline">$ echo '<em>username</em>'<span>Outputs the text in the quotation marks.</span></span>
    </pre>

    <p>Areas of yellow text represent your own personal info, repos, etc. If it is part of an input ($) line, you should replace your it with your own info when you type it. If it is part of output text, it is just for your reference. It will automatically show your own info in Terminal.</p>

    <p><strong>Good to know</strong>: There will be times when you type code, hit return, and all you are given is another prompt. Some actions that you execute in Terminal don&rsquo;t have any output. Don&rsquo;t worry, if there is ever a problem with your code, Terminal will let you know.</p>

    <p><strong>Good to know</strong>: For security reasons, Terminal will not display what you type when entering passwords. Just type your password and hit the return key.</p>
  </div>
</div>

1. <span class="step-title">Find SSH key fingerprints.</span>

	Copy and paste this command into Terminal to find the fingerprints for all public keys in your ".ssh" directory:

	<pre class="terminal bootcamp">
	<span class="codeline">$ for i in ~/.ssh/*.pub; do ssh-keygen -l -f "$i"; done<span>Print fingerprint for each public key in the ".ssh" directory in your user directory</span></span>
	</pre>

	If the output says &ldquo;No such file or directory&ldquo; then you have no SSH keys locally or they are stored somewhere else.

2. <span class="step-title">Compare to fingerprints on GitHub.</span>

	If you did not receive a &ldquo;No such file or directory&ldquo; message then what you see should look something like this:

	<pre class="terminal bootcamp">
	<span class="codeline">$ for i in ~/.ssh/*.pub; do ssh-keygen -l -f "$i"; done<span>Print fingerprint for each public key in the ".ssh" directory in your user directory</span></span>
	<span class="bash-output">2048 c2:d1:0d:35:7f:b0:7d:44:c3:7d:7d:76:55:ff:99:7b /Users/chris/.ssh/github.pub (RSA)<br>2048 b7:82:bf:e4:08:33:f9:45:b5:f5:40:cf:60:ab:47:51 /Users/chris/.ssh/staging.pub (RSA)</span>
	</pre>

	The fingerprints are the hexidecimal strings, e.g. <code>22:d4:ab:9d:be:a9:4f:86:a2:05:45:88:0d:14:ea:e8</code>.

	Now open <https://github.com/settings/ssh> and make sure the fingerprints attached to your GitHub account match the fingerprints in Terminal.

3. <span class="step-title">Fingerprints don't match?</span>

	If there are any SSH keys attached to your account that you don't recognize <b>delete them immediately</b>.

	If all the fingerprints match then you are safe - continue social coding.


