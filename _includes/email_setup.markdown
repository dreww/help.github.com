
1. <span class="step-title">Set your username and email.</span>

	Git tracks who makes each commit by checking the user&rsquo;s name and email. In addition, we use this info to associate your commits with your GitHub account. To set these, enter the code below, replacing the name and email with your own. The name should be your _actual name_, not your GitHub username.

	<pre class="terminal bootcamp">
		<span class="codeline">$ git config --global user.name "<em>Firstname Lastname</em>"<span>Sets the name of the user for all git instances on the system</span></span>
		<span class="codeline">$ git config --global user.email "<em>your_email@youremail.com</em>"<span>Sets the email of the user for all git instances on the system</span></span>
	</pre>

	<div class="more-info">
		<h4 class="compressed">More about user info</h4>
		<div class="more-content">
			<p>
				The steps listed above show you how to set your user info globally. This means that no matter which repo you work in on your computer, you&rsquo;ll be making commits as that user. If you find yourself needing to make commits with different user info for a specific repo (perhaps for work vs. personal projects), you will have to change the info in that repo itself.
			</p>
			<pre class="terminal bootcamp">
				<span class="codeline">$ cd <em>my_other_repo</em><span>Changes the working directory to the repo you need to switch info for</span></span>
				<span class="codeline">$ git config user.name "<em>Different Name</em>"<span>Sets the user's name for this specific repo</span></span>
				<span class="codeline">$ git config user.email "<em>differentemail@email.com</em>"<span>Sets the user's email for this specific repo</span></span>
			</pre>
			<p>
				Now your commits will be &ldquo;blamed&rdquo; on (associated with) new user name and email whenever working in the specified repo.
			</p>
		</div>
	</div>

2. <span class="step-title">Set your GitHub token.</span>

    Previous versions of our API used token authentication, but we're removing support for that soon, see https://github.com/blog/1090-github-api-moving-on for details.

    If you are using a 3rd party tool that is asking for your token, you should contact the maintainer and ask them to update to our [latest API](http://developer.github.com/v3/) as the old API will stop working soon.

    Please note you do not need the API Token to work with git.