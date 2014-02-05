gtm-oauth2
==========

Unofficial Git Repo representing the gtm-oath2 SVN repo from googlecode.com
--------------------------------------------------------

This repo is meant to stay in lockstep with the SVN repository and as such
should not be modified on it's own.  If there are changes in the SVN repository
that should be pulled into this copy I would recommend the following steps

    cd [local repository]
    mkdir /tmp/new-gtm-oath2-read-only
    svn export http://gtm-oauth2.googlecode.com/svn/trunk/ /tmp/new-gtm-oauth2-read-only
    rm -rf .
    mv /tmp/new-gtm-oauth2-read-only/* ./
    git add --all .
    git ci -m 'Updates to SVN revision [????]'


INSTALATION
===========

in your project directory run:

    git submodule add git@github.com:pivotalshiny/gtm-oauth2.git Externals/gtm-oauth2

then:

add Externals/gtm-oauth2/Source/GTMOAuth2.xcodeproj to your project

add OAuthTouchStaticLib (GTMOAuth2) to "Target Dependencies"

add libOAuthTouch2.a to "Link Binary With Libraries"

add "$(SOURCE_ROOT)/Externals/gtm-oauth2/Source"
  and "$(SOURCE_ROOT)/Externals/gtm-oauth2/HTTPFetcher"
  to "Header Search Paths"
