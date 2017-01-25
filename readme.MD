* Copyright 2017, Shoppr Labs Sdn Bhd
* Marcus Low

How to use
==========

Treat Config as your tree key-value store.
Where key = filename, value = content
Use the directory as your structure for information navigation.

Example of how i use it to read the exception list for sitemaps for SG.
	# You need PyGitHub - > pip install PyGitHub

        from github import Github
	g = Github(GIT_READER_NAME, GIT_READER_PASS)
        user = g.get_user()
        org  = user.get_orgs()[0]
        repo = org.get_repo("Config")
        
        data = repo.get_contents("{}/sitemaps/exceptions.json".format(country.upper()))
        actualdata = json.loads(data.decoded_content)

