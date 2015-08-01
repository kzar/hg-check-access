# hg-check-access

## Intro

Simple Python script to help check which Mercurial repositories you have access to.
For a given hgweb URL and base repository URL the script will return a list of
repository names with True / False depending on weather access to it has been
granted or not.

For example:

    ./hg-check-access https://hg.adblockplus.org ssh://hg@ssh.adblockplus.org

    abpbot False
    abpcrawler False
    abpcustomization False
    abpwatcher False
    actionbarsherlock False
    adblockplus False
    adblockplusandroid False
    adblockpluschrome True
    adblockpluscore False
    ...

I specifically wrote the script in order to double-check which Adblock Plus
repositories I had access to. I've avoided hard-coding the URLs though in
case it's useful for other teams too.

### Update

If you're using this at Adblock Plus... stop! Wladimir has added this functionality to the Mercurial server, attempt to SSH to `hg@ssh.adblockplus.org` and the repositories you have access to will be displayed:

    ssh hg@ssh.adblockplus.org

    PTY allocation request failed on channel 0
    You can access the following repositories: adblockpluschrome cms sitescripts web.adblockplus.org web.eyeo.com
    Connection to ssh.adblockplus.org closed.a

Much quicker and easier!
